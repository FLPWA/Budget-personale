BUDGET PERSONALE PWA v3

File inclusi:
- index.html
- manifest.webmanifest
- sw.js
- README.txt

Modifiche v3:
- il promemoria backup non compare sull'app vuota
- backup .budget cifrato con password
- cifratura AES-GCM 256 bit
- chiave derivata con PBKDF2-SHA256
- la password del backup non viene salvata
- compatibilità di ripristino con i vecchi backup v2 non cifrati
- pallino privacy invariato

IMPORTANTE:
Se dimentichi la password di un backup cifrato, quel backup non è recuperabile.
I dati operativi restano nel database locale IndexedDB del dispositivo.

- icona personalizzata nero/blu per installazione PWA

- v5: correzione installazione PWA, manifest forzato, id/scope/start_url espliciti, icone any+maskable, cache aggiornata

- v6: movimenti futuri esclusi dal saldo fino alla data effettiva; stipendio futuro non chiude il ciclo in anticipo
- v6: modifica/elimina con icone per movimenti, obiettivi e spese fisse
- v6: obiettivi puliscono il modulo dopo il salvataggio
- v6: spese fisse con prossima scadenza e variazioni di importo con data di decorrenza
- v6: toast interni per i salvataggi
- v6: rimozione/cambio PIN e biometria richiedono autenticazione
