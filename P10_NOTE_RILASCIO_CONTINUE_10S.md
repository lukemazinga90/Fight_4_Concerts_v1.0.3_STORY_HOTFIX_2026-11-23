# Fight 4 Concerts — v1.0.3 (countdown arcade da 10 secondi)

Aggiornamento incrementale della release v1.0.3 del 23 novembre 2026.

## Nuovo comportamento alla sconfitta in Campagna

- Dopo la sconfitta, 1,5 secondi di annuncio del KO e comparsa automatica della schermata CONTINUA? con conto alla rovescia da 10 a 0.
- Facile / Normale: scegliere RIPROVA LO STESSO INCONTRO con un tocco o Invio. Nessun limite ai retry.
- Difficile: mostra VITE RIMASTE 2/3, 1/3 o 0/3. Una sconfitta consuma una vita; a 0 vite il pulsante avvia una nuova campagna dalla tappa 1.
- Il giocatore può selezionare TORNA AL MENU, oppure premere Esc. Dopo 10 secondi senza scelta, ritorno automatico al menu principale.
- Timer basato sul tempo reale (performance.now), non sui frame di simulazione. Se l'app viene messa in background e ripresa, il tempo trascorso conta.
- Le vite vengono salvate al KO come nella 1.0.3 precedente. In caso di game over, il nuovo tour con tre vite viene salvato al KO.
- Le schermate di vittoria rimangono almeno 4 secondi con avanzamento manuale; le altre modalità restano invariate.

## Invariato

Il gioco rimane v1.0.3: sprite, illustrazioni, musica, dialoghi, combattimento, menu di selezione, sblocchi, salvataggi precedenti e modalità extra non sono stati cambiati.

## Pubblicazione

Pubblicare il contenuto dello ZIP mantenendo index.html, assets/, frames/ e dialoghi_p3.json nella stessa cartella. L'aggiornamento sullo stesso dominio conserva i progressi già salvati nel browser.
