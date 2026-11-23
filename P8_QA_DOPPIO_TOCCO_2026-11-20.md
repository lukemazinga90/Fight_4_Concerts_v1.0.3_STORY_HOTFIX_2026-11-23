# Fight 4 Concerts v1.0.2 — Patch doppio tocco nelle scene Campagna

Data: 20 novembre 2026

Base: `Fight_4_Concerts_v1.0.2_QA_VALIDATA_2026-11-20.zip`.

## Modifica

- Nello stato `story`, un singolo tocco/click sul canvas non fa più avanzare le scene.
- Sono richiesti due tocchi vicini (massimo 48 coordinate di gioco di distanza) entro 450 millisecondi, sulla **medesima schermata**. I tocchi multi-finger non sono accettati come doppio tocco.
- Il primo tocco viene resettato ogni volta che la scena cambia, e ogni volta che si entra in una nuova sequenza narrativa.
- Il blocco iniziale di 20 frame su ogni schermata rimane attivo.
- Sulle schermate illustrate e su quelle con grafica nativa ora compare l'indicazione `DOPPIO TOCCO / INVIO`.
- Da tastiera, Invio (o J) continua ad avanzare di una scena, come prima.
- Le schermate dei menu, VS, pausa, mappe e il combattimento non sono interessati dalla modifica.

## Test automatici Chromium

**89/89 superati, nessun errore JavaScript.**

- Tutte le **16 campagne**: tap singolo non avanza; doppio tap avanza; tap singolo sulla scena successiva non avanza; doppio tap completa la sequenza (64 controlli).
- Tocchi tripli ravvicinati: non saltano più di una scena.
- Intervallo oltre 450 ms: non vale come doppio tocco.
- Tocchi lontani: non valgono come doppio tocco.
- Input nei primi 20 frame: nessun salto e nessun accumulo di un tocco per la scena successiva.
- Accessibilità tastiera: Invio continua a funzionare.
- Test browser mobile emulato: touch screen su Guidotti, Luke, Donatella e Lou Reed (12 controlli touch).
- Nessuna eccezione JavaScript nel browser.

Il test è stato effettuato su Chromium desktop e con emulazione touch mobile; rimane opportuno un controllo su iPhone e Android fisici per comportamento di Safari, tocchi rapidi e feedback visivo.

La nuova build mantiene intatti gli sprite, il codice dei combattimenti, i salvataggi e le 16 campagne, salvo il solo meccanismo touch di avanzamento delle scene.
