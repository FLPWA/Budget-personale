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
