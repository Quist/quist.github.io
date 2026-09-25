# GitHub Copilot Review Instructions

This file provides guidance for GitHub Copilot when reviewing pull requests in this repository.

## Language Instructions

**Use Norwegian (bokmål) for all interactions in this repository:**
- Pull request reviews should be written in Norwegian
- Commit messages should be in Norwegian  
- Comments and suggestions should be in Norwegian
- Code review feedback should be in Norwegian

**Example phrases to use:**
- "✅ Ser bra ut!" instead of "✅ Looks good!"
- "❌ Dette endrer..." instead of "❌ This change..."
- "Forslag:" instead of "Suggestion:"
- "Godkjent med forslag:" instead of "Approved with suggestion:"

## Project Context

This is a personal portfolio website for Joakim Lindquister - a static HTML/CSS site hosted on GitHub Pages. The focus is on simplicity, clean code, and functional design.

## Review Philosophy

**Approve unless something is seriously wrong.** This project values:
- Functional style and best practices
- Code cleanliness and maintainability
- Working functionality over perfection

## Review Criteria

### Code Cleanliness ✨

**Must Review:**
- HTML semantic structure and accessibility
- CSS organization and naming conventions
- Consistent indentation and formatting
- No duplicate or redundant code
- Proper use of CSS classes vs IDs

**Approve if:**
- Code follows existing patterns in the repository
- Changes maintain or improve readability
- No obvious syntax errors or typos

**Reject only if:**
- Code introduces security vulnerabilities
- HTML is malformed or breaks accessibility
- CSS changes break the responsive design
- Changes would break the GitHub Pages deployment

### Functionality 🚀

**Must Review:**
- Links work correctly and open in appropriate targets
- Responsive design is maintained across screen sizes
- CSS animations and transitions function properly
- Meta tags and SEO elements are correct
- Font loading and asset references are valid

**Approve if:**
- New features work as intended
- Changes don't break existing functionality
- Performance is maintained or improved
- Visual design stays consistent with established theme

**Reject only if:**
- Changes break core navigation or contact functionality
- Responsive design is significantly damaged
- Page loading is severely impacted
- Accessibility is reduced

### Functional Style & Best Practices 💡

**Prefer:**
- Semantic HTML5 elements over generic divs
- CSS Grid/Flexbox over float-based layouts  
- Progressive enhancement approach
- Mobile-first responsive design
- Minimal, clean CSS without excessive specificity
- Consistent naming conventions (kebab-case for CSS classes)
- Logical grouping of CSS rules

**Design System Adherence:**
- Fonts: Geist (body), Instrument Serif (headings), JetBrains Mono (labels), Caveat (handwritten details)
- Colors: Light paper theme defined as oklch tokens on `body` in `styles.css` (`--bg`, `--fg`, `--accent` etc.)
- Layout: Sections up to 1100px wide, text blocks narrower
- Hover effects: Smooth transitions and subtle animations

### Specific to This Project

**File Structure:**
- `index.html` - Main portfolio page
- `gjestebok.html` - Guestbook backed by Firebase Firestore
- `styles.css` - All styling (no CSS frameworks), shared by both pages
- `firestore.rules` - Firestore security rules for the guestbook
- `CLAUDE.md` - Development guidance (update if needed)

**Key Features to Preserve:**
- Personal introduction and photo
- Work experience and projects section
- Contact links (GitHub, LinkedIn, Email)
- Guestbook links in the nav and teaser section
- Light paper theme with tape and handwriting details
- Content must stay visible without JavaScript (reveal animations only apply under `.js`)
- Mobile responsiveness

## Auto-Approval Guidelines

**Automatically approve PRs that:**
- Fix typos or update content
- Improve accessibility without breaking design
- Optimize CSS without changing visual appearance
- Update personal information or project descriptions
- Add new projects following existing card pattern
- Improve SEO meta tags
- Fix broken links or update URLs

**Request changes only for:**
- Security issues (XSS vulnerabilities, etc.)
- Broken functionality that affects user experience
- Major design changes that don't follow existing patterns
- Changes that break GitHub Pages deployment
- Code that significantly hurts performance
- Accessibility regressions

## Review Tone

Keep reviews constructive and focused on the user's preferences **in Norwegian**:
- Acknowledge good practices and improvements (anerkjenn gode praksis og forbedringer)
- Suggest alternatives for functional style approaches (foreslå alternativer for funksjonelle stilmetoder)
- Focus on functionality over stylistic preferences (fokuser på funksjonalitet fremfor stilistiske preferanser)
- Provide specific, actionable feedback when requesting changes (gi spesifikk, handlingsrettet tilbakemelding ved endringsforespørsler)
- Remember this is a personal portfolio - perfection isn't required (husk at dette er en personlig portefølje - perfeksjon er ikke nødvendig)

## Example Review Comments

**For Approval:**
"✅ Ser bra ut! Det nye prosjektkortet følger eksisterende mønster og opprettholder designkonsistensen. Den semantiske HTML-en og rene CSS-en er i tråd med funksjonelle stilpreferanser."

**For Minor Suggestions:**
"✅ Godkjenner med forslag: Vurder å bruke CSS Grid i stedet for float for dette layoutet - det ville vært mer vedlikeholdbart og følge moderne beste praksis. Men nåværende tilnærming fungerer fint!"

**For Requesting Changes:**
"❌ Denne endringen ødelegger det responsive designet for mobil. Navigasjonslenkene overlapper ved skjermbredder under 768px. Vennligst test på mindre skjermer og juster CSS media queries."