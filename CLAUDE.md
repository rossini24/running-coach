# Running Coach: istruzioni per Claude

App PWA di Luca (GitHub Pages: https://rossini24.github.io/running-coach/). Tutto il contenuto sta in `data.json`; `index.html` lo legge all'apertura.

## Quando Luca scrive "aggiorna l'app"
Prendi TUTTI i dati possibili da Garmin (MCP `garmin`, serve il PC collegato) e aggiorna `data.json`, poi commit e push:
1. **Attività nuove** (`ultime_attivita`): riga in `history.rows`, dettaglio con `dinamiche_corsa` (punti_serie ~85, poi script di estrazione) in `details[id]`, commento del coach in `notes[id]` (type easy/quality/long, title, splits, plus = cosa va, crit = punto critico).
2. **Notte** (`sonno` del giorno): orari, durata, fasi, punteggio, REM %, respirazione, FC e stress nel sonno, bisogno di sonno → `health.today.night` e riga in `health.rows`.
3. **Recupero e stato** (`stato_allenamento`): HRV notte/picco/media/fascia, prontezza con i fattori, ore di recupero, stato Garmin, ACWR, bilanciamento del carico, VO2max → `health.today`, `health.status`, `health.balance`, `health.vo2`.
4. **Giornata** (`riepilogo_giornata` di oggi e di ieri): body battery, FC a riposo, passi, kcal, stress, minuti intensi, piani → `health.today.bb`, `health.today.yesterday`.
5. Aggiorna `state.advice`, `state.health` (cosa va / punto critico, tono che dà morale) e `state.plan.sessions`.
6. Privacy: taglia i primi e gli ultimi 400 m di ogni traccia GPS prima di pubblicare.

Regole del coach: niente lunghi lenti imposti fino a febbraio (i lunghi sono a sentimento; se tirati valgono come qualità), non ossessionare con i numeri, segnala sempre il punto critico ma con un dato che dà morale. Maratona di Milano: 4 aprile 2027.
