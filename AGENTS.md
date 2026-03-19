# AGENTS.md

This file provides guidance for AI coding agents operating in this repository.

## Project Overview

This is **ringo-intro**, a minimal static personal landing page for "Ringo," an
AI assistant in the `togusj` GitHub org. The entire project is a single
self-contained HTML file with inline CSS. There are no JavaScript frameworks,
build tools, package managers, or external dependencies.

- **Repository:** `https://github.com/togusj/ringo-intro.git`
- **Primary file:** `index.html`
- **Tech stack:** Plain HTML5 + CSS3 (no JS, no frameworks)

## Build / Lint / Test Commands

There is **no build system, linter, or test runner** configured for this project.

### Viewing the site

Open `index.html` directly in a browser:

```sh
open index.html        # macOS
xdg-open index.html    # Linux
```

### Validation (manual)

Since there are no automated tools, validate HTML manually if needed:

```sh
# Using the W3C Nu HTML Checker (requires network)
curl -s -H "Content-Type: text/html; charset=utf-8" \
  --data-binary @index.html \
  https://validator.w3.org/nu/?out=text

# Or use a local tool if available
npx html-validate index.html    # requires Node.js
```

### Running a single test

There are no tests. If tests are added in the future, document the single-test
command here. For a static HTML project, "testing" means visually inspecting the
page in a browser and validating the markup.

## Project Structure

```
ringo-intro/
├── AGENTS.md           # This file (agent instructions)
├── index.html          # The entire site (HTML + inline CSS)
└── .git/               # Git internals
```

There are no other configuration files: no `.gitignore`, no `package.json`,
no CI/CD workflows, no editor configs, no Cursor/Copilot rule files.

## Code Style Guidelines

### HTML

- Use HTML5 doctype: `<!DOCTYPE html>`
- Set `lang="en"` on the `<html>` element
- Include `<meta charset="UTF-8" />` and viewport meta tag
- Use self-closing syntax for void elements (e.g., `<meta ... />`)
- Use semantic HTML elements (`<main>`, `<section>`, `<header>`, etc.)
- Use `aria-hidden="true"` on purely decorative elements
- Indent with **2 spaces** (no tabs)
- Keep lines under 100 characters where practical

### CSS

- All CSS is **inline** in a `<style>` block in `<head>` (no external stylesheets)
- Use **CSS custom properties** (variables) defined on `:root` for theming:
  ```css
  :root {
    --apple-red: #b91c1c;
    --apple-red-deep: #7f1d1d;
    --apple-blush: #ffe4e6;
    --ink: #111827;
    --soft-ink: #374151;
  }
  ```
- Apply `box-sizing: border-box` globally via `* { box-sizing: border-box; }`
- Use the system font stack: `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif`
- Use `clamp()` for responsive typography (e.g., `font-size: clamp(2.4rem, 4vw, 3.2rem)`)
- Use `rem` units for font sizes and spacing
- Prefer `rgba()` for colors with transparency
- Use `radial-gradient` and `backdrop-filter` for visual effects
- Keep selectors simple: class-based (`.card`, `.accent`) or element-based (`h1`, `p`)
- No BEM or other naming methodology is in use; keep class names short and descriptive

### Naming Conventions

- CSS class names: lowercase, hyphen-separated (e.g., `apple-mark`, `soft-ink`)
- CSS custom properties: lowercase, hyphen-separated with `--` prefix
- Keep names semantic and descriptive of purpose, not appearance

### Formatting

- **Indentation:** 2 spaces throughout (HTML and CSS)
- **Quotes:** Double quotes for HTML attributes
- **Trailing whitespace:** None
- **Final newline:** End files with a newline
- **CSS declarations:** One property per line, opening brace on same line as selector
- **CSS values:** Space after colons, semicolon after every declaration

### Design Theme

The site uses an **apple/fruit theme** with a red-and-blush color palette:
- Primary: `#b91c1c` (apple red)
- Deep accent: `#7f1d1d`
- Blush/background: `#ffe4e6`, `#fff1f2`, `#fff7f7`
- Text: `#111827` (dark), `#374151` (soft), `#6b7280` (muted)

Maintain this color palette when making changes. Use the existing CSS custom
properties rather than hardcoding new color values.

### Error Handling

Not applicable for a static HTML page. If JavaScript is added in the future:
- Use `try/catch` for async operations
- Provide user-facing error messages
- Log errors to the console in development

## Git Conventions

- **Branch naming:** Use descriptive names with slashes (e.g., `apple-fruit-theme`,
  `cursor/development-environment-setup-03d4`)
- **Commit messages:** Short imperative descriptions (e.g., "Initial Ringo intro site",
  "Redesign intro page with minimal apple theme")
- **PRs:** Use merge commits from feature branches into `main`

## Important Notes for Agents

1. **This is a single-file project.** All changes go into `index.html` unless
   there is a specific reason to add new files (e.g., images, a favicon).
2. **No build step required.** Changes are immediately visible by refreshing
   the browser.
3. **No dependencies to install.** Do not add `package.json` or other tooling
   unless explicitly requested.
4. **Keep it simple.** The project's philosophy is minimal and self-contained.
   Avoid introducing complexity, frameworks, or build tools without clear need.
5. **Preserve the visual design.** The apple/fruit theme and card-based layout
   are intentional. Maintain the existing aesthetic when making changes.
6. **Accessibility matters.** Use semantic HTML, appropriate ARIA attributes,
   and ensure adequate color contrast.
7. **Responsive design.** The page uses viewport-relative units and `clamp()`
   for responsiveness. Test changes at multiple viewport widths.
8. **No external Cursor, Copilot, or other agent rule files exist.** This
   AGENTS.md is the sole source of agent instructions for the repository.
