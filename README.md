# Joakim Lindquister - Portfolio Website

A personal portfolio website hosted on GitHub Pages.

## 🚀 Features

- Clean, modern design with dark theme
- Responsive layout for all devices
- Fast loading static HTML/CSS
- Automated PR previews for testing changes

## 🛠️ Development

This is a static website with no build process required. Simply edit the files:

- `index.html` - Main portfolio page
- `styles.css` - All styling and layout

## 📦 PR Preview System

When you create a pull request, the following happens automatically:

1. **Build**: A preview version is created with PR indicators
2. **Artifact**: The preview is uploaded as a downloadable artifact
3. **Comment**: A bot comment provides download link and testing instructions

### Testing Your Changes

1. Create a pull request
2. Wait for the "Deploy PR Preview" workflow to complete
3. Download the preview artifact from the workflow run
4. Extract and open `index.html` to test your changes
5. Compare with the live site at [quist.github.io](https://quist.github.io)

## 🎨 Design System

- **Font**: Inter (Google Fonts)
- **Theme**: Dark background (#1a1a1a) with gradient effects
- **Accent**: Orange/yellow gradients (#f39c12, #e67e22)
- **Layout**: Centered container (max-width: 700px)
- **Cards**: Subtle glass morphism effect

## 📄 File Structure

```
├── index.html          # Main portfolio page
├── styles.css          # All styling
├── CLAUDE.md           # Development guidance
├── .github/
│   ├── workflows/
│   │   └── pr-validation.yml  # PR preview deployment
│   └── copilot-instructions.md
└── README.md           # This file
```

## 🌐 Deployment

- **Production**: Automatically deployed to GitHub Pages from `master` branch
- **PR Previews**: Built and packaged as downloadable artifacts via GitHub Actions

## 🔧 Local Development

No build tools required! Simply:

1. Clone the repository
2. Open `index.html` in your browser
3. Edit files and refresh to see changes

## 📱 Browser Support

Supports all modern browsers with CSS Grid and Flexbox support.

## ☁️ Firebase/Firestore for gjestebok

Gjesteboken bruker nå Firebase Firestore for persistering og sanntidsoppdatering. Ingen build er nødvendig; SDK lastes fra CDN i `gjestebok.html`.

### 1) Oppsett i Firebase Console
1. Opprett et Firebase-prosjekt
2. Aktiver Firestore Database (Native mode)
3. Legg til en Web App (uten hosting)
4. Kopier konfigurasjonen (apiKey, authDomain, projectId, osv.)

### 2) Konfigurer `gjestebok.html`
Finn `initFirebase()` og erstatt placeholder‑verdier:

```
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

Meldinger lagres i samlingen `guestbookMessages` med feltene:
- `name: string (≤ 50)`
- `message: string (≤ 500)`
- `createdAt: serverTimestamp()`

### 3) Firestore sikkerhetsregler (anbefalt minimum)
Tillat lesing for alle, tillat kun opprettelse (ikke oppdatering/sletting), og valider felter og lengder.

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /guestbookMessages/{docId} {
      allow read: if true;
      allow create: if
        request.resource.data.keys().hasOnly(["name", "message", "createdAt"]) &&
        request.resource.data.name is string &&
        request.resource.data.message is string &&
        request.resource.data.name.size() > 0 && request.resource.data.name.size() <= 50 &&
        request.resource.data.message.size() > 0 && request.resource.data.message.size() <= 500 &&
        request.resource.data.createdAt is timestamp;
      allow update, delete: if false;
    }
  }
}
```

Tips:
- Vurder å aktivere moderat antispam (honeypot er allerede inkludert i skjemaet). For mer robust beskyttelse, bruk f.eks. reCAPTCHA/Turnstile og/eller en enkel mellomtjener.
- Legg inn indekser i Firestore ved behov. Standard sortering på `createdAt desc` fungerer uten ekstra indeks.

### 4) Lokal testing
- Åpne `gjestebok.html` direkte i nettleser og test innsending/visning.
- Konsollen viser eventuelle feil fra Firestore/SDK.

### 5) Deploy
- Push til `master` → GitHub Pages oppdaterer produksjon.