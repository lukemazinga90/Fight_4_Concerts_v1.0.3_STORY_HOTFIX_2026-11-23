# QA — Fight 4 Concerts P1/P2

**Build:** 2026-11-19 (Combat Pass 2 P3.2 + P1 + P2).

## Verifiche eseguite
- `node --check` sul JavaScript integrato: superato.
- Browser Chromium mediante HTML iniettato e asset PNG forniti localmente: nessuna eccezione JS e nessuna richiesta immagine fallita.
- 63 asset nuovi (23 portrait + 36 stati prodotto + 3 stati stand + 1 sfondo) caricabili in browser, nessuno mancante.
- Capturing visivo di selezione personaggi, versus normale/ALT, HUD combattimento, bonus stage integro/danneggiato, risultato stage.
- Risultato bonus: 12 oggetti registrati, punteggio e ricompensa aggiornati; il sistema di salvataggio preesistente non è stato sostituito.
- Il foglio portrait concept errato non è stato usato: tutti i nuovi ritratti derivano dai veri sprite 000 dei relativi 23 set, compresi i costumi alternativi.

## Elementi da verificare sul dispositivo reale
1. Leggibilità barra vita e special a schermo piccolo.
2. Rendimento/fps di particelle e sprite del bonus stage su smartphone.
3. Bilanciamento durata di 35 secondi e ritmo di demolizione.
4. Controlli touch e salvataggi dopo deploy Netlify.

**Non attestato:** test manuali iOS/Android, nuove simulazioni IA Combat Pass 2.
