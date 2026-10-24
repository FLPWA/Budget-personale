BUDGET PERSONALE — v28

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

Sicurezza v28:
- PIN sempre disponibile come fallback della biometria.
- Disattivazione biometria autorizzata dal PIN, senza richiedere la biometria stessa.
- Disattivando il PIN si disattiva tutta la protezione e si elimina il riferimento biometrico locale.
- La biometria può essere riattivata in futuro e registra una nuova credenziale del dispositivo.


v28: correzione sicurezza. La disattivazione PIN/biometria riconosce la sessione sbloccata con PIN; la biometria viene registrata come credenziale WebAuthn di piattaforma non discoverable, con PIN sempre disponibile come recupero.
