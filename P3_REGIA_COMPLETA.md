# FIGHT 4 CONCERTS — P3: regia e implementazione completa

**Stato:** implementato e verificato in browser locale, senza deploy Netlify — 19 novembre 2026.

## Regole definitive

- **Intro NON skippabili**: né Invio, né ESC, né tap o pulsanti touch possono anticipare la fine. Anche la schermata VS dura almeno 90 frame (1,5 s a 60 Hz); i comandi durante l'intro vengono svuotati per evitare attacchi involontari appena parte il round.
- Un solo dialogo per personaggio a match, scelto fra tre e mostrato in ordine 1 → 2 → 3 → 1. Contatori indipendenti per Originale, ALT e ciascuno dei sette avversari, persistenti tra sessioni quando localStorage è disponibile.
- La prima battuta è del personaggio a sinistra, poi parla quello a destra. Nei round successivi al primo non viene ripetuta l'intro.
- **Durata adattiva**: circa 2,6–3,6 s per battuta nelle frasi attuali; l'intera intro dura circa 5,2–7,1 s più 1,5 s di VS. Il tempo del combattimento resta fermo fino al FIGHT.
- Ogni animazione usa i **PNG già approvati**, selezionati per il costume effettivo. Non si ridisegnano volti, arti o outfit. Pose diverse fra le tre frasi sono scelte tramite frame attuali e non richiedono nuovi sprite.
- Biglietto da concerto viola/oro, ritratto ricavato dallo sprite del costume, nome, tagline, indicatore 1/3–3/3, balloon con punta sul parlante e testo progressivo, senza tagli.

## Regia dei 16 outfit giocabili

| Personaggio | Costume | Titolo nel ticket | Entrata comune | Frase 1 · Accento | Frase 2 · Accento | Frase 3 · Accento |
|---|---|---|---|---|---|---|
| **Guidotti** | Originale | TECHNO CROCCANTINA | beat techno, avanzata e pugno breve | assaggio ironico / gesto del gusto | sguardo sprezzante verso le chitarre | invito scherzoso al concerto |
| **Guidotti** | ALT | OROSCOPO & TAROCCHI | ingresso da guru in tuta arancione | posa di lettura astrologica | gesto di invito al workshop | raccoglimento zen per la dieta liquida |
| **Giannini** | Originale | RIFF & GIUDIZI | ingresso teso, ritmo di chitarrista | sguardo complice sul pubblico | finta pennata con braccio teso | esasperazione per la techno |
| **Giannini** | ALT | RONIN DEL RIFF | entrata da ronin, costume originale ALT | allusione teatrale in giapponese | finta stoccata a mano libera | pausa riflessiva e sentenza poetica |
| **Frillo** | Originale | VECCHIA GUARDIA | passi da habitué e guardia rilassata | schiena stanca, abbassamento | gesto da intenditore di lunga data | rassegnazione per il viaggio in bus |
| **Frillo** | ALT | OSTE DELLA VIOLA | abito elegante, atteggiamento da oste viola | gesto di servire / porgere | richiamo polemico al coperto | esultanza per la Viola e il vino |
| **Vitto P** | Originale | GOSSIP DA PALCO | entrata energica e mimica da commentatrice | gesto di osservazione dei due fan | stanchezza con postura raccolta | esultanza da ritornello |
| **Vitto P** | ALT | DITA AL CIELO | già in costume cappello-dito, medie pose vere | doppio gesto di sfida | accento ritmico più insistito | colpo teatrale e posa finale |
| **Vitto C** | Originale | REGINA DEL DANCEFLOOR | passo da dancefloor, personaggio femminile | indica simbolicamente il regno del set | movimento ritmico breve | abbassamento ironico per la schiena |
| **Vitto C** | ALT | CAFFEINA PURA | costume elegante con tazzina nei frame | presentazione di sé / tazzina | colpo puntato verso la rivale | tazzina e ripetizione nervosa |
| **Rettori** | Originale | GRIDO DI BATTAGLIA | ingresso fiero e battagliero | grido con braccia alzate | gesto dialettale colloquiale | posa da dichiarazione solenne |
| **Rettori** | ALT | ISOLOTTO IN PISTA | abito viola, entrata popolare e aggressiva | puntamento diretto | braccia alzate sulla musica di strada | gesto verso orecchie e radio |
| **Luke** | Originale | POGO ANIMALESCO | ingresso basso, animalesco, cappello rosa | si abbassa per i sandali | oscillazione da capogiro | gesto verso il volto e trucco |
| **Luke** | ALT | UNICORNO DEL CAOS | unicorno rosa, ingresso stravagante | energia rosa in posa speciale | esultanza di passerella | gesto sfacciato e giocoso |
| **Lore** | Originale | SAMP E SOFFERENZA | maglia Samp, passo di pogo deciso | schiena incurvata dal dolore calcistico | pausa malinconica | esultanza autoironica |
| **Lore** | ALT | LOTTA IN 4K | giacca GKN, passo militante | gesto da ripresa del corteo | mano tesa in gesto tecnico | alzata di pugni da megafono |

## Regia dei 7 nemici

| Nemico | Titolo nel ticket | Entrata | Battuta 1 · Accento | Battuta 2 · Accento | Battuta 3 · Accento |
|---|---|---|---|---|---|
| **Occasionale** | FAN OCCASIONALE | passo timido da fan casuale | sorriso da ritornello | mezzo dietrofront per il bis | posa da selfie e birra |
| **Mainstreamer** | RADIO HIT | camminata da hit radiofonica | flash da telefono / stella | ritornello cantato a braccia mosse | gesto da classifica e radio |
| **Poser** | LOOK PRIMA DI TUTTO | telefono in mano, posa studiata | inquadratura prima della musica | posa da outfit | gesto da parrucchiere e scatto |
| **Bolognese** | PORTICI & ROCK | ingresso irruento con sciarpa | schiamazzo da orario del concerto | posa seduta sotto i portici | corsa per l’ultimo tram |
| **Metallaro** | METAL ETERNO | ingresso pesante da headbanger | accento sonico e pugni | ricordo struggente del 1987 | rimprovero metal e colpo finale |
| **Proletario vero** | ROCK POPOLARE | passo operaio con casco giallo | braccia aperte: musica per tutti | gesto verso balcone immaginario | pugno rosso contro i luoghi comuni |
| **MaxPezzali** | BOSS — ONDA 883 | ingresso del boss col cappello 883 | sentenza sull’Uomo Ragno | giro simbolico nord-sud-ovest-est | esultanza e onda finale 883 |

## Coreografia tecnica: frame reali per ciascuna variante

Le colonne "gesto 1/2/3" si riferiscono rispettivamente alla prima, seconda e terza battuta. Le pose finali, anch'esse in ordine 1/2/3, si ripetono fino al cambio di parlante. Tutti gli indici sono riferiti alla cartella `frames/<nome_costo>/` e vanno da `000` a `055`.

| Set sprite | Entrata | Gesto 1 | Gesto 2 | Gesto 3 | Finali 1 / 2 / 3 |
|---|---|---|---|---|---|
| Guidotti | 004 005 006 007 | 028 029 030 046 | 025 026 027 045 | 047 048 046 047 | 046 047 000 / 045 046 000 / 047 048 000 |
| Guidotti_ALT | 004 005 006 007 | 000 028 029 047 | 045 046 047 048 | 012 013 014 000 | 047 048 000 / 046 047 000 / 045 046 000 |
| Giannini | 003 004 005 006 | 045 046 000 001 | 028 029 030 046 | 012 013 014 047 | 045 046 000 / 047 048 000 / 045 046 000 |
| Giannini_ALT | 003 004 005 006 | 045 046 047 048 | 028 029 030 046 | 000 001 045 046 | 046 047 000 / 045 046 000 / 000 001 000 |
| Frillo | 003 004 005 006 | 012 013 014 045 | 025 026 027 028 | 000 001 012 013 | 045 046 000 / 047 048 000 / 012 013 000 |
| Frillo_ALT | 003 004 005 006 | 028 029 030 046 | 045 046 047 048 | 047 048 046 047 | 045 046 000 / 047 048 000 / 046 047 000 |
| VittoP | 003 004 005 006 | 000 001 028 029 | 012 013 014 046 | 045 046 047 048 | 045 046 000 / 012 013 000 / 047 048 000 |
| VittoP_ALT | 003 004 005 006 | 045 046 047 048 | 047 048 047 048 | 028 029 030 047 | 046 047 000 / 047 048 000 / 045 047 000 |
| VittoC | 003 004 005 006 | 028 029 030 046 | 000 001 045 046 | 012 013 014 047 | 047 048 000 / 045 046 000 / 046 047 000 |
| VittoC_ALT | 003 004 005 006 | 045 046 047 048 | 028 029 030 045 | 047 048 047 048 | 047 048 000 / 028 029 000 / 047 048 000 |
| Rettori | 003 004 005 006 | 047 048 047 048 | 000 001 045 046 | 045 046 047 048 | 047 048 000 / 045 046 000 / 047 048 000 |
| Rettori_ALT | 003 004 005 006 | 028 029 030 046 | 045 046 047 048 | 047 048 047 048 | 045 046 000 / 047 048 000 / 046 047 000 |
| Luke | 007 008 009 010 | 012 013 014 000 | 045 046 012 013 | 028 029 030 047 | 012 013 000 / 045 046 000 / 047 048 000 |
| Luke_ALT | 003 004 005 006 | 051 052 053 054 | 047 048 047 048 | 045 046 047 048 | 047 048 000 / 046 047 000 / 047 048 000 |
| Lore | 003 004 005 006 | 045 046 012 013 | 000 001 045 046 | 047 048 045 046 | 012 013 000 / 045 046 000 / 047 048 000 |
| Lore_ALT | 003 004 005 006 | 000 001 028 029 | 025 026 027 030 | 047 048 046 047 | 045 046 000 / 045 046 000 / 047 048 000 |
| Occasionale | 003 004 005 006 | 000 001 047 048 | 003 005 025 027 | 025 026 051 053 | 047 048 000 / 045 046 000 / 047 048 000 |
| Mainstreamer | 003 004 005 006 | 003 000 051 053 | 045 046 047 048 | 028 029 030 046 | 047 048 000 / 047 048 000 / 045 046 000 |
| Poser | 003 004 005 006 | 000 001 028 030 | 045 046 047 048 | 003 005 051 053 | 045 046 000 / 047 048 000 / 045 046 000 |
| Bolognese | 003 004 005 006 | 047 048 051 053 | 012 013 014 015 | 003 005 045 046 | 047 048 000 / 012 013 000 / 045 046 000 |
| Metallaro | 003 004 005 006 | 047 048 051 053 | 012 013 014 047 | 028 029 030 053 | 047 048 000 / 045 046 000 / 047 048 000 |
| Proletario | 003 004 005 006 | 003 004 005 000 | 028 029 030 047 | 045 046 051 053 | 000 001 000 / 047 048 000 / 047 048 000 |
| MaxPezzali | 003 004 005 006 | 028 029 030 045 | 003 004 005 007 | 047 048 051 053 | 047 048 000 / 045 046 000 / 047 048 000 |

## Timing e interfaccia

1. **VS**: 90 frame minimi, non skippabile.
2. **Ingresso**: primi 36 frame, due personaggi entrano da lati opposti, poi restano sull'arena.
3. **Battuta sinistra**: gesto selezionato dalla variante e posa finale, testo progressivo su ticket. La battuta dura da 156 a 252 frame in base alla lunghezza.
4. **Battuta destra**: stessa logica ma with punta del balloon rivolta a destra; selezione delle frasi indipendente dall'outfit a sinistra.
5. **FIGHT**: partenza automatica e pulizia del buffer dei comandi. Nei round 2+ si passa da VS direttamente al combattimento.

**Tipografia:** riadattamento automatico con misurazione reale della larghezza, al massimo quattro righe senza ellissi. Le frasi in giapponese usano font CJK con fallback; gli emoji sono segmentati per grafema così tono della pelle e dito restano uniti. Le 14 emoji per frase sono rese centrate, senza riduzioni del contenuto.

## Dialoghi completi

Per modificare le battute usare `dialoghi_p3.json` (UTF-8). Le chiavi dei giocatori contengono `original` e `alt`, ciascuna con tre frasi; `_nemici` contiene sette terne. In gioco c'è un fallback incorporato nel file HTML in caso di errore di caricamento. Il file `coreografie_p3.json` documenta le pose; la versione effettivamente usata dal gioco è integrata nell'HTML.

### Guidotti

**ORIGINAL**

1. «Questo match è proprio croccantino»
2. «Avresti anche del gusto, non fosse per quelle chitarre»
3. «Venerdì che fai? Concertino di Hachiko?»

**ALT**

1. «E quindi tu saresti un Sagittario ascendente Vergine. Interessante eh»
2. «Martedì sera a Tripalle faccio un workshop di tarocchi, ti può interessare?»
3. «Cibo? Sopravvalutato. Il mio credo prevede solo dieta liquida»

### Giannini

**ORIGINAL**

1. «今夜、すごい女がいたの見た？»
2. «Dai che forse stasera c'è un vero chitarrista a suonare»
3. «Serata techno? Tanto valeva che mi chiedevi di andare ad un comizio di Salvini»

**ALT**

1. «たぶん、俺の言ってること分かってないんだな。今夜は女が山ほどいるんだぜ！»
2. «Visti i tuoi gusti musicali hai mai pensato di fare seppuku?»
3. «Bello è ciò che piace, / e comodo è chiamarlo / bellezza, per non capire»

### Frillo

**ORIGINAL**

1. «Hai per caso un Oki? Ho la schiena a pezzi»
2. «Fatti da parte. Conosco questa band da quando suonavano alla Sagra della ficamaschia dorata di Porto Ercole»
3. «Verrei anche ma ho speso tutti i miei soldi per andare a quel concerto a Tsiblisi. Sono solo 40 ore di Flixbus»

**ALT**

1. «Oh bischero, la birra la vòi o l’autografo del cantante? Te lo servo io, ma a rate come la Viola»
2. «Fatti sotto, figliolo, la band attacca tra un’ora. Il coperto però te lo paghi, eh»
3. «Stasera c’è concerto e la Viola gioca. Scegli tu: il rock o il tifo. Io ho già scelto il vino»

### Vitto P

**ORIGINAL**

1. «Sto shippando questi due da tre settimane e loro manco si parlano. Vibes»
2. «Ho una playlist dello stress in riproduzione dal lunedì. Nessun drop mi basta più. Crisi»
3. «Ok boomer, il mio ship preferito è il ritornello del pezzo. Non chiedere»

**ALT**

1. «🖕🖕🖕🖕🖕🖕🖕🖕🖕🖕🖕🖕🖕🖕»
2. «🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿🖕🏿»
3. «🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻🖕🏻»

### Vitto C

**ORIGINAL**

1. «Questo è il mio regno, vediamo come reggi 8 ore di set»
2. «Anche la mia sveglia suona a 150 BPM»
3. «Il vero sballo è non aver mal di schiena»

**ALT**

1. «C sta per Conti baby. Conti Valerio»
2. «Mi stai dicendo che preferisci Fiorenzato? Ti pentirai di questa affermazione»
3. «Perchè mi dici che sembro agitata? Sono solo al decimo caffè della giornata»

### Rettori

**ORIGINAL**

1. «Bella merde!»
2. «El me acento toscano? Certo che no lo go perso»
3. «Una Rettori non è mai in ritardo, Frodo Baggins. Né in anticipo. Arriva precisamente quando intende farlo»

**ALT**

1. «Oh bono, sei venuto all’Isolotto a fare lo chic? Qui si combatte col cuore»
2. «Oh babbo, la musica all’Isolotto si fa in strada, mica in teatro. Se ti piace la rima, attacca!»
3. «Passi per via dell’Isolotto con la radio a palla? Qui si canta forte, o ti ci mando io a farti le orecchie»

### Luke

**ORIGINAL**

1. «Arregimi un attimo i sandali. Devo andare a pogare»
2. «Socmel mi gira tutto. Bere quell'americano alla goccia non è stata una grande idea»
3. «Senti ma posso farti io il trucco? Dei pallini bianchi ti starebbero benissimo»

**ALT**

1. «Il Lato Rosa della Forza è la via per molte abilità da alcuni ritenute... innaturali.»
2. «Dovresti aggiungere un pò di colore al tuo outfit, è cosi banale»
3. «Se porto le mutande sotto a questo costume? Ovviamente no»

### Lore

**ORIGINAL**

1. «Tifo Samp: non ho bisogno di vincere per soffrire, ci penso io»
2. «Lo scudetto del ‘91 l’ho visto solo nei video. Il mio dolore è più vintage»
3. «Al concerto ho cantato tutti i pezzi, tranne quelli che non ricordo. Come il gol della Samp»

**ALT**

1. «Ho girato il corteo con il drone. Il video è perfetto, la cassa integrazione un po’ meno»
2. «Montaggio in 4K della vertenza. Se il padrone non lo guarda, almeno lo guarda l’algoritmo»
3. «Ho un megafono, una telecamera e tre cause in corso. Non chiedermi cosa faccio nel tempo libero»

## Nemici: testi

### OCCASIONALE

1. «Vengo ai concerti una volta l’anno, ma il ritornello lo so cantare tutto»
2. «Ho preso il biglietto per il primo tempo. Il bis lo guardo su Instagram»
3. «Non sono un fan, sono qui per la birra e il selfie»

### MAINSTREAMER

1. «Se non è in classifica non esiste, scusa tanto»
2. «Ho ascoltato il disco tre volte, ormai lo canto come se fosse mio»
3. «Il rock vero? Quello che passa in radio alle sette di mattina»

### POSER

1. «Foto prima, musica dopo. Il concerto è una location»
2. «Il look è quello giusto, manca solo il gruppo che lo sa suonare»
3. «Ti piace il mio stile? Ci ho messo tre ore e due parrucchieri»

### BOLOGNESEEEEE

1. «A Bologna il concerto inizia alle undici e finisce quando dico io»
2. «Sotto i portici si suona meglio, lo dico da sempre»
3. «Ho la maglia gialla, il cappello e la sindrome dell’ultimo tram»

### METALLARO

1. «Il volume non è mai abbastanza. Lo so, lo dicono tutti»
2. «Ho sentito il primo disco nel 1987 e non mi sono più ripreso»
3. «Ti vedo sorridere. È un crimine nei confronti del metal»

### PROLETARIO VERO

1. «Il biglietto costa come una bolletta, ma la musica è di tutti»
2. «Io il concerto l’ho visto dal balcone del mio amico»
3. «Ci hanno detto che il rock è morto. Il rock lavora ancora alla mensa»

### MAX PEZZALI

1. «Hanno ucciso l'Uomo Ragno. Io invece ho appena fatto fuori la tua playlist»
2. «Nord, sud, ovest, est: girala come vuoi, alla fine il ritornello lo sai»
3. «Sei un mito? Come mai allora hai paura di uno che canta dagli anni Novanta?»

## Vincoli di manutenzione

- Non pubblicare su Netlify per vedere questi cambiamenti: il pacchetto ha una build locale completa e le anteprime sono state catturate da Chromium.
- Non cambiare i PNG originali o gli anchor. Se si aggiungono frame in futuro, validarli confrontando **stesso personaggio e stesso outfit**, con due braccia e due gambe coerenti e senza duplicazioni/sovrapposizioni.
- Verificare a mano anche su telefono reale FPS, input e leggibilità dopo il successivo eventuale deploy.
