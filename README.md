# Joakim Lindquister - Portfolio Website

A personal portfolio website hosted on GitHub Pages.

## 🚀 Features

- Light, paper-inspired design
- Responsive layout
- Guestbook backed by Firebase Firestore
- Works without JavaScript (animations are progressive enhancement)
- Automated PR previews

## 🛠️ Development

This is a static website with no build process required. Simply edit the files:

- `index.html` - Main portfolio page
- `gjestebok.html` - Guestbook
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

- **Fonts**: Geist, Instrument Serif, JetBrains Mono and Caveat (Google Fonts)
- **Theme**: Light paper background with a rust-red accent, defined as oklch tokens in `styles.css`
- **Layout**: Sections up to 1100px wide

## 📄 File Structure

```
├── index.html          # Main portfolio page
├── gjestebok.html      # Guestbook (Firebase Firestore)
├── styles.css          # All styling
├── firestore.rules     # Firestore security rules
├── profile.jpg         # Portrait
├── sitemap.xml
├── robots.txt
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

### Sikkerhetsregler

Firestore Security Rules er definert i `firestore.rules` og må deployes til Firebase:

```bash
npx firebase-tools login          # første gang
npx firebase-tools deploy --only firestore:rules
```

Prosjektet (`quister-homepage`) er satt i `.firebaserc`, og `firebase.json` peker på `firestore.rules`.

Reglene sikrer at:
- Alle kan lese meldinger
- Kun gyldige meldinger kan opprettes (navn 1-50 tegn, melding 1-500 tegn, `createdAt` må være serverens tidspunkt)
- Meldinger kan ikke oppdateres eller slettes via klienten
