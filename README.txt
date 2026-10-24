BUDGET PERSONALE PWA — v24

Installazione GitHub Pages
- Sostituire i file di questo pacchetto nella root del repository FLPWA/Budget-personale.
- NON modificare .github/workflows/static.yml.

Logica contabile
- Saldo di riferimento: fotografia impostata manualmente; non viene riscritta dai movimenti.
- Saldo totale Home: saldo di riferimento + movimenti effettivi successivi alla fotografia.
- Disponibilità Mensile: ciclo stipendio corrente, al netto di spese/quote già impegnate.
- Risparmi disponibili: risparmi liberi + residui dei cicli precedenti + entrate extra libere - spese/accantonamenti, incluse le spese future già impegnate.
- Disponibilità totale = Disponibilità Mensile + Risparmi disponibili.
- Fondi accantonati: entrate destinate a obiettivi + accantonamenti manuali + quote delle fisse non mensili.
- Da accantonare: residuo complessivo ancora scoperto degli obiettivi.

Spese fisse
- Mensili: prenotate nel ciclo e trasformate automaticamente in movimento alla scadenza.
- Bimestrali/trimestrali/semestrali/annuali: quota accantonata per ciclo; alla scadenza il fondo relativo viene consumato e la ricorrenza avanza automaticamente.
- Le ricorrenze restano ancorate al giorno originario (es. 31/01 -> 28/02 -> 31/03).
- La data/importo/frequenza restano modificabili senza dover intervenire ogni mese.

Altre funzioni
- Categorie modificabili; creazione rapida direttamente dalla scelta categoria.
- Movimenti futuri prenotano subito la disponibilità ma non modificano il saldo bancario fino alla data.
- Rollover stipendio automatico al passaggio del nuovo stipendio effettivo.
- Backup cifrato AES-GCM 256 / PBKDF2-SHA256 250.000 iterazioni.
- Privacy globale e per singolo valore.
- Date contabili basate sull'ora locale del dispositivo.
