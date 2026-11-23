# Fight 4 Concerts — v1.0.3

**Release: 23 novembre 2026**  
Base: v1.0.2 con doppio tocco, già distribuita agli amici.

## Modifiche

- **Schermata di vittoria:** resta visibile almeno 4 secondi. Nessuna transizione automatica. Nelle campagne si passa alla schermata dei risultati con **doppio tocco** oppure **Invio**; la schermata dei risultati richiede una conferma separata prima della prossima tappa.
- **Sconfitte Facile e Normale:** nuova schermata per riprovare lo stesso incontro, con tentativi illimitati. Si può anche tornare al menu. Nessun avanzamento della campagna in caso di sconfitta.
- **Difficile (HARD):** tre vite per l'intera campagna. Ogni **incontro** perso consuma una vita; sono disponibili due retry, mentre alla terza sconfitta la campagna ricomincia dalla prima tappa. Le vite residue sono mostrate sulla mappa e salvate al KO, anche prima di confermare la schermata finale.
- **Descrizioni:** sostituite le biografie degli otto protagonisti con i testi approvati. Le descrizioni degli otto rivali sono state rimosse dalla schermata di selezione.
- **Contatore TOUR:** il numero totale delle tappe nel combattimento corrisponde ora alle otto tappe reali della campagna.

## Non modificato

Tutti gli sprite, i frame, le illustrazioni narrative, gli sfondi, gli attacchi, le speciali, gli sblocchi dei rivali e dei costumi alternativi e le modalità extra sono invariati. Fatality, trofei e varietà dei colpi restano esclusi da questa release.

## Salvataggi

Il campo `hardLives` è aggiuntivo: un salvataggio precedente senza il campo viene caricato con tre vite. Campagne, sblocchi e costumi esistenti non vengono cancellati. Il salvataggio è locale al browser: per mantenerlo in fase di pubblicazione aggiornare la stessa origine/URL, non cambiare dominio.

## Installazione

Per pubblicare online sostituire **tutti i file** sul sito corrente: caricare la struttura completa dello ZIP, con `index.html`, `assets/`, `frames/` e `dialoghi_p3.json` allo stesso livello. Non pubblicare il solo `index.html`.
