# QA — Fight 4 Concerts v1.0.1

## Verifiche effettuate

- Sintassi JavaScript verificata con Node.js (`node --check`), nessun errore.
- Confronto SHA-256 dei file PNG della v1.0.0 e v1.0.1: **1379 su 1379 identici**.
- Test offline in Chromium con inlining dei PNG originali (senza rete, senza Netlify): tre viewport (844×390 touch, 667×375 touch, 1280×720 desktop).
- Precaricamento: **24/24 immagini disponibili** (23 ritratti + `C_map`), nessun errore JavaScript nel test.
- Condivisione dell'oggetto ritratto fra selezione e VS verificata; nessun asset ridisegnato.
- Altezza margine inferiore: 72 px invece di 40 px su viewport testata senza safe-area.
- Verificato che il testo HTML e l'archivio mantengono P0–P3, 69 dialoghi, 16 outfit e 7 nemici.

## Limiti

- Il sito Netlify pubblico è stato letto tramite accesso web, ma non è stato possibile eseguire un test completo dell'applicazione ospitata nel browser da remoto.
- Il rendering offline è stato ottenuto incorporando temporaneamente i PNG nella pagina di prova: non misura la latenza Internet.
- Non è stato eseguito un collaudo su iPhone reale o su tutte le varianti di notch / UI di Netlify.
- La schermata di avviso di risorse mancanti durante il rendering offline è attesa: il mock non includeva i frame e gli stage del sito; non è indice di errori nella build da pubblicare.
