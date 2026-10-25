BUDGET PERSONALE — v33

Versione con motore contabile delle scadenze fisse e gestione PIN/biometria corretti.

Regole principali:
- Saldo di riferimento: fotografia manuale; il saldo Home cambia solo per movimenti effettivi non inclusi nella fotografia.
- Spese future: prenotano subito la fonte scelta, ma cambiano il saldo solo alla data effettiva.
- Disponibilità totale = Disponibilità Mensile + Risparmi disponibili. I Fondi accantonati sono esclusi.
- Fondi accantonati distinti: fondo generico, singoli obiettivi e fondi delle singole spese fisse.
- Le quote delle spese fisse non mensili non transitano dai risparmi.
- Alla scadenza di una spesa fissa, se la fonte prevista copre tutto, il movimento viene registrato automaticamente e la scadenza avanza.
- Se la fonte prevista non basta, la scadenza NON avanza e il pagamento NON viene registrato finché l'utente non sceglie da quale altra disponibilità coprire il residuo.
- Un movimento manuale equivalente alla scadenza viene assorbito nella spesa fissa e la copertura viene normalizzata senza doppio consumo.
- Gli stipendi futuri aprono il nuovo ciclo alla data effettiva; il residuo del ciclo precedente passa ai risparmi una sola volta.
- Le date contabili usano l'ora locale del dispositivo.
- Backup cifrato AES-GCM/PBKDF2.

Aggiornamento GitHub Pages:
Sostituire index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png e README.txt. Non modificare .github/workflows/static.yml.

Sicurezza v33:
- PIN sempre disponibile come fallback della biometria.
- Dopo lo sblocco dell’app, biometria e PIN possono essere disattivati senza una seconda autenticazione.
- Disattivando il PIN si disattiva tutta la protezione e si elimina il riferimento biometrico locale.
- La biometria può essere riattivata in futuro e registra una nuova credenziale del dispositivo.


v33: sicurezza riscritta. Il PIN viene creato solo se l’utente lo inserisce esplicitamente e viene verificato in modo stretto. La biometria ripristina il flusso WebAuthn di piattaforma non residente usato nelle versioni precedenti funzionanti e viene segnata attiva solo dopo registrazione riuscita.


v33: recupero automatico dello stato corrotto bioEnabled=true/pinEnabled=false creato dalle versioni precedenti. In tale stato vengono azzerate esclusivamente le impostazioni di sicurezza; i dati del budget restano intatti. Nessun PIN arbitrario può più sbloccare una protezione biometrica.
