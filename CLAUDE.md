# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Language Instructions

**Bruk norsk (bokmål) for alle interaksjoner i dette repositoryet:**
- Pull request-beskrivelser skal skrives på norsk
- Commit-meldinger skal være på norsk
- Kommentarer og forslag skal være på norsk
- Kode-review tilbakemeldinger skal være på norsk
- Progress reports skal være på norsk

**Eksempel på fraser å bruke:**
- "Legger til" i stedet for "Adding"
- "Fikser" i stedet for "Fixing"  
- "Oppdaterer" i stedet for "Updating"
- "Forbedrer" i stedet for "Improving"

## Prosjektoversikt

Dette er en personlig porteføljenettside for Joakim Lindquister hostet på GitHub Pages. Det er en statisk side uten build-prosess:

- `index.html` - Forsiden med intro, «Nå», prosjekter og kontakt
- `gjestebok.html` - Gjestebok som lagrer hilsener i Firebase Firestore (SDK lastes fra CDN)
- `styles.css` - All styling, delt av begge sidene
- `firestore.rules` - Sikkerhetsregler for gjesteboken (deployes manuelt med `npx firebase-tools deploy --only firestore:rules`, konfigurert i `firebase.json` og `.firebaserc`)
- `sitemap.xml`, `robots.txt` - SEO
- `.github/workflows/pr-validation.yml` - Lager en nedlastbar forhåndsvisning for hver PR

## Utvikling

Endringer gjøres direkte i filene. Åpne `index.html` i nettleseren for å teste. Metadata og font-lenker i `<head>` er duplisert i begge HTML-filene, så endringer der må gjøres begge steder.

## Distribusjon

Endringer som pushes til `master` blir automatisk distribuert via GitHub Pages (quist.github.io).

## Designsystem

- Fonter (Google Fonts): Geist (brødtekst), Instrument Serif (overskrifter), JetBrains Mono (etiketter), Caveat (håndskrift-detaljer)
- Farger: Lyst «papir»-tema definert som oklch-variabler på `body` i `styles.css` (`--bg`, `--paper`, `--fg`, `--muted`, `--line`, `--accent`). Aksentfargen er rustrød.
- Layout: Seksjoner opptil 1100px brede, tekstblokker smalere
- Detaljer: Portrett med tape, håndskrevet signatur, kort med lett rotasjon
- Animasjon: Elementer med `data-reveal` fades inn ved scroll. De skjules bare når `<html>` har klassen `js`, så innholdet vises uten JavaScript. Respekterer `prefers-reduced-motion`.
- Tekst: Kort og direkte. Unngå floskler og pynt.
