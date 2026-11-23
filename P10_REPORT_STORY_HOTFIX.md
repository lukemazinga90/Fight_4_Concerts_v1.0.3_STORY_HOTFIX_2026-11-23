# Fight 4 Concerts 1.0.3 — Story Hotfix QA

Base: `Fight_4_Concerts_v1.0.3_COUNTDOWN_ARCADE_10S_2026-11-23.zip`.

## Diagnosi confermata

- `assets/C_vittoc_prologue16.png` e `assets/C_conti_festival16.png` sono lo stesso PNG collage di sette miniature, inclusa la Rival Battle con Filippo Conti: lo spoiler era incorporato nella grafica.
- La funzione `drawCampaignStory()` mostrava temporaneamente la scena di Guidotti in altri prologhi in attesa che l'immagine desiderata fosse pronta.
- `assets/C_guidotti_silhouette.png` era a sua volta un collage, anziché un ritratto enigmatico.
- Le scene native che riusavano `drawStage()` ereditavano la didascalia dello stage, che interferiva con il suggerimento del doppio tocco.

## Correzioni

1. Scene Vitto C e Filippo Conti ora composte con sfondo di Magazzino Generali e ritratti già esistenti, senza utilizzare i due PNG collage. Le scene poster successive, i dialoghi e i testi della rivelazione rimangono invariati.
2. Precaricamento delle sole risorse della campagna corrente. Prima venivano richiesti grafici di molte altre campagne simultaneamente.
3. Durante il caricamento di una scena, sfondo neutro con didascalia di caricamento e layout coerente, mai un'immagine di un'altra campagna.
4. Collage ombra Guidotti sostituito con una grafica neutra `???` disegnata via canvas. Non sono stati modificati i file PNG originali.
5. Sfondi di scena senza la didascalia dello stage, per evitare sovrapposizione con `DOPPIO TOCCO / INVIO`.

## Test

- 16/16 campagne renderizzate.
- 278 schermate narrative attraversate nel test visivo automatizzato.
- Nessuna richiesta dei tre asset collage nelle 16 campagne.
- 0 errori JavaScript durante il ciclo completo delle scene.
- Asset originali invariati: 1987/1987 file preservati bit per bit; il solo file del gioco modificato è `index.html`.
- Nessuna modifica a combattimenti, statistiche, meccaniche di salvataggio o storia.

## Limitazioni

Test con Chromium su desktop e scene simulate; non è un test end-to-end su telefono fisico e non implica che il sito Netlify esistente sia stato aggiornato. La resa sulle diverse versioni di Safari resta da verificare dopo la pubblicazione.
