# GitHub Copilot Review Instructions

This file provides guidance for GitHub Copilot when reviewing pull requests in this repository.

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
- Font: Inter (currently used, was Roboto in docs)
- Colors: Dark theme with light text (#ffffff on dark backgrounds)
- Layout: Centered container with appropriate margins
- Hover effects: Smooth transitions and subtle animations

### Specific to This Project

**File Structure:**
- `index.html` - Main portfolio page
- `styles.css` - All styling (no CSS frameworks)
- `CLAUDE.md` - Development guidance (update if needed)

**Key Features to Preserve:**
- Personal introduction and photo
- Work experience and projects section
- Contact links (GitHub, LinkedIn, Email)
- Dark theme with gradient background
- Card-based layout with subtle effects
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

Keep reviews constructive and focused on the user's preferences:
- Acknowledge good practices and improvements
- Suggest alternatives for functional style approaches
- Focus on functionality over stylistic preferences
- Provide specific, actionable feedback when requesting changes
- Remember this is a personal portfolio - perfection isn't required

## Example Review Comments

**For Approval:**
"✅ Looks good! The new project card follows the existing pattern and maintains the design consistency. The semantic HTML and clean CSS align well with the functional style preferences."

**For Minor Suggestions:**
"✅ Approving with a suggestion: Consider using CSS Grid instead of float for this layout - it would be more maintainable and follow modern best practices. But the current approach works fine!"

**For Requesting Changes:**
"❌ This change breaks the mobile responsive design. The navigation links overlap at screen widths below 768px. Please test on smaller screens and adjust the CSS media queries."