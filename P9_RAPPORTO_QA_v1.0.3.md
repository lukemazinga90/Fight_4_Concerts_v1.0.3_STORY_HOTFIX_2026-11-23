# Fight 4 Concerts v1.0.3 — rapporto QA

**Data:** 23 novembre 2026  
**Build di origine:** Fight_4_Concerts_v1.0.2_DOPPIO_TOCCO_QA_2026-11-20.zip

## Prove eseguite

- **JavaScript:** sintassi verificata con Node.js `--check`.
- **Logica nel Chromium headless:** 783 scenari, 5.069 asserzioni, 0 errori / asserzioni fallite.
- **Facile e Normale:** 512 sconfitte di campagna simulate (16 personaggi × 2 difficoltà × 4 tappe di prova × 4 tentativi); sempre disponibile retry dello stesso incontro, senza avanzamento o penalizzazione.
- **Difficile:** 192 sconfitte simulate (16 personaggi × 4 tappe × 3 vite); conteggio 3→2→1→0, salvataggi al KO, azzeramento della campagna alla terza sconfitta e conservazione dei dati di sblocco.
- **Vittorie e premi:** 48 vittorie finali di campagna, 6 controlli degli sblocchi alla settima battaglia per Luke e Rettori. Conservati i requisiti dei costumi Normale/Difficile.
- **Salvataggi:** tre prove di retrocompatibilità: campagna preesistente senza `hardLives`, vita residua memorizzata in 1.0.3, e valore zero ripristinato a inizio campagna. Nessuna perdita degli sblocchi.
- **Durata della vittoria:** verificati 239 frame di attesa, 4+ secondi senza transizione automatica, primo tocco ignorato, doppio tocco valido e terzo tocco immediato non in grado di saltare la schermata risultati.
- **Input effettivi:** testato pointerdown con mouse, touchscreen Chromium emulato e tastiera Invio. Retry e Game Over testati con eventi touch reali emulati.
- **UI:** renderizzate la selezione di Guidotti e Vitto C con immagini originali, il rivale senza descrizione, la mappa HARD, le schermate Retry, Game Over, vittoria e risultati. Risorse servite al browser durante il controllo. Nessun errore JavaScript.
- **Modalità VS, Festival Sprint e Ultimo Pogo:** progressione post-partita ricontrollata, senza modifiche alle regole.

## Integrità degli asset

L'archivio eredita inalterati tutti i file originali 1.0.2, tranne `index.html`; aggiunti soltanto i due documenti di rilascio/QA. Il controllo hash degli asset originali viene eseguito anche sul pacchetto finale.

## Limiti del QA

Le battaglie sono state indotte nel motore per verificare KO e progressione, non giocate tutte manualmente. I test sono stati eseguiti nel browser headless con asset serviti da un host di prova intercettato, **non sul sito pubblico Netlify**. Mancano ancora una prova su iPhone fisico e una su Android fisico prima di distribuire la nuova patch su larga scala.
