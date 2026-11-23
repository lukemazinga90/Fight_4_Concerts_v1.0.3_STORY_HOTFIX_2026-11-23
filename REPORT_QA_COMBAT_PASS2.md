# Fight 4 Concerts — QA Combat Pass 2 (P3.2)

## Ambito
Partenza da `Fight_4_Concerts_Combat_Fix_Netlify.zip` (P3.1). Tutti i 1.288 PNG e le 28 risorse grafiche sono conservati byte per byte. Modifiche soltanto a `index.html`.

## Controlli
- Sintassi JavaScript: `node --check`, superato.
- Browser Chromium emulato, risorse locali servite tramite intercettazione degli URL statici (`assets/`, `frames/`): menu e combattimento renderizzati, zero errori JS.
- Quattro pulsanti visibili; con evento pointer reale il tasto `PARA` resta attivo fino al rilascio.
- `GIÙ + PUGNO` produce pugno basso. Guardia alta e guardia bassa bloccano colpi della categoria corretta.
- Un colpo connesso può concatenare il secondo e il terzo; quarto cancellamento impedito. Nessuna combo autorizzata su colpo parato.
- 672 round simulati: 8 giocabili × 7 avversari × 3 difficoltà × 4 script giocatore. **0 stati numerici invalidi**.
- Gli script dei bot sono semplici e in alcuni casi reagiscono perfettamente alle mosse; i tassi di vittoria NON misurano la difficoltà per un umano.

## Cambiamenti al gameplay
- Animazioni d'attacco: pugni 20–21 frame, calci 27–29, speciale 43, con recupero aggiuntivo.
- Movimento ridotto al 78% del moltiplicatore precedente al Combat Pass (anziché al 90%).
- Rinculo sui colpi e parate, hitstun 15 frame, combo massimo 3 colpi con scaling dei danni.
- Anti-spam: recupero aggiuntivo morbido per lo stesso colpo ripetuto in rapida successione.
- IA: identificazione delle mosse ripetute, finestra di reazione più leggibile, possibilità di punire la recovery, passi indietro non bloccati automaticamente.
- Quattro azioni touch. La direzione GIÙ determina la variante bassa di pugni, calci e parata. Comandi avanzati tastiera invariati.
- Round da 75 secondi.

## Criticità aperte
1. Collaudo reale Safari iOS e Chrome Android dopo il deploy Netlify.
2. Bilanciamento con giocatori umani, inclusa sensazione di reattività dello schermo touch.
3. Verifica estetica delle pose e collisioni per ogni outfit; il pass non modifica i PNG.
4. Gli script automatici possono sovra- o sottostimare la difficoltà reale dell'IA.

## Prossima fase
Una breve sessione su telefono con Luke a Normale, alternando attacco, guardia, basso e combo 2-3 colpi; poi ritoccare i tempi effettivi in base al feedback.
