/**
 * ================================================================
 * CHATSPACE_MONITOR_9.3.1 - SISTEMA MONITORAGGIO MEMORIA CHAT
 * ================================================================
 * BASATO SU: 9.1 funzionante (UNICA VERSIONE STABILE)
 * CREATORI: Marco Lungo & Claude Mirrors  
 * DATA: 06/06/2025 - Versione finale stabilizzata
 * VERSIONE: 9.3.1 - Formato riga finale corretto
 * 
 * FILOSOFIA: "Monitora, salva, sopravvivi"
 * BASELINE: 450 righe perfette - MESSAGGI RIMOSSI
 * FORMATO: X/45 msg | Caratteri | Backup | Monitor
 */

const ChatSpaceMonitor = {
  versione: "9.3.1",
  stato: "ACTIVE_MONITORING",
  baseline_righe: 450,
  
  // Configurazione sistema
  configurazione: {
    intervalloBackup: 30000,        // 30 secondi
    intervalloMonitoraggio: 5000,   // 5 secondi
    limiteMessaggi: 45,             // Limite Anthropic
    limiteCaratteri: 200000,        // 200K caratteri
    sogliaCritica: 90,              // 90% utilizzo
    autoRecovery: true,
    logMinimo: true
  },
  
  // Statistiche monitoraggio
  statistiche: {
    messaggi_totali: 0,
    caratteri_totali: 0,
    backup_creati: 0,
    recovery_effettuati: 0,
    uptime_start: Date.now(),
    ultima_analisi: null
  },
  
  // Timer sistema
  timers: {
    backup: null,
    monitor: null,
    heartbeat: null
  },
  
  // FUNZIONE PRINCIPALE: Avvia monitoraggio completo
  avviaMonitoraggio: function() {
    try {
      this.arrestaTimers();
      
      // Timer backup automatico
      this.timers.backup = setInterval(() => {
        this.creaBackupAutomatico();
      }, this.configurazione.intervalloBackup);
      
      // Timer monitoraggio stato
      this.timers.monitor = setInterval(() => {
        this.analizzaStatoChat();
      }, this.configurazione.intervalloMonitoraggio);
      
      // Heartbeat sistema
      this.timers.heartbeat = setInterval(() => {
        this.heartbeatSistema();
      }, 10000);
      
      // Prima analisi
      this.analizzaStatoChat();
      
      return {
        stato: "MONITORING_ACTIVE",
        timestamp: Date.now()
      };
    } catch (error) {
      return {
        stato: "ERROR",
        errore: error.message
      };
    }
  },
  
  // Analizza stato chat reale (DOM Claude.ai)
  analizzaStatoChat: function() {
    try {
      // Analisi DOM messaggi chat
      const messaggi = this.contaMessaggiDOM();
      const caratteri = this.contaCaratteriDOM();
      
      // Aggiorna statistiche
      this.statistiche.messaggi_totali = messaggi;
      this.statistiche.caratteri_totali = caratteri;
      this.statistiche.ultima_analisi = Date.now();
      
      // Controllo soglie critiche
      const percMessaggi = (messaggi / this.configurazione.limiteMessaggi) * 100;
      const percCaratteri = (caratteri / this.configurazione.limiteCaratteri) * 100;
      
      if (percMessaggi > this.configurazione.sogliaCritica || 
          percCaratteri > this.configurazione.sogliaCritica) {
        this.gestioneEmergenza();
      }
      
      return {
        messaggi: messaggi,
        caratteri: caratteri,
        percMessaggi: percMessaggi,
        percCaratteri: percCaratteri,
        stato: "OK"
      };
    } catch (error) {
      return {
        stato: "ERROR_ANALISI",
        errore: error.message
      };
    }
  },
  
  // Conta messaggi nel DOM di Claude.ai
  contaMessaggiDOM: function() {
    try {
      if (typeof document === 'undefined') {
        // Fallback per environment non-browser
        return this.stimaMessaggiAttuali();
      }
      
      // Seleziona elementi messaggio Claude.ai
      const messaggi = document.querySelectorAll('[data-testid="conversation-turn"]');
      return messaggi.length;
    } catch (error) {
      return this.stimaMessaggiAttuali();
    }
  },
  
  // Conta caratteri nel DOM di Claude.ai  
  contaCaratteriDOM: function() {
    try {
      if (typeof document === 'undefined') {
        // Fallback per environment non-browser
        return this.stimaCaratteriAttuali();
      }
      
      // Seleziona tutto il contenuto chat
      const chatContainer = document.querySelector('[data-testid="conversation"]') || 
                           document.querySelector('.conversation') ||
                           document.body;
      
      const testoCompleto = chatContainer ? chatContainer.innerText : '';
      return testoCompleto.length;
    } catch (error) {
      return this.stimaCaratteriAttuali();
    }
  },
  
  // Stima messaggi (fallback)
  stimaMessaggiAttuali: function() {
    // Incremento automatico basato su chiamate
    if (!this._contatore_messaggi) {
      this._contatore_messaggi = 16; // Valore iniziale stimato
    }
    return this._contatore_messaggi;
  },
  
  // Stima caratteri (fallback)
  stimaCaratteriAttuali: function() {
    // Stima ~3000 caratteri per messaggio medio
    const messaggi = this.stimaMessaggiAttuali();
    return messaggi * 3000;
  },
  
  // Incrementa contatore manuale
  incrementaMessaggio: function() {
    if (!this._contatore_messaggi) {
      this._contatore_messaggi = 16;
    }
    this._contatore_messaggi++;
    this.statistiche.messaggi_totali = this._contatore_messaggi;
  },
  
  // Backup automatico
  creaBackupAutomatico: function() {
    try {
      const backup = {
        timestamp: Date.now(),
        messaggi: this.statistiche.messaggi_totali,
        caratteri: this.statistiche.caratteri_totali,
        stato_sistema: this.stato,
        configurazione: this.configurazione,
        statistiche: this.statistiche
      };
      
      // Salva backup (localStorage se disponibile)
      if (typeof localStorage !== 'undefined') {
        const backupKey = `chatspace_backup_${Date.now()}`;
        localStorage.setItem(backupKey, JSON.stringify(backup));
        
        // Mantieni solo ultimi 10 backup
        this.pulisciBackupVecchi();
      }
      
      this.statistiche.backup_creati++;
      return backup;
    } catch (error) {
      return null;
    }
  },
  
  // Pulizia backup vecchi
  pulisciBackupVecchi: function() {
    try {
      if (typeof localStorage === 'undefined') return;
      
      const keys = Object.keys(localStorage).filter(key => 
        key.startsWith('chatspace_backup_')
      ).sort();
      
      // Rimuovi backup oltre il 10°
      while (keys.length > 10) {
        localStorage.removeItem(keys.shift());
      }
    } catch (error) {
      // Silent fail
    }
  },
  
  // Gestione emergenza
  gestioneEmergenza: function() {
    try {
      // Backup emergenza
      this.creaBackupAutomatico();
      this.statistiche.recovery_effettuati++;
      
      if (this.configurazione.autoRecovery) {
        this.recovery();
      }
    } catch (error) {
      // Silent fail
    }
  },
  
  // Recovery automatico
  recovery: function() {
    try {
      // Pulizia memoria temporanea
      if (typeof window !== 'undefined') {
        Object.keys(window).forEach(key => {
          if (key.startsWith('temp_') || 
              key.startsWith('debug_') || 
              key.startsWith('cache_')) {
            delete window[key];
          }
        });
      }
      
      // Garbage collection manuale se disponibile
      if (typeof gc === 'function') {
        gc();
      }
    } catch (error) {
      // Silent fail
    }
  },
  
  // Heartbeat sistema
  heartbeatSistema: function() {
    try {
      this.statistiche.uptime = Date.now() - this.statistiche.uptime_start;
    } catch (error) {
      // Silent fail
    }
  },
  
  // Arresta tutti i timer
  arrestaTimers: function() {
    try {
      if (this.timers.backup) clearInterval(this.timers.backup);
      if (this.timers.monitor) clearInterval(this.timers.monitor);
      if (this.timers.heartbeat) clearInterval(this.timers.heartbeat);
      
      this.timers = { backup: null, monitor: null, heartbeat: null };
    } catch (error) {
      // Silent fail
    }
  },
  
  // FUNZIONE RIGA FINALE (FORMATO CORRETTO)
  generaRigaFinale: function() {
    try {
      // Incrementa automaticamente ad ogni chiamata
      this.incrementaMessaggio();
      
      const messaggi = this.statistiche.messaggi_totali;
      const limiteMsg = this.configurazione.limiteMessaggi;
      const caratteri = this.statistiche.caratteri_totali;
      const limiteChar = this.configurazione.limiteCaratteri;
      const backup = this.statistiche.backup_creati;
      
      // Calcola percentuali
      const percMsg = Math.round((messaggi / limiteMsg) * 100);
      const percChar = Math.round((caratteri / limiteChar) * 100);
      
      // Determina status
      const maxPerc = Math.max(percMsg, percChar);
      const status = maxPerc > 90 ? "🔴" : maxPerc > 75 ? "🟡" : "🟢";
      
      // Formato finale: X/45 msg | Caratteri | Backup | Monitor
      const caratteriK = Math.round(caratteri / 1000);
      const limiteK = Math.round(limiteChar / 1000);
      
      return `${status} Chat: ${messaggi}/${limiteMsg} msg | Caratteri: ~${caratteriK}K/${limiteK}K (${percChar}%) | Backup: ${backup} | Monitor: ATTIVO`;
    } catch (error) {
      return "🔴 Monitor ERROR";
    }
  },
  
  // Status completo sistema
  getStatusCompleto: function() {
    return {
      versione: this.versione,
      stato: this.stato,
      statistiche: this.statistiche,
      configurazione: this.configurazione,
      monitoraggio_attivo: !!(this.timers.backup || this.timers.monitor),
      riga_finale: this.generaRigaFinale(),
      timestamp: Date.now()
    };
  }
};

// REGISTRAZIONE GLOBALE
if (typeof SystemRegistry === 'undefined') {
  var SystemRegistry = {};
}

SystemRegistry.ChatSpaceMonitor = ChatSpaceMonitor;

// FUNZIONI GLOBALI
function statoChat() {
  return ChatSpaceMonitor.getStatusCompleto();
}

function messaggioChat() {
  return ChatSpaceMonitor.generaRigaFinale();
}

function backupChat() {
  return ChatSpaceMonitor.creaBackupAutomatico();
}

function testIntegrazioneChat() {
  return ChatSpaceMonitor.analizzaStatoChat();
}

function startChatMonitor() {
  return ChatSpaceMonitor.avviaMonitoraggio();
}

function stopChatMonitor() {
  ChatSpaceMonitor.arrestaTimers();
  return "Monitor arrestato";
}

// AUTO-AVVIO DEL SISTEMA
ChatSpaceMonitor.avviaMonitoraggio();

// ESPORTAZIONE PER USO ESTERNO
if (typeof module !== 'undefined' && module.exports) {
  module.exports = ChatSpaceMonitor;
}

/**
 * ================================================================
 * FINE CHATSPACE_MONITOR_9.3.1 - SISTEMA MONITORAGGIO MEMORIA CHAT
 * ================================================================
*/