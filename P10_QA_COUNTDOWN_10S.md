# Fight 4 Concerts — verifica tecnica countdown arcade

**Data:** 23 novembre 2026  
**Build di partenza:** v1.0.3 CAMPAGNA VITE DESCRIZIONI

## Esito

- 243 scenari eseguiti, 2426 controlli logici completati, 0 fallimenti.
- Nessun errore JavaScript rilevato nel browser di test.
- Input verificati su desktop (mouse) e touch simulato su smartphone (selezione retry/menu).

## Copertura

- Tutte le 16 campagne × 3 difficoltà × tappe 1, 5 e 8: ingresso automatico nel countdown dopo la sconfitta, riproduzione dei numeri 10, 9 e 1, timeout a zero, rientro nel menu e assenza di avanzamento della campagna.
- Retry per tutte le 16 campagne e tutte le difficoltà, senza consumare vite aggiuntive.
- Ultima vita in Difficile per tutte le 16 campagne: compare 0/3; timeout al menu; conferma per ricominciare dalla prima tappa.
- Scelta manuale TORNA AL MENU per tutte le campagne.
- Un input in ritardo a timer scaduto non può aggirare il timeout.
- Le vittorie conservano la schermata per almeno 4 s senza avvio automatico del timer.
- Una sconfitta in VS non attiva il countdown della Campagna.

## Test con cronometro reale

Un ulteriore test in Chromium senza simulazione del tempo ha lasciato trascorrere 10,8 secondi reali: il timer ha portato automaticamente al menu, preservando vite e progressi. Nessun errore JavaScript.

## Limiti

I controlli del timer sono stati accelerati simulando il tempo in Chromium per verificare precisamente i confini di secondo. Sono stati verificati eventi mouse/touch reali emulati, non il comportamento su un dispositivo fisico. La build non è stata caricata sul sito Netlify.
