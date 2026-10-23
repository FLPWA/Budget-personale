BUDGET PERSONALE PWA v2

Questa versione usa IndexedDB: i dati del budget restano nel dispositivo/browser in cui installi la PWA e non vengono inviati all'hosting.

NOVITÀ:
- backup manuale in file .budget
- ripristino da backup
- frequenza promemoria: disattivata / 7 / 15 / 30 giorni / personalizzata
- data e ora ultimo backup
- “Ricordamelo più tardi”
- tema Sistema / Chiaro / Scuro
- colore principale
- PIN e biometria WebAuthn
- privacy cifre con occhio acceso/spento e stato memorizzato
- ciclo stipendio → stipendio
- avanzo del ciclo trasferito ai risparmi precedenti
- spese fisse e obiettivi

INSTALLAZIONE:
La PWA completa (service worker, installazione e biometria) deve essere servita via HTTPS.
Pubblicare questi file su un hosting statico HTTPS. I dati personali NON sono contenuti nei file pubblicati.

NOTA:
Il backup v2 è un file JSON con estensione .budget. Non è ancora cifrato: conservalo in luogo sicuro. La cifratura del backup può essere aggiunta in una versione successiva.
