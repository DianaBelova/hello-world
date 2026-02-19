# CLAUDE.md

This file provides guidance for AI assistants working with this repository.

## Project Overview

This repository began as a **static HTML/CSS GitHub Pages starter** (a minimal beginner template from GitHub) and has since grown to include a **BookRetreats.com UI prototype** — a set of self-contained HTML pages mocking a retreat-booking platform. All pages are pure HTML/CSS with no build step.

**Live URL:** Served directly via GitHub Pages (no build step required).

## Repository Structure

```
hello-world/
├── index.html              # Original GitHub Pages starter (Octocat landing page)
├── styles.css              # Stylesheet for index.html only
├── booking-summary.html    # BookRetreats: booking summary page (inline CSS)
├── messaging.html          # BookRetreats: inbox/messaging page (inline CSS)
├── images/
│   └── create-octocat.png  # Example image for Octocat customization (not used in HTML)
└── README.md               # Beginner-oriented tutorial for GitHub Pages
```

## Technology Stack

- **HTML5** — no templating engine or preprocessor
- **CSS3** — plain CSS; `index.html` uses an external `styles.css`; the BookRetreats pages use inline `<style>` blocks
- **No JavaScript** — except one `onclick="window.location.href=..."` inline handler in `booking-summary.html`
- **No dependencies** — no package.json, no node_modules, no build tools

## Pages

### `index.html` — GitHub Pages Starter

The original one-page starter site. Notable details:
- References an external Octocat GIF from the GitHub CDN (`octodex.github.com`)
- Styled by the external `styles.css` file
- Contains an HTML comment at line 14 indicating where to paste a custom Octocat template
- The `<LINK>` tag for CSS uses uppercase (intentional in the original template)

### `styles.css`

Minimal stylesheet for `index.html` only. Contains:
- A global CSS reset (`margin: 0; padding: 0` on `*`)
- Centered layout for the `#octocat` image (384px width, 50px auto margins)
- Monospace paragraph styling (30px Monaco/Courier New font stack)

### `booking-summary.html` — BookRetreats Booking Summary

A self-contained UI prototype page. All CSS is inline in a `<style>` block. Displays:
- A sticky header with the BookRetreats.com logo, navigation (Inbox, Bookings, My Retreats, My Vouchers), and a user avatar button ("Diana")
- Three info cards: Address (San Gimignano, Tuscany), Arrival (Feb 26th 2026), Departure (Mar 8th 2026)
- A booking details card with guest, status badge, accommodation, addons, amount paid (US$ 200), and remaining balance (€ 675 / US$ 800)
- A sticky sidebar with action buttons: Message Host (links to `messaging.html`), Receipt, Change Arrival Date, Cancel
- Responsive breakpoints at 900px (single-column) and 640px (hide nav)

### `messaging.html` — BookRetreats Inbox / Messaging

A self-contained UI prototype page. All CSS is inline in a `<style>` block. Displays:
- Same sticky header as `booking-summary.html`
- A two-column layout: left panel (message thread) and right panel (booking details sidebar)
- A booking confirmation message bubble showing the full financial breakdown (deposit US$ 200, remaining US$ 800, total US$ 1000)
- A message input bar with a send button (static, not functional)
- Right sidebar with retreat details, a placeholder image (Wikipedia cat image), and a FAQ accordion (static, no JS expand/collapse)
- A sticky bottom bar: "Why wait? Spots are limited." with a "Book Again" button
- Responsive breakpoints at 900px and 640px

### `images/create-octocat.png`

An example Octocat image included for the customization tutorial. It is **not referenced** in any HTML page — `index.html` links to an external CDN image instead.

## Design Language (BookRetreats pages)

Both `booking-summary.html` and `messaging.html` share:
- **Primary color:** `#0066cc` (blue)
- **Background:** `#f7f7f7`
- **Font stack:** `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif`
- **Max content width:** 1200px centered
- **Header height:** 64px, sticky with `z-index: 100`
- **Card style:** white background, `1px solid #e5e5e5` border, `border-radius: 10px`, subtle box-shadow

The two pages cross-link via `<a href="messaging.html">` and `<a href="booking-summary.html">` in navigation and back-links.

## Development Workflow

### Viewing the site locally

Open any HTML file directly in a browser — no server or build step is needed:

```bash
open index.html              # macOS
open booking-summary.html    # macOS
xdg-open index.html          # Linux
start index.html             # Windows
```

### Making changes

- For `index.html`: edit the file and `styles.css` directly.
- For `booking-summary.html` / `messaging.html`: all CSS is in the `<style>` block inside each file. Edit inline.
- Changes are reflected immediately on browser reload.

### Deploying

Deployment is handled automatically by GitHub Pages when changes are pushed to the configured branch (typically `master`). There is no CI/CD pipeline or manual deploy step.

## Conventions

- **No linting or formatting tools** are configured. Keep HTML and CSS clean and readable.
- **No testing framework** exists. Validate changes by opening the HTML in a browser.
- **Inline CSS pattern:** The BookRetreats pages keep all styles in a `<style>` block in the `<head>`. Do not introduce external CSS files for these pages without explicit instruction.
- **No JavaScript:** The project intentionally avoids JS. The one `onclick` in `booking-summary.html` is the only scripting present. Do not add JS unless explicitly requested.
- **Avoid adding unnecessary complexity** — this project is intentionally minimal. Do not introduce build tools, frameworks, or dependencies unless explicitly requested.
- When editing HTML, preserve existing structure and comments for educational clarity.

## Git Workflow

- The primary branch is `master`.
- Feature or task branches follow the naming pattern `claude/<task-id>`.
- Commit messages should be short and descriptive (imperative mood preferred).
- There are no pre-commit hooks, linters, or automated checks — all commits go through directly.

## No Build, Test, or Lint Commands

This project has none of the following:
- `npm install` / `npm run build` / `npm test`
- `make` targets
- Linter configurations (ESLint, Prettier, Stylelint)
- Test runners (Jest, Mocha, Vitest, Playwright)

If any of these are needed in the future, add them along with appropriate configuration files and update this document.
