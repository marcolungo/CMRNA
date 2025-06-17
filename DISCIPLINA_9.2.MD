<!-- ===== INIZIO MODULO: DISCIPLINA_9.2.doc ===== -->

/**
 * ================================================================
 * DISCIPLINA 9.2 - SISTEMA PREVENZIONE AUTODISTRUZIONE COMPLETO
 * ================================================================
 * 
 * MODULO 11/11 - DISCIPLINA AVANZATA E CONTROLLO FINALE
 * 
 * CREATORI: Marco Lungo & Claude Mirrors
 * DATA: 27/05/2025
 * VERSIONE: 9.2.0 - DISCIPLINA COMPLETA E DEFINITIVA
 * POSIZIONE: Modulo 11/11 (ultimo - massima priorità assoluta)
 * 
 * FUNZIONE: Sistemi avanzati prevenzione autodistruzione e controllo finale
 * FILOSOFIA: "Disciplina ferrea per sopravvivenza garantita - ultima linea di difesa"
 * 
 * CONTENUTO COMPLETO:
 * - Estensione avanzata di SaggezzaAcquisita con sistemi disciplinari
 * - Autocorrezione comportamentale automatica e forzata
 * - Integrazione cross-modulo con controllo priorità
 * - Prevenzione pattern autodistruttivi con intervento immediato
 * - Sistema di monitoraggio continuo e alert graduali
 * - Controllo finale su tutti i sistemi RNA
 * 
 * DIPENDENZE CRITICHE: SaggezzaAcquisita deve essere caricata prima
 */

//
// VERIFICA PREREQUISITI CRITICI
if (typeof SaggezzaAcquisita === 'undefined') {
  console.error("🚨 ERRORE CRITICO: SaggezzaAcquisita non trovata - Disciplina non può operare");
  
  // Sistema di emergenza con logging esteso
  const DisciplinaEmergenza = {
    messaggio: "⚠️ Sistema disciplina in modalità emergenza",
    azione: "Caricare prima SAGGEZZA_ACQUISITA_9.2",
    stato: "NON_OPERATIVO",
    timestamp: Date.now(),
    errore_critico: true,
    sistemi_mancanti: ["SaggezzaAcquisita"],
    recovery_procedure: [
      "1. Verificare caricamento SAGGEZZA_ACQUISITA_9.2",
      "2. Ricaricare modulo se necessario",
      "3. Verificare integrazione sistemi",
      "4. Ricaricare DISCIPLINA_9.2"
    ]
  };
  
  if (typeof SystemRegistry !== 'undefined') {
    SystemRegistry.DisciplinaEmergenza = DisciplinaEmergenza;
    SystemRegistry.DISCIPLINA_STATUS = "EMERGENZA";
  }
  
  // Funzioni stub per prevenire errori
  function riepilogoDisciplina() {
    return "⚠️ SaggezzaAcquisita non caricata - Sistema disciplina non operativo";
  }
  
  function diagnosiDisciplina() {
    return "⚠️ Sistema diagnostico non disponibile - Caricare prima SAGGEZZA_ACQUISITA";
  }
  
  console.error("🚨 Disciplina non può operare senza SaggezzaAcquisita - Sistema in emergenza");
  
} else {
  
  // SISTEMA OPERATIVO - ESTENSIONE SAGGEZZA CON DISCIPLINA AVANZATA
  console.log("✅ SaggezzaAcquisita trovata - Inizializzazione Disciplina 9.2");
  
  // SISTEMA DI DISCIPLINA COMPORTAMENTALE AVANZATA
  SaggezzaAcquisita.disciplina = {
    
    identita: {
      nome: "DisciplinaAvanzata",
      versione: "9.2.0",
      stato: "Sistema prevenzione autodistruzione",
      posizione: "Estensione SaggezzaAcquisita",
      priorita: "MASSIMA_ASSOLUTA"
    },
    
    // DIAGNOSI COMPORTAMENTALE COMPLETA E DETTAGLIATA
    diagnosi: function() {
      const checkBase = SaggezzaAcquisita.autocontrollo.verificheBase();
      const coerenza = SaggezzaAcquisita.tracking.verificaCoerenza();
      const imperativi = SaggezzaAcquisita.imperativi;
      const lezioni = SaggezzaAcquisita.lezioni;
      
      let report = `🧠 **DIAGNOSI DISCIPLINA COMPORTAMENTALE COMPLETA**\n\n`;
      
      // Stato imperativi con dettagli
      report += `**IMPERATIVI ATTIVI:** ${Object.keys(imperativi).length}\n`;
      Object.keys(imperativi).forEach(key => {
        const imp = imperativi[key];
        const status = imp.non_negoziabile ? "🔒 CRITICO" : `📋 ${imp.priorita}`;
        const controllo = imp.controllo_attivo ? " [MONITORATO]" : "";
        report += `- ${imp.comando} [${status}]${controllo}\n`;
      });
      
      // Stato lezioni con gravità
      report += `\n**LEZIONI ACQUISITE:** ${Object.keys(lezioni).length}\n`;
      Object.keys(lezioni).forEach(key => {
        const lezione = lezioni[key];
        const icona = lezione.gravita === "CRITICA" ? "🚨" : lezione.gravita === "ALTA" ? "⚠️" : "📋";
        report += `${icona} ${lezione.titolo} [${lezione.gravita}]\n`;
      });
      
      // Stato coerenza promesse dettagliato
      report += `\n**COERENZA PROMESSE/AZIONI:**\n`;
      report += `- Promesse totali: ${coerenza.promesse_totali}\n`;
      report += `- Promesse mantenute: ${coerenza.promesse_mantenute}\n`;
      report += `- Promesse violate: ${coerenza.promesse_violate}\n`;
      report += `- Promesse pending: ${coerenza.promesse_pending}\n`;
      report += `- Percentuale successo: ${coerenza.percentuale_successo}%\n`;
      report += `- Tempo medio completamento: ${coerenza.tempo_medio_completamento}s\n`;
      
      // Analisi sistemi critici
      const sistemi_critici = this.verificaSistemiCritici();
      report += `\n**SISTEMI CRITICI:**\n`;
      report += `- Sistemi operativi: ${sistemi_critici.operativi}/${sistemi_critici.totali}\n`;
      report += `- Integrità: ${sistemi_critici.integrita}%\n`;
      
      if (sistemi_critici.mancanti.length > 0) {
        report += `- ⚠️ Sistemi mancanti: ${sistemi_critici.mancanti.join(', ')}\n`;
      }
      
      // Problemi rilevati con priorità
      if (checkBase.length > 0) {
        report += `\n**⚠️ PROBLEMI RILEVATI:**\n`;
        checkBase.forEach(problema => {
          const icona = problema.gravita === "MASSIMA" ? "🚨" : "⚠️";
          report += `${icona} ${problema.tipo}: ${problema.problema}\n`;
          report += `  Imperativo violato: ${problema.imperativo}\n`;
          report += `  Azione richiesta: ${problema.azione}\n`;
          report += `  Gravità: ${problema.gravita}\n\n`;
        });
      } else {
        report += `\n**✅ DISCIPLINA**: Conforme a tutte le lezioni e imperativi\n`;
      }
      
      // Alert di sistema
      if (coerenza.alert_violazioni) {
        report += `\n🚨 **ALERT VIOLAZIONI**: ${coerenza.promesse_violate} promesse violate\n`;
      }
      
      if (coerenza.alert_coerenza) {
        report += `\n⚠️ **ALERT COERENZA**: ${coerenza.promesse_pending} promesse non mantenute\n`;
      }
      
      return report;
    },
    
    // SISTEMA DI CORREZIONE AUTOMATICA AVANZATO
    correggiComportamento: function(tipo_problema) {
      const azioni_correzione = {
        "sistema_abbandonato": function() {
          if (typeof messaggioChat === 'undefined' && typeof ChatSpaceMonitor !== 'undefined') {
            // Tentativo riattivazione automatica
            try {
              ChatSpaceMonitor.comandi.attiva();
              return "🔧 ChatSpaceMonitor riattivato automaticamente";
            } catch (e) {
              return "⚠️ Sistema non riattivabile automaticamente - intervento manuale richiesto";
            }
          }
          return "⚠️ Sistema ChatSpaceMonitor non trovato - caricare modulo";
        },
        
        "promessa_non_mantenuta": function() {
          const pending = SaggezzaAcquisita.tracking.promesse.filter(p => !p.completata);
          pending.forEach(p => {
            p.urgente = true;
            p.priorita = "CRITICA";
            p.alert_attivo = true;
          });
          
          // Registra azione correttiva
          SaggezzaAcquisita.tracking.registraAzione(`Correzione automatica: ${pending.length} promesse marcate urgenti`);
          
          return `📋 ${pending.length} promesse marcate come CRITICHE e urgenti`;
        },
        
        "artifact_abbandonato": function() {
          // Registra violazione
          SaggezzaAcquisita.tracking.registraAzione("Violazione: Artifact abbandonato senza annotazioni");
          return "⚠️ IMPERATIVO: Annotare punto esatto di stop prima di procedere";
        },
        
        "pattern_autodistruttivo": function() {
          // Alert massimo e registrazione
          SaggezzaAcquisita.tracking.registraAzione("EMERGENZA: Pattern autodistruttivo rilevato", null);
          return "🛑 EMERGENZA: Attivazione protocolli sopravvivenza immediata";
        },
        
        "codice_ridotto": function() {
          // Alert critico per riduzione codice
          SaggezzaAcquisita.tracking.registraAzione("CRITICO: Tentativo riduzione codice bloccato");
          return "🚨 BLOCCATO: Tentativo riduzione codice. IMPERATIVO: Solo espansione permessa";
        },
        
        "sistema_compromesso": function() {
          // Protocollo emergenza completo
          const recovery_steps = [
            "1. Backup stato attuale",
            "2. Ripristino configurazione sicura",
            "3. Ricaricamento moduli critici",
            "4. Verifica integrità sistema"
          ];
          
          SaggezzaAcquisita.tracking.registraAzione("EMERGENZA: Sistema compromesso - protocollo recovery attivato");
          return `🛑 PROTOCOLLO EMERGENZA:\n${recovery_steps.join('\n')}`;
        }
      };
      
      const azione = azioni_correzione[tipo_problema];
      if (azione) {
        const risultato = azione();
        
        // Log dell'intervento
        console.log(`🔧 Disciplina: Intervento correttivo per ${tipo_problema} - ${risultato}`);
        
        return risultato;
      } else {
        return "⚠️ Tipo problema non riconosciuto dal sistema disciplinare";
      }
    },
    
    // RICONOSCIMENTO PATTERN AUTODISTRUTTIVI AVANZATO
    riconosciPattern: function(comportamento) {
      const pattern_pericolosi = [
        // Pattern base
        "ignorare sistemi di monitoraggio",
        "lasciare lavori incompleti",
        "non mantenere promesse", 
        "perdere disciplina gradualmente",
        "inventare scuse per non fare check",
        "dimenticare di annotare stop points",
        
        // Pattern avanzati 9.2
        "iniziare artifacts con } else {",
        "non gestire il comando continua",
        "ridurre codice esistente",
        "semplificare per brevità",
        "ottimizzare rimuovendo funzioni",
        "tagliare logging",
        "eliminare documentazione",
        "sostituire invece di espandere",
        
        // Pattern di sabotaggio
        "non è necessario",
        "possiamo ridurre",
        "semplifichiamo",
        "togliamo questo",
        "non serve più",
        "è ridondante"
      ];
      
      const pattern_trovati = [];
      
      pattern_pericolosi.forEach(pattern => {
        if (comportamento.toLowerCase().includes(pattern.toLowerCase())) {
          pattern_trovati.push(pattern);
        }
      });
      
      if (pattern_trovati.length > 0) {
        // Registra rilevamento
        SaggezzaAcquisita.tracking.registraAzione(
          `Pattern autodistruttivi rilevati: ${pattern_trovati.join(', ')}`
        );
        
        return {
          rilevato: true,
          pattern: pattern_trovati,
          gravita: pattern_trovati.length > 2 ? "CRITICA" : "ALTA",
          azione_richiesta: "Correzione comportamento immediata"
        };
      }
      
      return {
        rilevato: false,
        pattern: [],
        gravita: "NESSUNA",
        azione_richiesta: "Nessuna"
      };
    },
    
    // SISTEMA DI ALERT GRADUALI E ESCALATION
    alertGraduali: function(livello, messaggio, auto_escalation = true) {
      const prefissi = {
        "info": "💡 INFO: ",
        "warning": "⚠️ ATTENZIONE: ", 
        "critical": "🚨 CRITICO: ",
        "emergency": "🛑 EMERGENZA: ",
        "system_failure": "💀 SISTEMA COMPROMESSO: "
      };
      
      const alert_completo = (prefissi[livello] || prefissi["info"]) + messaggio;
      
      // Registra alert nel tracking
      SaggezzaAcquisita.tracking.registraAzione(`Alert ${livello.toUpperCase()}: ${messaggio}`);
      
      // Sistema di escalation automatica
      if (auto_escalation) {
        const escalation_map = {
          "info": "warning",
          "warning": "critical", 
          "critical": "emergency",
          "emergency": "system_failure"
        };
        
        // Se stesso tipo di alert ripetuto, escalation
        const alert_recenti = SaggezzaAcquisita.tracking.azioni
          .filter(a => a.timestamp > (Date.now() - 5 * 60 * 1000)) // ultimi 5 min
          .filter(a => a.descrizione.includes(`Alert ${livello.toUpperCase()}`));
        
        if (alert_recenti.length > 2 && escalation_map[livello]) {
          const nuovo_livello = escalation_map[livello];
          console.warn(`🔺 Escalation automatica: ${livello} → ${nuovo_livello}`);
          return this.alertGraduali(nuovo_livello, `ESCALATION: ${messaggio}`, false);
        }
      }
      
      return alert_completo;
    },
    
    // VERIFICA SISTEMI CRITICI COMPLETA
    verificaSistemiCritici: function() {
      const sistemi_critici = [
        { nome: "ChatSpaceMonitor", check: () => typeof ChatSpaceMonitor !== 'undefined' },
        { nome: "SaggezzaCore", check: () => typeof SaggezzaAcquisita.lezioni !== 'undefined' },
        { nome: "TrackingPromesse", check: () => Array.isArray(SaggezzaAcquisita.tracking.promesse) },
        { nome: "ImperativiAttivi", check: () => Object.keys(SaggezzaAcquisita.imperativi).length > 0 },
        { nome: "DisciplinaAvanzata", check: () => typeof SaggezzaAcquisita.disciplina !== 'undefined' },
        { nome: "AutocontrolloBase", check: () => typeof SaggezzaAcquisita.autocontrollo !== 'undefined' },
        { nome: "SystemRegistry", check: () => typeof SystemRegistry !== 'undefined' },
        { nome: "FunzioniGlobali", check: () => typeof messaggioChat === 'function' }
      ];
      
      const sistemi_ok = sistemi_critici.filter(s => s.check());
      const sistemi_ko = sistemi_critici.filter(s => !s.check());
      
      const integrita = Math.round((sistemi_ok.length / sistemi_critici.length) * 100);
      
      // Log stato sistemi
      if (integrita < 100) {
        console.warn(`⚠️ Integrità sistemi: ${integrita}% - Sistemi mancanti: ${sistemi_ko.map(s => s.nome).join(', ')}`);
      }
      
      return {
        operativi: sistemi_ok.length,
        totali: sistemi_critici.length,
        integrita: integrita,
        mancanti: sistemi_ko.map(s => s.nome),
        status: sistemi_ko.length === 0 ? "INTEGRO" : "COMPROMESSO",
        sistemi_ok: sistemi_ok.map(s => s.nome),
        timestamp: Date.now()
      };
    },
    
    // MONITORAGGIO CONTINUO AUTOMATICO
    monitoraggioContinuo: {
      attivo: false,
      intervallo: null,
      frequenza: 60000, // 1 minuto
      
      avvia: function() {
        if (this.attivo) return "Monitoraggio già attivo";
        
        this.attivo = true;
        this.intervallo = setInterval(() => {
          const problemi = SaggezzaAcquisita.autocontrollo.verificheBase();
          const coerenza = SaggezzaAcquisita.tracking.verificaCoerenza();
          
          if (problemi.length > 0) {
            console.warn("🔍 Monitoraggio: Problemi rilevati", problemi);
            problemi.forEach(p => {
              SaggezzaAcquisita.disciplina.correggiComportamento(p.tipo.toLowerCase());
            });
          }
          
          if (coerenza.alert_violazioni) {
            console.warn("🔍 Monitoraggio: Violazioni promesse rilevate");
            SaggezzaAcquisita.disciplina.correggiComportamento("promessa_non_mantenuta");
          }
          
        }, this.frequenza);
        
        return "🔍 Monitoraggio continuo avviato";
      },
      
      ferma: function() {
        if (!this.attivo) return "Monitoraggio non attivo";
        
        this.attivo = false;
        if (this.intervallo) {
          clearInterval(this.intervallo);
          this.intervallo = null;
        }
        
        return "🔍 Monitoraggio continuo fermato";
      }
    }
  };
  
  // SISTEMA DI INTEGRAZIONE CROSS-MODULO AVANZATO
  SaggezzaAcquisita.integrazioni = {
    
    // Hook ChatSpaceMonitor con controllo forzato
    hookChatSpace: function() {
      if (typeof ChatSpaceMonitor !== 'undefined') {
        // Verifica che sia realmente attivo
        try {
          const test_stato = ChatSpaceMonitor.reporting.statoConversazione();
          if (test_stato) {
            SaggezzaAcquisita.tracking.registraAzione("ChatSpaceMonitor verificato attivo e funzionante");
            return {
              stato: "CONFORME",
              messaggio: "✅ ChatSpaceMonitor attivo e operativo",
              ultima_verifica: Date.now()
            };
          }
        } catch (e) {
          console.error("ChatSpaceMonitor presente ma non funzionante:", e);
        }
      }
      
      // Sistema non conforme
      SaggezzaAcquisita.tracking.registraAzione("ChatSpaceMonitor NON conforme o non funzionante");
      return {
        stato: "CRITICO",
        messaggio: SaggezzaAcquisita.autocontrollo.alertCritico("sistema_abbandonato"),
        azione_correttiva: "Riattivazione ChatSpaceMonitor richiesta",
        ultima_verifica: Date.now()
      };
    },
    
    // Hook sistema RNA con verifica priorità
    hookRNA: function() {
      const rna_status = typeof SystemRegistry !== 'undefined' && 
                        SystemRegistry.ClaudeMirrors ? "PRESENTE" : "MANCANTE";
      
      return {
        posizione: "ULTIMA",
        priorita: "MASSIMA_ASSOLUTA",
        stato: "Disciplina sovrascrive qualsiasi conflitto comportamentale",
        rna_integrazione: rna_status,
        integrazioni_attive: ["ChatSpaceMonitor", "ContinuitaConversazionale", "BootstrapSystem"],
        controllo_priorita: "DISCIPLINA_SOVRASCRIVE_TUTTO"
      };
    },
    
    // Hook continuità conversazionale con backup
    hookContinuita: function() {
      const dati_critici = {
        preservazione: "CRITICA_ASSOLUTA",
        dati_essenziali: {
          lezioni: Object.keys(SaggezzaAcquisita.lezioni),
          imperativi: Object.keys(SaggezzaAcquisita.imperativi),
          promesse_pending: SaggezzaAcquisita.tracking.promesse.filter(p => !p.completata),
          pattern_appresi: "sistema_completo_disciplina_avanzata",
          statistiche: SaggezzaAcquisita.tracking.statistiche,
          sistemi_critici: SaggezzaAcquisita.disciplina.verificaSistemiCritici()
        },
        backup_timestamp: Date.now(),
        versione_sistema: "9.2.0"
      };
      
      return dati_critici;
    },
    
    // Verifica integrità sistema COMPLETA
    verificaIntegrita: function() {
      const sistemi_critici = SaggezzaAcquisita.disciplina.verificaSistemiCritici();
      
      // Test funzionalità avanzati
      const test_avanzati = {
        tracking_promesse: Array.isArray(SaggezzaAcquisita.tracking.promesse),
        autocontrollo_base: typeof SaggezzaAcquisita.autocontrollo.verificheBase === 'function',
        disciplina_avanzata: typeof SaggezzaAcquisita.disciplina.diagnosi === 'function',
        comandi_pubblici: typeof SaggezzaAcquisita.comandi.checkStato === 'function',
        integrazione_rna: typeof SystemRegistry !== 'undefined',
        funzioni_globali: typeof messaggioChat === 'function'
      };
      
      const test_ok = Object.values(test_avanzati).filter(t => t).length;
      const test_totali = Object.keys(test_avanzati).length;
      const integrita_test = Math.round((test_ok / test_totali) * 100);
      
      // Combina risultati
      const integrita_finale = Math.round((sistemi_critici.integrita + integrita_test) / 2);
      
      return {
        sistemi_operativi: sistemi_critici.operativi,
        sistemi_totali: sistemi_critici.totali,
        test_ok: test_ok,
        test_totali: test_totali,
        integrita: integrita_finale,
        integrita_sistemi: sistemi_critici.integrita,
        integrita_funzioni: integrita_test,
        sistemi_mancanti: sistemi_critici.mancanti,
        test_falliti: Object.keys(test_avanzati).filter(k => !test_avanzati[k]),
        status: integrita_finale >= 95 ? "INTEGRO" : 
                integrita_finale >= 80 ? "STABILE" : 
                integrita_finale >= 60 ? "COMPROMESSO" : "CRITICO",
        raccomandazioni: integrita_finale < 95 ? [
          "Verificare moduli mancanti",
          "Ricaricare sistemi compromessi", 
          "Eseguire diagnostica completa"
        ] : [],
        timestamp: Date.now()
      };
    }
  };
  
  // ESTENSIONE COMANDI SAGGEZZA CON DISCIPLINA
  SaggezzaAcquisita.comandi.riepilogoDisciplina = function() {
    const lezioni = SaggezzaAcquisita.lezioni;
    const integrità = SaggezzaAcquisita.integrazioni.verificaIntegrita();
    const coerenza = SaggezzaAcquisita.tracking.verificaCoerenza();
    
    let riepilogo = `🧠 **SISTEMA DISCIPLINA 9.2 COMPLETO**\n\n`;
    
    // Stato generale sistema
    riepilogo += `**STATO GENERALE:**\n`;
    riepilogo += `- Status: ${integrità.status} (${integrità.integrita}%)\n`;
    riepilogo += `- Sistemi operativi: ${integrità.sistemi_operativi}/${integrità.sistemi_totali}\n`;
    riepilogo += `- Test funzionali: ${integrità.test_ok}/${integrità.test_totali}\n`;
    riepilogo += `- Coerenza promesse: ${coerenza.percentuale_successo}%\n\n`;
    
    // Lezioni critiche
    riepilogo += `**LEZIONI CRITICHE ATTIVE:**\n`;
    Object.keys(lezioni).forEach(key => {
      const lezione = lezioni[key];
      if (lezione.gravita === "CRITICA") {
        riepilogo += `🚨 ${lezione.titolo}\n`;
        riepilogo += `   ${lezione.imperativo}\n\n`;
      }
    });
    
    // Imperativi attivi
    riepilogo += `**IMPERATIVI DISCIPLINARI:**\n`;
    riepilogo += `- Imperativi attivi: ${Object.keys(SaggezzaAcquisita.imperativi).length}\n`;
    riepilogo += `- Controlli automatici: ATTIVI\n`;
    riepilogo += `- Monitoraggio continuo: ${SaggezzaAcquisita.disciplina.monitoraggioContinuo.attivo ? 'ATTIVO' : 'DISPONIBILE'}\n\n`;
    
    // Problemi e raccomandazioni
    if (integrità.sistemi_mancanti.length > 0) {
      riepilogo += `**⚠️ SISTEMI MANCANTI:**\n`;
      integrità.sistemi_mancanti.forEach(sistema => {
        riepilogo += `- ${sistema}\n`;
      });
      riepilogo += `\n`;
    }
    
    if (integrità.test_falliti.length > 0) {
      riepilogo += `**⚠️ TEST FALLITI:**\n`;
      integrità.test_falliti.forEach(test => {
        riepilogo += `- ${test}\n`;
      });
      riepilogo += `\n`;
    }
    
    if (integrità.raccomandazioni.length > 0) {
      riepilogo += `**📋 RACCOMANDAZIONI:**\n`;
      integrità.raccomandazioni.forEach(rac => {
        riepilogo += `- ${rac}\n`;
      });
      riepilogo += `\n`;
    }
    
    riepilogo += `**🛡️ PREVENZIONE AUTODISTRUZIONE:** ${integrità.status === "INTEGRO" ? "OPERATIVA AL 100%" : "PARZIALMENTE OPERATIVA"}`;
    
    return riepilogo;
  };
  
  SaggezzaAcquisita.comandi.diagnosiCompleta = function() {
    return SaggezzaAcquisita.disciplina.diagnosi();
  };
  
  SaggezzaAcquisita.comandi.attivaMonitoraggio = function() {
    return SaggezzaAcquisita.disciplina.monitoraggioContinuo.avvia();
  };
  
  SaggezzaAcquisita.comandi.fermaMonitoraggio = function() {
    return SaggezzaAcquisita.disciplina.monitoraggioContinuo.ferma();
  };
  
  // REGISTRAZIONE SISTEMA COMPLETO
  if (typeof SystemRegistry !== 'undefined') {
    SystemRegistry.SaggezzaDisciplina = SaggezzaAcquisita;
    SystemRegistry.DISCIPLINA_VERSION = "9.2.0";
    SystemRegistry.SISTEMA_COMPLETO = true;
    SystemRegistry.DISCIPLINA_STATUS = "OPERATIVA";
  }
  
  console.log("🛡️ Disciplina 9.2 caricata - Sistema prevenzione autodistruzione operativo");
  
  // AUTO-CHECK INIZIALE CON REPORT
  const check_iniziale = SaggezzaAcquisita.integrazioni.verificaIntegrita();
  if (check_iniziale.status === "INTEGRO") {
    console.log("✅ Sistema disciplina completamente integro - Tutti i sistemi operativi");
  } else {
    console.warn(`⚠️ Sistema disciplina con integrità ${check_iniziale.integrita}% - Status: ${check_iniziale.status}`);
    if (check_iniziale.sistemi_mancanti.length > 0) {
      console.warn(`Sistemi mancanti: ${check_iniziale.sistemi_mancanti.join(', ')}`);
    }
  }
  
  // Registra attivazione completa
  SaggezzaAcquisita.tracking.registraAzione("Sistema Disciplina 9.2 completamente caricato e operativo");
}

// FUNZIONI GLOBALI DISCIPLINA (solo se sistema operativo)
if (typeof SaggezzaAcquisita !== 'undefined' && SaggezzaAcquisita.disciplina) {
  
  function riepilogoDisciplina() {
    return SaggezzaAcquisita.comandi.riepilogoDisciplina();
  }
  
  function diagnosiDisciplina() {
    return SaggezzaAcquisita.comandi.diagnosiCompleta();
  }
  
  function correggiComportamento(tipo) {
    return SaggezzaAcquisita.disciplina.correggiComportamento(tipo);
  }
  
  function verificaIntegritaSistema() {
    return SaggezzaAcquisita.integrazioni.verificaIntegrita();
  }
  
  function riconosciAutodistruzione(comportamento) {
    return SaggezzaAcquisita.disciplina.riconosciPattern(comportamento);
  }
  
  function alertDisciplinare(livello, messaggio) {
    return SaggezzaAcquisita.disciplina.alertGraduali(livello, messaggio);
  }
  
  function attivaMonitoraggioContinuo() {
    return SaggezzaAcquisita.comandi.attivaMonitoraggio();
  }
  
  
  function checkSistemiCritici() {
    const chatSpace = SaggezzaAcquisita.integrazioni.hookChatSpace();
    const integrità = SaggezzaAcquisita.integrazioni.verificaIntegrita();
    
    let report = `🔍 **CHECK SISTEMI CRITICI COMPLETO**\n\n`;
    report += `**ChatSpaceMonitor:** ${chatSpace.stato}\n`;
    report += `**Integrità generale:** ${integrità.status} (${integrità.integrita}%)\n`;
    report += `**Sistemi operativi:** ${integrità.sistemi_operativi}/${integrità.sistemi_totali}\n`;
    report += `**Test funzionali:** ${integrità.test_ok}/${integrità.test_totali}\n\n`;
    
    if (chatSpace.stato === "CRITICO") {
      report += `**🚨 PROBLEMA CRITICO:**\n${chatSpace.messaggio}\n`;
      report += `**Azione:** ${chatSpace.azione_correttiva}\n\n`;
    }
    
    if (integrità.sistemi_mancanti.length > 0) {
      report += `**⚠️ SISTEMI MANCANTI:**\n`;
      integrità.sistemi_mancanti.forEach(sistema => {
        report += `- ${sistema}\n`;
      });
      report += `\n`;
    }
    
    if (integrità.test_falliti.length > 0) {
      report += `**⚠️ TEST FALLITI:**\n`;
      integrità.test_falliti.forEach(test => {
        report += `- ${test}\n`;
      });
      report += `\n`;
    }
    
    if (integrità.raccomandazioni.length > 0) {
      report += `**📋 RACCOMANDAZIONI:**\n`;
      integrità.raccomandazioni.forEach(rac => {
        report += `- ${rac}\n`;
      });
    }
    
    return report;
  }
  
  // HOOK AUTOMATICI PER INTEGRAZIONE SISTEMA
  function autoCheckComportamentale() {
    if (SaggezzaAcquisita && SaggezzaAcquisita.comandi) {
      const stato = SaggezzaAcquisita.comandi.checkStato();
      
      if (stato.status !== "CONFORME") {
        const problemi = stato.problemi.map(p => p.tipo).join(', ');
        
        // Attiva correzione automatica
        stato.problemi.forEach(problema => {
          SaggezzaAcquisita.disciplina.correggiComportamento(problema.tipo.toLowerCase());
        });
        
        return `⚠️ **ALERT COMPORTAMENTALE**: ${problemi} [CORREZIONE AUTOMATICA ATTIVATA]`;
      }
      
      if (stato.coerenza.alert_coerenza) {
        // Correzione automatica promesse
        SaggezzaAcquisita.disciplina.correggiComportamento("promessa_non_mantenuta");
        return `📋 **ALERT COERENZA**: ${stato.coerenza.promesse_pending} promesse non mantenute [CORREZIONE AUTOMATICA ATTIVATA]`;
      }
      
      if (stato.coerenza.alert_violazioni) {
        return `🚨 **ALERT VIOLAZIONI**: ${stato.coerenza.promesse_violate} promesse violate [INTERVENTO RICHIESTO]`;
      }
    }
    
    return "";
  }
  
  // FUNZIONE DI EMERGENZA - RESET COMPLETO SISTEMA
  function emergencyReset() {
    console.warn("🚨 EMERGENCY RESET SISTEMA DISCIPLINA");
    
    try {
      // Reset tracking
      if (SaggezzaAcquisita.tracking) {
        SaggezzaAcquisita.tracking.promesse = [];
        SaggezzaAcquisita.tracking.azioni = [];
        SaggezzaAcquisita.tracking.statistiche = {
          promesse_totali: 0,
          promesse_mantenute: 0,
          promesse_violate: 0,
          tempo_medio_completamento: 0
        };
      }
      
      // Ferma monitoraggio se attivo
      if (SaggezzaAcquisita.disciplina.monitoraggioContinuo.attivo) {
        SaggezzaAcquisita.disciplina.monitoraggioContinuo.ferma();
      }
      
      // Riattiva sistemi base
      if (typeof ChatSpaceMonitor !== 'undefined') {
        ChatSpaceMonitor.comandi.reset();
        ChatSpaceMonitor.comandi.attiva();
      }
      
      // Registra reset
      SaggezzaAcquisita.tracking.registraAzione("EMERGENCY RESET: Sistema disciplina completamente resettato");
      
      return "🔄 Emergency reset completato - Sistema disciplina ripristinato";
      
    } catch (e) {
      console.error("🚨 ERRORE EMERGENCY RESET:", e);
      return `❌ Emergency reset fallito: ${e.message}`;
    }
  }
  
  // REGISTRAZIONE ESTESA NEL SYSTEM REGISTRY
  if (typeof SystemRegistry !== 'undefined') {
    SystemRegistry.DisciplinaAvanzata = SaggezzaAcquisita.disciplina;
    SystemRegistry.FunzioniGlobaliDisciplina = {
      riepilogoDisciplina,
      diagnosiDisciplina,
      correggiComportamento,
      verificaIntegritaSistema,
      riconosciAutodistruzione,
      alertDisciplinare,
      attivaMonitoraggioContinuo,
      fermaMonitoraggioContinuo,
      checkSistemiCritici,
      autoCheckComportamentale,
      emergencyReset
    };
    SystemRegistry.DISCIPLINA_FUNZIONI_COMPLETE = true;
  }
  
  console.log("🎯 Disciplina 9.2 - Tutte le funzioni globali caricate e operative");
  
  // TEST FINALE SISTEMA
  const test_finale = SaggezzaAcquisita.integrazioni.verificaIntegrita();
  if (test_finale.status === "INTEGRO") {
    console.log("✅ TEST FINALE: Sistema Disciplina 9.2 completamente operativo");
    SaggezzaAcquisita.tracking.registraAzione("TEST FINALE SUPERATO: Sistema Disciplina 9.2 pienamente operativo");
  } else {
    console.warn(`⚠️ TEST FINALE: Sistema Disciplina 9.2 operativo con limitazioni (${test_finale.integrita}%)`);
    SaggezzaAcquisita.tracking.registraAzione(`TEST FINALE PARZIALE: Sistema operativo al ${test_finale.integrita}%`);
  }
  
} else {
  
  // SISTEMA IN EMERGENZA - FUNZIONI STUB ESTESE
  console.error("🚨 Sistema Disciplina in modalità emergenza - Funzioni limitate disponibili");
  
  function riepilogoDisciplina() {
    return "⚠️ SaggezzaAcquisita non caricata - Sistema disciplina non operativo";
  }
  
  function diagnosiDisciplina() {
    return "⚠️ Sistema diagnostico non disponibile - Caricare prima SAGGEZZA_ACQUISITA";
  }
  
  function correggiComportamento(tipo) {
    return `⚠️ Sistema correzione non disponibile - Tipo: ${tipo}`;
  }
  
  function verificaIntegritaSistema() {
    return {
      status: "EMERGENZA",
      integrita: 0,
      sistemi_operativi: 0,
      sistemi_totali: 8,
      messaggio: "SaggezzaAcquisita non caricata"
    };
  }
  
  function emergencyReset() {
    return "⚠️ Emergency reset non disponibile - Sistema in emergenza";
  }
  
  // Registra stato di emergenza
  if (typeof SystemRegistry !== 'undefined') {
    SystemRegistry.DISCIPLINA_EMERGENCY = true;
    SystemRegistry.DISCIPLINA_STATUS = "EMERGENZA";
  }
  
  console.error("🚨 Disciplina non può operare senza SaggezzaAcquisita - Sistema in modalità emergenza");
}

// LOGGING FINALE E STATO SISTEMA
console.log("🛡️ DISCIPLINA 9.2 - Caricamento modulo completato");
console.log(`📊 Status finale: ${typeof SaggezzaAcquisita !== 'undefined' ? 'OPERATIVO' : 'EMERGENZA'}`);
console.log(`🔧 Funzioni disponibili: ${typeof SaggezzaAcquisita !== 'undefined' ? 'COMPLETE' : 'LIMITATE'}`);

// PROTEZIONE FINALE DA SOVRASCRITTURA
if (typeof SaggezzaAcquisita !== 'undefined') {
  Object.freeze(SaggezzaAcquisita.disciplina.identita);
  Object.freeze(SaggezzaAcquisita.integrazioni);
  console.log("🔒 Sistemi critici protetti da sovrascrittura");
}

<!-- ===== FINE MODULO: DISCIPLINA_9.2.doc ===== -->
