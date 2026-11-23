# REPORT QA — Fight 4 Concerts P3 finale

**Data:** 19 novembre 2026. Test Chromium locale, intercettando le risorse direttamente dal filesystem (ambiente del browser con navigazione HTTP bloccata). Nessun deploy Netlify eseguito.

| Verifica | Risultato |
|---|---|
| 8 giocatori × 2 outfit × 3 battute | **48/48** |
| 7 nemici × 3 battute | **21/21** |
| Layout per ogni testo, larghezza misurata e testo integrale | **69/69**, nessuna ellissi / overflow |
| Giapponese, apostrofi, testo multilinea, emoji con skin tone | **OK** |
| 16 set originali/ALT + 7 nemici, tutti i frame coreografici referenziati presenti | **23/23** |
| Combinazioni di intro (16 outfit × 7 nemici × 3 varianti) | **336**, 0 riferimenti invalidi |
| Rotazione ciclica per ciascuno dei 23 set | **1→2→3→1**, OK |
| VS non saltabile premendo Invio o toccando | **OK** |
| Intro non saltabile con Invio, Escape, Space, J, L, tap | **OK** |
| Fine intro: FIGHT automatico | **OK** |
| Round 2: nessuna nuova intro | **OK** |
| Touch in browser mobile emulato | **OK** |
| Smoke test combattimento: 24 configurazioni × 200 frame | **4.800 frame**, coordinate/vita finite, entro i limiti |
| Browser: eccezioni JavaScript, errori console, richieste fallite | **0 / 0 / 0** |
| Hash PNG invariati dal precedente ZIP P3 | **1.288 sprite + 91 asset P1/P2 identici** |

**Limiti:** test automatizzati e anteprime browser, non certificano fluidità su telefoni reali, bilanciamento soggettivo o compatibilità Netlify in pubblicazione. La simulazione breve del combattimento non sostituisce gli stress test preesistenti per P0–P2.
