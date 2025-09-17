# GitHub Copilot Review Instructions

This file provides guidance for GitHub Copilot when reviewing pull requests in this repository.

## Review Criteria

### Code Cleanliness
- **HTML Structure**: Ensure semantic HTML5 elements are used appropriately
- **CSS Organization**: Check for logical grouping of styles and consistent naming conventions
- **Code Formatting**: Verify proper indentation and consistent spacing
- **Accessibility**: Confirm alt text for images, proper heading hierarchy, and semantic markup
- **Performance**: Look for optimized CSS (avoid redundancy, use efficient selectors)

### Functionality Verification
- **Cross-browser Compatibility**: Ensure CSS works across modern browsers
- **Responsive Design**: Verify mobile responsiveness and proper viewport handling
- **Link Functionality**: Check that all navigation links are valid and working
- **Asset Loading**: Confirm external resources (fonts, images) load correctly
- **Page Structure**: Ensure the single-page layout maintains proper flow and readability

### Functional Style & Best Practices
- **CSS Methodology**: Prefer functional CSS patterns and utility-first approaches where appropriate
- **Modern CSS Features**: Encourage use of CSS Grid, Flexbox, and modern properties
- **Maintainable Code**: Look for reusable patterns and consistent design tokens
- **Progressive Enhancement**: Ensure the site works without JavaScript and enhances gracefully
- **Clean Architecture**: Favor separation of concerns between HTML structure and CSS presentation

### Design System Adherence
- **Color Consistency**: Maintain the established dark theme (#1a1a1a background variants)
- **Typography**: Preserve the Inter font family and consistent text hierarchy
- **Spacing**: Use consistent spacing patterns (currently 20px, 30px intervals)
- **Component Patterns**: Keep the card-based layout system intact
- **Hover Effects**: Maintain the established interaction patterns

## Approval Guidelines

**DEFAULT ACTION: APPROVE** unless any of the following serious issues are present:

### Block for Approval (Serious Issues):
- **Broken Functionality**: Changes that break existing features or navigation
- **Security Vulnerabilities**: Introduction of XSS risks or other security issues
- **Accessibility Violations**: Changes that significantly harm screen reader compatibility or keyboard navigation
- **Performance Regression**: Additions that dramatically increase page load time or cause layout shifts
- **Design System Violations**: Changes that fundamentally break the established visual design
- **Code Quality Issues**: Introduction of significant technical debt or unmaintainable patterns

### Minor Issues (Approve with Comments):
- Small formatting inconsistencies
- Minor optimization opportunities
- Suggestion for alternative approaches
- Documentation improvements
- Non-critical accessibility enhancements

## Review Tone
- Be constructive and encouraging
- Focus on the most important issues first
- Provide specific, actionable feedback
- Acknowledge good practices when present
- Remember this is a personal portfolio site - perfection is not required

## Context
This is a static portfolio website with:
- No build process or runtime dependencies
- Direct deployment to GitHub Pages
- Focus on simplicity and maintainability
- Primary goal: showcase developer's work and experience

When in doubt, **approve the pull request** and provide constructive feedback for future improvements.