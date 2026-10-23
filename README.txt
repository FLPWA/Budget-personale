BUDGET PERSONALE PWA — v13

AGGIORNAMENTO v16 — REVISIONE STRUTTURALE
- Date locali del dispositivo: niente UTC per giorno corrente e scadenze.
- Aggiornamento automatico della data a mezzanotte locale, anche con cambio ora solare/legale gestito dal dispositivo.
- Saldo di riferimento nelle Impostazioni = fotografia immutabile finché non viene salvata di nuovo manualmente.
- I movimenti già effettivi al momento della fotografia sono considerati inclusi; i movimenti futuri incidono sul saldo Home solo alla loro data.
- Le spese future prenotano subito Risparmi/Fondi; quelle dal Mensile prenotano solo il ciclo corrente.
- Disponibilità totale = Disponibilità Mensile + Risparmi disponibili.
- Modifica movimento: la vecchia versione del movimento viene neutralizzata durante il controllo copertura, evitando falsi fondi insufficienti.
- Eliminazione/modifica stipendio elimina gli eventuali rollover collegati per evitare residui fantasma.
- Risparmi negativi non vengono più nascosti artificialmente a zero nei calcoli interni.
- Scadenze fisse arretrate avanzano automaticamente alla ricorrenza successiva.
- Service worker, manifest e cache allineati a v16.
- Nessun alert/confirm/prompt nativo del browser: vengono usate finestre interne dell'app.


File inclusi:
- index.html
- manifest.webmanifest
- sw.js
- icon-192.png
- icon-512.png
- README.txt

DATI
I dati operativi restano nel database IndexedDB locale del dispositivo.
Il repository GitHub contiene soltanto l'applicazione.

LOGICA CONTABILE
- Saldo totale sul conto: saldo bancario effettivo.
- Disponibilità Mensile: denaro del ciclo stipendio ancora spendibile.
- Risparmi disponibili: risparmi liberi iniziali + residui dei cicli chiusi + entrate extra libere - spese pagate dai risparmi - trasferimenti verso fondi accantonati.
- Fondi accantonati: denaro vincolato creato esclusivamente da accantonamenti, entrate destinate a obiettivi e quote delle spese periodiche non mensili.
- Disponibilità totale = Disponibilità Mensile + Risparmi disponibili.
- Da accantonare: importo complessivo ancora scoperto degli obiettivi.

IMPOSTAZIONI > BUDGET
Sono presenti soltanto:
- Saldo di riferimento
- Risparmi liberi iniziali

Non esiste più l'inserimento diretto di “Fondi già accantonati” nelle Impostazioni.
Per destinare denaro già presente a un obiettivo usare “Accantona fondi”.
Un'entrata può inoltre essere destinata direttamente a un obiettivo e in quel caso non aumenta i risparmi liberi.

SALDO DI RIFERIMENTO
Il saldo inserito viene riconciliato con i movimenti effettivi già presenti nell'app, così non vengono conteggiati due volte.
Da quel punto i nuovi movimenti effettivi modificano normalmente il saldo.

CICLO STIPENDIO
Lo stipendio alimenta la Disponibilità Mensile.
Alla partenza di un nuovo ciclo, l'eventuale residuo del ciclo precedente passa una sola volta nei Risparmi disponibili.
Le altre entrate non alimentano il mensile: vanno nei risparmi oppure direttamente a un obiettivo.

SPESE
Ogni spesa sceglie la fonte: Disponibilità Mensile, Risparmi o Fondi accantonati.
Se la fonte scelta non basta, l'app consente di coprire il residuo con una seconda fonte.

SPESE FISSE
Le spese mensili previste incidono sulla Disponibilità Mensile del ciclo.
Le spese periodiche non mensili generano una quota per ciclo che passa direttamente da Disponibilità Mensile a Fondi accantonati, senza transitare dai Risparmi.
Le spese fisse sono raggruppate per frequenza e ordinate per prossima scadenza.

OBIETTIVI
Creare un obiettivo non sposta denaro.
L'importo scoperto compare in “Da accantonare”.
La quota per ciclo è informativa.
La copertura aumenta con:
- Accantona fondi associato all'obiettivo
- entrate destinate direttamente all'obiettivo

CATEGORIE
Le categorie si gestiscono dalle Impostazioni.
Durante l'inserimento di un movimento o di una spesa fissa è disponibile in fondo alla scelta categoria “+ Crea nuova categoria…”, senza uscire dal modulo.

INTERFACCIA
- Home con sei riquadri riordinabili.
- Pallino privacy globale e per singolo importo.
- Impostazioni tramite ingranaggio.
- Guida generale tramite icona informazioni.
- Nessun alert/confirm/prompt nativo del browser: avvisi, conferme e richieste usano finestre interne all'app.

REPORT
Report annuale delle spese effettive per categoria e previsione annualizzata delle spese fisse, con dettaglio selezionabile.

BACKUP
Backup cifrato AES-GCM 256 bit.
Chiave derivata con PBKDF2-SHA256, 250.000 iterazioni.
La password non viene salvata nell'app.

PWA
Service worker v13 con navigazione network-first e cache aggiornata.
URL previsto: https://flpwa.github.io/Budget-personale/

AGGIORNAMENTO v13
- Rimossi definitivamente “Fondi già accantonati” e relativa associazione obiettivo dalle Impostazioni.
- I vecchi fondi iniziali vengono azzerati dalla vecchia configurazione: per ricrearli usare “Accantona fondi”.
- Mantenuta la separazione strutturale tra saldo, mensile, risparmi e fondi accantonati.
- Mantenuta la creazione rapida delle categorie nei moduli.
- Mantenuti i modal interni al posto delle finestre native del browser.

- v15: le spese future prenotano immediatamente la disponibilità della fonte scelta (Mensile, Risparmi o Fondi accantonati), mentre il Saldo totale del conto cambia solo alla data effettiva. Il passaggio da futuro a effettivo non sottrae una seconda volta la disponibilità.

v15 - Saldo di riferimento nelle Impostazioni
Il campo "Saldo di riferimento" resta la fotografia salvata dall'utente e non viene modificato dalla registrazione di nuovi movimenti. Il "Saldo totale sul conto" nella Home resta invece il valore contabile aggiornato: cambia con i movimenti effettivi, mentre i movimenti futuri prenotano la disponibilità senza modificare il saldo bancario fino alla loro data.
