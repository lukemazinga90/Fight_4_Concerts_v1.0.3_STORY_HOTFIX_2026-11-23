# QA — Fight 4 Concerts v1.0.2 (19 novembre 2026)

## Ambito

Patch cumulativa v1.0.1 → v1.0.2: protezione zoom accidentale sulle superfici di gioco. Combattimento, animazioni, dialoghi, stage e immagini restano invariati. Conserva il precaricamento immagini e il rialzo pulsanti della patch precedente.

## Controlli completati

- Sintassi JS valida (`node --check`).
- Test browser headless Chromium (tre viewport: mobile 844×390, 667×375, desktop 1280×720), con 24 PNG reali incorporati nel documento solo per il test offline.
- 24/24 risorse di presentazione precaricate; pulsanti ancora a 72 px dal fondo sui viewport senza safe-area.
- Eventi `gesturestart`, `gesturechange`, `gestureend`, `touchmove` e `dblclick` bloccati sulle superfici di gioco, non sul pannello diagnostico.
- Doppio tap: seconda chiusura touch cancellata, prima non cancellata; i Pointer Events restano funzionanti.
- Due tap reali rapidi con controllo PUGNO: input registrato.
- Multi-touch reale simulato dal browser: joystick a destra + tasto PUGNO contemporaneamente registrati; rilasci puliti.
- Pinch gesture sintetizzata dal browser Chromium: `visualViewport.scale` rimasta a 1, scrollX/scrollY rimasti 0.
- Nessun errore JS / nessuna richiesta di rete fallita nello smoke test offline.
- Confronto SHA-256: **1379/1379 PNG identici alla v1.0.1**.
- Gli unici file preesistenti modificati sono `index.html`, `VERSION.json`, `CHANGELOG.md`, `RELEASE_NOTES.md`. Nuovo QA aggiunto.

## Limiti

- I test sono su Chromium simulato, non su Safari iOS o Android reale: non garantiscono controllo dei gesti proprietari dell'OS o gesture di accessibilità.
- Il sistema operativo e l'interfaccia nativa del browser/Netlify possono mantenere le proprie gesture vicino ai bordi.
- Per evitare deploy multipli, la build v1.0.2 include anche tutte le correzioni della v1.0.1; caricarla direttamente come ZIP completo.
