# CLAUDE.md

This file provides guidance for AI assistants working with this repository.

## Project Overview

This is a **static HTML/CSS GitHub Pages starter website** — a minimal beginner template from GitHub designed to introduce new users to Git, GitHub, and GitHub Pages hosting.

**Live URL:** Served directly via GitHub Pages (no build step required).

## Repository Structure

```
hello-world/
├── index.html          # Main webpage (entry point)
├── styles.css          # Global stylesheet
├── images/
│   └── create-octocat.png  # Example image for Octocat customization
└── README.md           # Beginner-oriented tutorial for GitHub Pages
```

## Technology Stack

- **HTML5** — no templating engine or preprocessor
- **CSS3** — plain CSS, no Sass/Less/PostCSS
- **No JavaScript**
- **No dependencies** — no package.json, no node_modules, no build tools

## Development Workflow

### Viewing the site locally

Open `index.html` directly in a browser — no server or build step is needed:

```bash
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

### Making changes

Edit `index.html` or `styles.css` directly. Changes are reflected immediately on reload.

### Deploying

Deployment is handled automatically by GitHub Pages when changes are pushed to the configured branch (typically `master` or `main`) in the repository settings. There is no CI/CD pipeline or manual deploy step.

## Key Files

### `index.html`

The sole HTML page. Notable details:
- References an external Octocat GIF from the GitHub CDN (`octodex.github.com`)
- Contains an HTML comment indicating where to paste a custom Octocat template (line 15)
- The `<LINK>` tag for CSS uses uppercase (intentional in the original template)

### `styles.css`

Minimal stylesheet with:
- A global CSS reset (`margin: 0; padding: 0` on `*`)
- Centered layout for the `#octocat` image (384px width, 50px auto margins)
- Monospace paragraph styling (30px Monaco/Courier New font stack)

### `images/create-octocat.png`

An example Octocat image included for the customization tutorial. It is **not referenced** in the current `index.html` — the HTML links to an external CDN image instead.

## Conventions

- **No linting or formatting tools** are configured. Keep HTML and CSS clean and readable.
- **No testing framework** exists. Validate changes by opening the HTML in a browser.
- **Avoid adding unnecessary complexity** — this project is intentionally minimal. Do not introduce build tools, frameworks, or dependencies unless explicitly requested.
- When editing HTML, preserve the existing structure and comments for educational clarity.

## Git Workflow

- The primary branch is `master`.
- Feature or task branches should follow the naming pattern used by the project (e.g., `claude/<task-id>`).
- Commit messages should be short and descriptive (imperative mood preferred).
- There are no pre-commit hooks, linters, or automated checks — all commits go through directly.

## No Build, Test, or Lint Commands

This project has none of the following:
- `npm install` / `npm run build` / `npm test`
- `make` targets
- Linter configurations (ESLint, Prettier, Stylelint)
- Test runners (Jest, Mocha, Vitest, Playwright)

If any of these are needed in the future, add them along with appropriate configuration files and update this document.
