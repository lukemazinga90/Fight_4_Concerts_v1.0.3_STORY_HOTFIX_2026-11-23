# Fight 4 Concerts v1.0.2 — Campagne Luke e Lou Reed

Data: 20 novembre 2026  
Base: `Fight_4_Concerts_v1.0.1_FIX_RETTORI_GIANNINI_COBAIN_2026-11-20(1).zip`  
Stato: build integrata locale, non pubblicata online.

## Cambiamenti

- Luke: campagna **Walk on the Wild Side** trasformata da percorso generico a **8 incontri** (6 avversari base, Lou Reed, Max Pezzali).
- Lou Reed: nuovo combattente selezionabile e campagna speculare **No More Heroes**, anch'essa da **8 incontri** (6 avversari base, Luke, Max Pezzali).
- **18 schermate narrative per campagna (36 in totale)**. Si usano 8 illustrazioni PNG 16:9, 384×216 px, riutilizzate in punti coerenti. I titoli e sottotitoli sono disegnati dal motore.
- Lou Reed: 56 PNG numerati 000–055, RGBA realmente trasparenti, ritagliati dal foglio visuale approvato; geometria di ciascun file e profilo rendering abbinati a Luke. Le sue animazioni e `ATTACK_FRAME_MAP` seguono gli **indici effettivi** di Luke, senza usare una tabella generica.
- Ritratto Lou Reed per selezione, HUD, schermata VS e Soundcheck; stat, speciale `WILD SIDE`, tre battute introduttive (anche nel file dialoghi di backup).
- Lou Reed si **sblocca dopo il settimo scontro vinto dalla campagna Luke** e resta sbloccato nel salvataggio. La sua campagna speculare compare nella casella Luke premendo B / toccando il controllo rivale.
- Conservati 56 frame originali di Luke e Luke_ALT e tutti i personaggi preesistenti.
- Nessuna modifica al sistema di combattimento condiviso, né alle 14 altre campagne; aggiornato numero versione cache URL asset per evitare cache vecchia del browser.

## QA eseguito

- **54/54** controlli funzionali: avvio, roster, rotte, dialoghi, asset, 36 scene nell'ordine giusto, sblocco e persistenza simulata, VS, controlli base mobile, 14 campagne preesistenti; nessun errore JS/HTTP rilevato.
- **15/15** controlli ulteriori: integrità dei file originali, 56 PNG Lou RGBA e dimensioni abbinate ai 56 PNG Luke, illustrazioni 384×216, tutti i riferimenti asset, **16 campagne simulate completamente (128 tappe)** con conteggio schermate identico al baseline, render di mosse, pausa/ripresa, controlli landscape/portrait in emulazione touch; nessun errore JS.
- Il confronto byte-a-byte con la release precedente riscontra modificati **solo `index.html` e `dialoghi_p3.json`** tra tutti i file preesistenti. I nuovi file sono aggiunte.
- Verificati manualmente i fogli contatti visuali e screenshot gameplay di Lou; nessun clipping evidente o sprite mancante nei campioni ispezionati.

### Limiti espliciti dei test

- La prova delle 128 tappe **simula gli esiti degli incontri attraverso il motore**, non costituisce 128 vittorie giocate con input umano né una prova della difficoltà/bilanciamento di ogni match.
- Test di gioco e UI in Chromium desktop e touch emulato. **Non testati direttamente su iPhone/Android reali o su Netlify**.
- I frame sono stati ispezionati visivamente sul foglio QA e campionati in partita; non esiste un collaudo percettivo automatico di tutte le transizioni a 60 fps e dei singoli pixel.

## Avvio e deploy

Estrarre **l'intero archivio** mantenendo `index.html`, `frames/`, `assets/` e `dialoghi_p3.json` allo stesso livello. Pubblicare la cartella completa (non solo `index.html`). I salvataggi locali delle versioni precedenti vengono letti e la nuova chiave `lou` viene aggiunta senza annullare gli sblocchi esistenti.

## Verifica suggerita su dispositivo reale

Avviare la campagna Luke, avanzare al settimo incontro, vincere contro Lou, confermare che la casella Luke mostra **Lou Reed (B)**, selezionare Lou, provare i quattro attacchi e la speciale, e proseguire sino a Max Pezzali. Ripetere infine la battaglia Luke/Lou nella campagna speculare. 
