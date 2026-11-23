# Changelog — sviluppo

## v1.0.1 — IN PREPARAZIONE (NON PUBBLICATA)

Patch unica cumulativa delle correzioni precedentemente etichettate localmente 1.0.1 e 1.0.2.
- Pulsanti d’attacco alzati di 32 px.
- Precaricamento di 23 ritratti VS e della mappa campagna.
- Protezione touch contro doppio tap, pinch-to-zoom, trascinamento/overscroll involontario, preservando joystick + attacco.
- Audit completato su dimensioni, ridondanze e possibili ottimizzazioni.
- Pulizia asset obsoleti: rimossi 14 vecchi ritratti `assets/P_*.png` (247.087 byte), sostituito il riferimento diagnostico con `VP_Guidotti.png`; sprite, ritratti nuovi e gameplay invariati.
- Le altre ottimizzazioni (WebP, atlas, refactoring, alias dei frame duplicati) restano sospese.
- Collaudo su dispositivi mobili reali da eseguire prima di chiudere la release.

## v1.0.0 — 19 novembre 2026
Prima release di riferimento con P0, P1, P2, P3.

## Versioni successive pianificate
P5 — discussione campagna e altre modalità prima di P4 Fatality; P6 — musica. Nessuna nuova build ZIP generata.

### Modalità extra (staging 19/11/2026)
- Festival Sprint: tre incontri con stage e avversari casuali, inclusi giocatori CPU.
- Ultimo Pogo: 14 avversari unici in ordine casuale, HP conservati e un round per match.
- Soundcheck: scelta tra 15 bersagli e stage, manichino immobile, invulnerabile al KO, contatori colpi/danni.
- Menu pausa: nuova opzione COMANDI, con ritorno al combattimento sospeso.
- Campagna, salvataggi e sblocchi rimasti invariati; nessun asset aggiunto.
- Nessuno ZIP prodotto e nessun deploy effettuato.

## P5 (staging) — Percorsi Guidotti / Vasco Brondi — 19 novembre 2026
- Due campagne speculari da otto combattimenti, Rival Battle alla tappa 7, Max Pezzali alla tappa 8.
- Prologo e scene testuali, biglietto con sei indizi e seconda lettura, messaggio anonimo, finale Lunapop e finale speculare.
- Vasco Brondi giocabile dopo completamento Guidotti; 56 nuovi frame, ritratto, silhouette e ambientazione narrativa.
- Selezione in una delle otto finestre tramite B/touch, senza outfit ALT; disponibile nelle altre modalita' quando sbloccato.
- Nuovo schema di salvataggio 2 con reset unico concordato.
- QA automatico Chromium superato, test su telefono reale ancora necessario.
- Nessun nuovo ZIP, nessun deploy Netlify.

### P5 — Giannini / Kurt Cobain: campagna speculare (staging, non pubblicata)
- Setlist progressiva: Johnny Marr, Jack White, Robert Smith, Joey Santiago, Jerry Cantrell, Alex Turner. Reveal Kurt Cobain alla tappa 7.
- Dialoghi Rival Battle e gag di Giannini / Dave Grohl; finale Giannini a Tokyo e finale Kurt "Rest in Rock".
- Sei fondali 16-bit di scenetta costruiti dalla tavola approvata, con testi UI separati.
- Sprite Kurt e Vasco ripristinati nelle cartelle frames con 56 PNG per personaggio; asset mancanti di campagna reintegrati.
- Verifica statica: zero riferimenti PNG mancanti, nessun ZIP Netlify.

### P5 — Vitto C / Filippo Conti (staging, non pubblicato)
- Due tour speculari di otto scontri, tappa 7 Rival Battle, tappa 8 Max.
- Poster festival incrementale fino alla dicitura ambigua CONTI; riconoscimento padre/figlia e finale Electro Symphonic.
- Scena a meta' campagna col vocale di Filippo, risposta ironica di Vitto C.
- Filippo sbloccabile sulla stessa casella di Vittoria; 56 frame, ritratto, 3 intro, nessun ALT.
- Fondali 16-bit e testi in Canvas per coerenza con gli sprite originali.
- QA browser su pagina con risorse incorporate: JS senza errori, 56 frame caricati, sblocco e campagna speculare verificati.
- Da verificare su smartphone reale e in combattimenti manuali continuativi. Non pubblicato, nessun ZIP.

### P5 — Vitto P / Faccianuvola (staging; nessun deploy)
- Due campagne Ship Quest speculari: 8 incontri, rivale alla settima tappa, Max all ottava.
- Misuratore progressivo con sei indizi, story a meta campagna e due finali.
- Faccianuvola sbloccabile sulla quarta casella dopo completamento di Vitto P; accessibile nelle modalita roster.
- 56 PNG trasparenti e ritratto, animazioni e speciale NUVOLA D AMORE.
- QA browser/sintassi/sblocco positivo; restano alcune pose duplicate da perfezionare e QA su iPhone.
- Asset pack ZIP separato dal gioco, non e una release Netlify.

### P5 Vitto P / Faccianuvola — scenette 16-bit approvate (staging)
- Integrate cinque immagini narrative (prologo, mid, indizi, Rival Battle, finale) nella campagna di Vitto P.
- Sottotitoli dinamici sul pannello inferiore, con navigazione e progresso invariati.
- Immagini visualizzate solo nei corretti stati narrativi; spoiler nascosti fino alla sesta vittoria.
- Corrette due discrepanze visive del concept (74% al quarto incontro, conteggio 6/6 indizi).
- Sintassi JS e 5 schermate con dialoghi reali controllate in Chromium isolato, nessun errore JS.
- Nessun nuovo ZIP Netlify. Sprite/mosse invariati.

### Asset Lore / De André — preparazione P5
- Aggiunti 56 PNG di FabrizioDeAndre (`frames/FabrizioDeAndre/000–055.png`) e 16 tavole grafiche `assets/C_lore_*.png`; non ancora utilizzati dal motore.
- QA sprite aperta: differenze di pose per salto/KO e alcuni bordi di celle.
- Nessun nuovo pacchetto Netlify, nessun reset salvataggi.

### P5 — Lore/De André + Frillo/Piero Pelù (19/11/2026, staging, NO NETLIFY)
- Integrate due coppie di campagne speculari con 8 tappe (rivale alla 7ª, Max alla 8ª), prologo/mid-scene/finali e UI di progresso dedicate.
- Lore: sei riprese con timeline e segreto De André; proiezione speculare; sblocco De André alla vittoria finale di Lore.
- Frillo: viaggio fino a Tbilisi, itinerario a 6 tappe, notifiche di Piero, rival battle e finale Reykjavík. Speculare Piero con Frillo rivale.
- 56 frame De André e 56 Piero Pelù in formato/ancoraggi compatibili rispettivamente con Lore e Frillo, nessuna animazione ALT.
- Piero: 36 celle rimappate e 20 poste da 18 disegni correttivi; nuova sequenza speciale 051–055 e corsa più dinamica.
- Ritratti, 3 linee intro e speciali configurati per entrambi i nuovi rivali.
- Roster a 8 caselle invariato, sblocco su tile 5° (Lore) e 6° (Frillo); altre modalità condividono unlock roster.
- QA browser: 15 scene, 4 combattimenti rival/special, zero pageerror; test di migrazione del vecchio salvataggio con storage simulato superato.
- BLOCCO DEPLOY PREESISTENTE: lo staging locale manca ancora di 185 PNG delle coppie precedenti. Restano da ripristinare i file esatti approvati prima dell'eventuale ZIP Netlify, senza rigenerazioni arbitrarie.
- Nessun ZIP del gioco, nessun deploy.


## 2026-11-20 — Consolidamento P5, sei coppie nella v1.0.1 locale
- Ripristinati da archivio completo tutti gli asset originali mancanti, senza sovrascrivere `index.html` P5.
- Ripristinati 336 PNG (56×6) dei rivali Vasco, Kurt, Filippo, Faccianuvola, De André e Piero; geometria del set Vasco/Kurt riagganciata ai frame dei protagonisti.
- Recuperati ritratti, scene 16-bit, oggetti progressivi e 7 tavole timeline Lore. Manifest: `P5_ASSET_MANIFEST.json`.
- Test browser 36 scene narrative, 6 combattimenti, 0 errori JS e 0 richieste fallite; validazione 1760 PNG.
- Nessuna modifica ai salvataggi e nessun deploy/ZIP Netlify. Alcuni asset ricostruiti/restaurati richiedono revisione artistica e collaudo smartphone prima della release.

### P5 Rettori/Donatella — proposta e asset da validare (20/11/2026)
- Preparati storyboard testuali delle due campagne (`P5_Rettori_Donatella_STORY.md`), con inserimento di sospetti progressivi, mid-scene e dialogo finale autorizzato.
- Preparata una variante sprite Mattia con la special `OCCHIO DEL DOMINIO` sui SOLI frame 051-055. I frame 000-050 sono invariati a livello pixel e la verifica è registrata in `asset_proposte/Rettori_MattiaSpecial/QA_checksums.json`.
- **Non integrati ancora nel motore di gioco**, in attesa di approvazione delle due scalette e controllo del taglio originale del foglio (alcune celle non speciali contengono parti della riga precedente nella sorgente). Non effettuato deploy.

# Fight 4 Concerts v1.0.1 — Rettori / Donatella — 2026-11-20

INTEGRATO NELLA CARTELLA LOCALE, SENZA BUILD O DEPLOY NETLIFY.

- Rettori: 8 incontri (6 classici + Mattia + Max), progressione offerta misteriosa in sei indizi, sospetto anticipato, mid-scene sullo spritz, riflesso Occhio nel vetro, dialoghi di Mattia: "Io ti conosco, Rettori" e citazione LOTR; ispirazione di Donatella riprodotta letteralmente.
- Donatella: 8 incontri (6 classici + Max + Mattia), sei clausole del Contratto, trama e finale distinti.
- Ricompensa: Donatella sbloccata automaticamente dopo la settima vittoria di Rettori, nella stessa casella #8, senza ALT. Mattia non entra nel roster né nella selezione degli altri modi.
- Sprite Donatella: 56 PNG nel corretto ordine numerico con contorni e dimensioni esattamente ricavati dai 56 sprite canonici di Rettori; nuova palette platino/nero/oro e speciale magenta. L'artwork 56-celle generato in precedenza è conservato in asset_proposte, ma non è stato usato direttamente perché le pose risultavano non congruenti con il moveset Honda. Questo è un set tecnico con pose esatte, non un restyling approvato definitivo.
- Mattia: 56 sprite recuperati dal pacchetto approvato; solo 051–055 con Occhio del Dominio. I file 000–050 sono byte per byte identici al pacchetto di origine.
- P3: tre frasi di Mattia e Donatella; intro esistenti non skippabili preservate.
- Test browser con asset intercettati (senza HTTP pubblico): roster 15; P3, 7 scene, sblocco, due arene e speciale caricati; zero errori JS, zero HTTP mancanti. Test smartphone e completamento manuale di tutte le battaglie ancora necessari.
- File generati dal modello nella cartella di staging non modificano nessun file su Netlify.
- Alcune immagini dei precedenti rivali sono state ripristinate dalle sorgenti approvate disponibili e potrebbero differire dalle ultime rifiniture originali; fare QA visiva prima del deploy definitivo.

### Ripartenza QA Donatella (20/11/2026, secondo passaggio)
- Rivisto il blocco esistente anziché rigenerare o ricostruire le campagne.
- Rifiniti tutti i 56 sprite di Donatella: palette più vicina al design platino/nero/oro, alpha e ancoraggi identici ai frame originali di Rettori. Conservato backup fuori dalla cartella di staging.
- Validati 56/56 sprite Mattia identici al pacchetto approvato con speciale Occhio del Dominio 051-055.
- Browser Chromium: 15 giocabili, Mattia boss non giocabile, sblocco Donatella dopo vittoria 7, due arene e speciale, 0 errori JS/HTTP.
- **Nota aperta**: Donatella è un recolor tecnico con la geometria di Rettori, incluso l'abito a gonna; il design del costume non è ancora una replica grafica perfetta dell'artwork nero/oro approvato.
- Nessun nuovo deploy e nessuno ZIP del gioco.

### 2026-11-20 — Procedura definitiva sprite 56 frame
- Aggiunto `PROCEDURA_SPRITE_56_FRAME.txt` con sequenza nominale V17 ricostruita da `FR/frameFor`, eccezioni `ATTACK_FRAME_MAP`, workflow per rivali/outfit, controlli anatomici, segmentazione, ancoraggi e QA 56/56. Nessuna modifica a gameplay o PNG.


## v1.0.1 — Consolidamento Rettori / Donatella (20/11/2026)
- Sostituiti i 56 frame di Donatella con lo **stile nero/oro/platino approvato** mediante mappatura di 58 silhouette originali su 56 pose Rettori; 3 riutilizzi documentati.
- Salvato `MAPPATURA_DONATELLA_56_FRAME.txt`; estesa `PROCEDURA_SPRITE_56_FRAME.txt` (appendice 1.1).
- Aggiornato il riflesso dell'Occhio di Sgreccia nel vetro dopo il sesto indizio; corretto il prologo di Donatella per non rivelare il boss in anticipo.
- Confermate le due campagne di 8 incontri, sblocco di Donatella dopo il 7° incontro di Rettori, Mattia boss non selezionabile; conservata la speciale 051–055 originale.
- Browser QA locale: 56/56 Donatella e Mattia, scena e match renderizzati, 0 errori JS; persistenza e controlli touch da collaudare su telefono reale.
- Nessun ZIP/Deploy Netlify.

### 2026-11-20 - QA campagne e modalita (nessuna modifica di gameplay)
- 96/96 controlli logici, 15 campagne/119 incontri simulati, 9 combattimenti caricati; test Festival Sprint, Ultimo Pogo, Soundcheck, salvataggi, menu Comandi.
- Identificati due difetti grafici pre-release: 6 PNG Giannini/Cobain con errore di deploy incorporato; sprite Rettori diverso dalla reference approvata. Vedi REPORT_QA_CAMPAGNE_E_MODALITA_2026-11-20.txt.


## 2026-11-20 — Pass scala e ancoraggi roster (checkpoint locale v1.0.1)
- Guidotti fissato come riferimento: canvas logico 384x216, ground Y=186, h visiva neutra 93.
- Piero Pelù: scala .5768 → .620; stessa sequenza Frillo, asset invariati.
- Mattia Sgreccia: scala .68148 → .625, anchorY 146 → 154; speciale Occhio preservata.
- Vasco Brondi: scala .58125 → .64 e ancoraggi mirati sulle pose a terra.
- Donatella Rettore: scala .58974 → .615 per altezza comparabile a Rettori.
- frameFor idle: da 4 a 3 pose (000–002), impedisce che 003/corsa appaia in idle.
- Ripristinati asset e dialoghi mancanti dalla copia di checkpoint; nessuna nuova modifica ai PNG.
- QA: 31 set x 56 PNG, 310 pose chiave, 589/589 test di regressione simulata; nessun JS error/404.
- Documentazione STANDARD_SCALA_BASELINE_ROSTER.txt e report QA aggiunti.
- Ancora aperto: 6 immagini Giannini/Cobain con errore incorporato e costume Rettori discordante.
- Nessun deploy Netlify; richiede ancora prova reale mobile e revisione artistica.


## 2026-11-20 — Procedura e audit Mattia/Rettori
- aggiunto `MAPPATURA_RETTORI_56_VISIVA.txt` con la sequenza visiva 000-055 da usare per Rettori, DonatellaRettore e MattiaSgreccia
- aggiunto `REPORT_MATTIA_vs_RETTORI_56_FRAME.txt` con confronto dell'ultimo foglio Mattia vs Rettori
- aggiunta estrazione di lavoro `working_mattia_latest_sheet_extracted/000..055.png`
- aggiornato `PROCEDURA_SPRITE_56_FRAME.txt` con rimando esplicito ai file operativi della famiglia Rettori


## 2026-11-20 — Rigenerazione Mattia + check immagini campagne
- rigenerato l'intero set `frames/MattiaSgreccia/000..055.png` da un nuovo foglio coerente con la procedura Rettori
- salvato backup in `frames/MattiaSgreccia_backup_pre_regen_2026-11-20/`
- generata anteprima QA `../F4C_Mattia_Rigenerato_QA/Mattia_56_contact.png`
- eseguito controllo immagini e frame delle campagne, salvato in `CHECK_IMMAGINI_CAMPAGNE_2026-11-20.txt`

## 2026-11-20 — Mattia corretto e reintegrato
- 56 PNG puliti, nuova scala e baseline, speciale Occhio del Dominio ricomposta.
- Due transizioni ricostruite da pose equivalenti per eliminare sprite troncati.
- Nessuna modifica alle altre campagne o alle modalità di gioco.


## 20 novembre 2026 — Speciale Mattia: ripristino dei 4 frame approvati
- Sostituiti esclusivamente `frames/MattiaSgreccia/051.png` – `054.png` con i 4 disegni singoli approvati dall’utente (braccio anatomicamente corretto, progressione Occhio del Dominio).
- Nessun cambio agli sprite 000–050 e 055, nessuna modifica al codice, alle altre campagne o alle modalità.
- Immagini finali trasparenti 230×190 px, piedi sulla linea del set esistente; copia delle vecchie pose conservata fuori dalla cartella di gioco.
- La rigenerazione completa dell'ultimo spritesheet NON viene utilizzata.


## 2026-11-20 — Patch grafica Rettori e Giannini/Cobain
- Sostituiti 56 PNG Rettori con outfit ufficiale a righe e shorts, estratto dal foglio approvato.
- Sostituite le 6 scene Giannini/Cobain che contenevano una schermata di errore, senza modificare dialoghi o progressione.
- Backup disponibili fuori dalla cartella di release; nessun intervento sul codice o sulla speciale di Mattia.
