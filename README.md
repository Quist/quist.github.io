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