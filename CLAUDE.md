# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal portfolio website for Joakim Lindquister hosted on GitHub Pages. It's a simple static site with two main files:

- `index.html` - Single page with personal introduction and navigation links
- `styles.css` - Styling with dark theme (#211f1d background, #f8b92e accent color)

## Development

This is a static HTML/CSS website with no build process or dependencies. Changes can be made directly to the files and will be reflected immediately when the site is served.

## Deployment

**Production:** The site is hosted via GitHub Pages (quist.github.io). Changes pushed to the master branch are automatically deployed.

**PR Previews:** Pull requests automatically trigger a preview build workflow:
- HTML/CSS validation 
- Preview build creation with PR indicators
- Downloadable artifact with testing instructions
- Automated PR comments with links

See `.github/workflows/pr-validation.yml` for the complete workflow.

## Design System

- Font: Inter (loaded from Google Fonts) 
- Theme colors: Dark gradient background (#1a1a1a to #2a2a2a), white text (#ffffff)
- Accent colors: Orange/yellow gradients (#f39c12, #e67e22)
- Layout: Centered container (max-width: 700px) with flexbox
- Cards: Glass morphism effect with backdrop-filter
- Navigation: Horizontal link buttons with hover effects