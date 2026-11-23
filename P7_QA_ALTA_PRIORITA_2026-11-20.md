# Fight 4 Concerts v1.0.2 — QA ad alta priorità

Data: 20 novembre 2026  
Versione sorgente verificata: `Fight_4_Concerts_v1.0.2_LUKE_LOU_COMPLETE_2026-11-20.zip`.  
Versione preparata per distribuzione: `Fight_4_Concerts_v1.0.2_QA_VALIDATA_2026-11-20.zip`.

## Risultati

| Prova | Copertura | Esito |
|---|---|---|
| Stress del combattimento | **500 scontri completi** nel motore, 16 combattenti, 3 difficoltà, confronti Luke/Lou, IA attiva | **500/500** terminati |
| Sconfitte e retry | 16 campagne × 3 checkpoint (incontri 1, 7, 8) | **48/48** corretti |
| Pausa, uscita e ripresa | 16 campagne × 3 checkpoint | **48/48** corretti |
| Migrazione salvataggi da **v1.0.0** | 6 salvataggi generati dal codice della release originale `v1.0.0_P0-P3_RELEASE.zip` | **6/6** corretti |
| Sblocco Lou | Sconfitta al 7°, vittoria al 7°, sconfitta all'8°, ripresa e persistenza | **Superato** |
| Errori script / indici animazione | Monitoraggio durante i 500 scontri | **0** |

### Stress test — metodologia

Automazione Chromium headless. Ogni scontro parte dalla funzione originale `startFight` (statistiche complete, posizione iniziale ordinaria, HP pieni). Il bot test invia input nel circuito `held`/`pend`/`queueAttack`; il motore originale `update()` gestisce camminata, colpi, collisioni, schivate, IA, danni, round, timeout, KO e vittoria/sconfitta. Per accelerare il test vengono saltate le sole sequenze VS/intro, non la simulazione degli scontri.

**Statistiche registrate:**

- 500 scontri conclusi: 331 vittorie, 169 sconfitte del bot.
- 1.776.517 frame logici di aggiornamento.
- 47.062 input d'attacco tentati.
- 11.204 decrementi HP registrati nel tracciamento, indicativi di colpi efficaci (non metriche di bilanciamento).
- 1.378 avvii della mossa speciale.
- Difficoltà: 167 Facile, 167 Normale, 166 Hard.
- Tutti i 16 combattenti coinvolti come P1, compresi Lou Reed e Luke; controlli ciclici degli indici sprite 000–055.
- 0 combattimenti non terminati, 0 indici fuori range, 0 eccezioni JavaScript.

### Sconfitte / retry

Per ogni campagna: caricato checkpoint, avviato il relativo match, pilotati due KO del giocatore passando per la logica originale `update` dei round, confermata la schermata di sconfitta, tornati al titolo, ripreso il salvataggio e ritentato lo stesso match. **48/48 corretti:** progressione non incrementata e sblocchi non assegnati erroneamente. I KO sono indotti nel test per verificare le transizioni, non ottenuti ogni volta con una partita umana completa.

### Pausa / uscita

Per tutte le 16 campagne e tre checkpoint, dalla fase di combattimento si è aperta la pausa, scelta l'uscita al titolo e ripreso il salvataggio. **48/48 corretti**: stesso personaggio, stesso step.

### Compatibilità vera v1.0.0 → v1.0.2

Recuperato il file originale `Fight_4_Concerts_v1.0.0_P0-P3_RELEASE.zip`; caricata la sua `index.html` e generati sei esempi con la funzione originale `saveRun`, preservando anche `f4c_records`. Verificati: Guidotti a metà campagna, Luke a metà, Luke vecchia campagna completata (step 7), Rettori a metà, Rettori vecchia campagna completata e inizio nuova campagna. **6/6** salvataggi riconosciuti e ripresi dalla nuova build. Sblocchi precedenti e record mantenuti; i nuovi flag introdotti sono inizializzati a `false`.

Nota: il salvataggio di Luke nella vecchia campagna completata riprende dallo step 7 nella nuova campagna a otto scontri, quindi permette di giocare il nuovo ultimo combattimento. Questo comportamento è coerente con l'espansione, non cancella il salvataggio.

### Sblocco Lou Reed

Sconfitta contro Lou allo scontro 7 → Lou resta bloccato, step invariato. Vittoria contro Lou allo scontro 7 → sblocco immediato memorizzato, rivale selezionabile. Sconfitta contro Max allo scontro 8 → sblocco Lou conservato, step 7 ritentabile.

## Correzione effettuata dopo i test

Unicamente il titolo HTML della scheda browser, da `Fight 4 Concerts — v1.0.1` a `Fight 4 Concerts — v1.0.2`. Nessuna modifica al codice JavaScript, al gameplay o agli sprite. Creato nuovo ZIP QA con questo rapporto aggiunto.

## Limiti e decisione di rilascio

**Esito: QA desktop automatico superato, nessun bug bloccante rilevato.** I test sono stati svolti in Chromium headless con input sintetici, non con persone su dispositivi fisici. Non sostituiscono un controllo su Safari/iPhone, Android, prestazioni reali, audio, touch o rete di hosting. Si consiglia una sessione manuale su smartphone prima di pubblicare.

Dati grezzi disponibili esternamente alla build in `QA_HIGH_STRESS_00..04.json`, `QA_HIGH_STATE.json` e `QA_HIGH_PAUSE.json`.
