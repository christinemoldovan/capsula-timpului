# Capsula Timpului ⚽

Aplicație web pentru statistici de echipă de fotbal: golgheteri, istoric meciuri, prezență per meci și rezumat general. Datele sunt sincronizate live prin Firebase Realtime Database, vizibile pentru toată echipa.

## Funcționalități

- **Statistici golgheter** — clasament cu bare de progres
- **Istoricul meciurilor** — scor, marcatori, rezultat (Victorie/Egal/Înfrângere)
- **Prezență per meci** — doar jucătorii prezenți primesc meci jucat în statistici
- **Rezumat general** — meciuri jucate, victorii, remize, înfrângeri, total goluri date/primite
- **Panou Admin protejat prin parolă** — doar adminul poate adăuga/șterge meciuri; restul aplicației e public, fără autentificare
- **Sincronizare live** — toate datele sunt salvate în Firebase Realtime Database, vizibile instant de toată echipa

## Structura proiectului

```
capsula-timpului/
├── index.html                   # Aplicația completă (HTML + CSS + JS)
├── firebase-config.js            # Config Firebase cu valori reale (NU se versionează)
├── firebase-config.example.js    # Template pentru config (se versionează)
├── .gitignore
└── firebase.json                 # Config Firebase Hosting
```

## Setup local

1. Clonează acest repository:
   ```bash
   git clone https://github.com/christinemoldovan/capsula-timpului.git
   cd capsula-timpului
   ```

2. Creează `firebase-config.js`:

3. Completează `firebase-config.js` cu valorile reale din [Firebase Console](https://console.firebase.google.com) → Project Settings → Your apps:
   ```js
   const firebaseConfig = {
     apiKey: "...",
     authDomain: "...",
     databaseURL: "...",
     projectId: "...",
     storageBucket: "...",
     messagingSenderId: "...",
     appId: "..."
   };
   ```

4. Deschide `index.html` direct în browser pentru a testa local.

## Deploy pe Firebase Hosting

```bash
npm install -g firebase-tools
firebase login
firebase deploy
```

Aplicația va fi disponibilă la `https://<project-id>.web.app`.

## Configurare

- **Lista jucătorilor** și **portarul** se modifică direct în `index.html`, în variabilele `PLAYERS` și `GK`.
- **Parola de admin** se modifică în `index.html`, variabila `ADMIN_PASSWORD`.
- **Regulile Firebase Database** (citire/scriere publică) se configurează în Firebase Console → Realtime Database → Rules.
