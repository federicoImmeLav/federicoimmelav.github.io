# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository

Personal homepage of Federico Pozzi, published via GitHub Pages at `federicoimmelav.github.io`. No build step, no package manager, no test suite — the site is a single self-contained HTML file.

## Development

Open `index.html` directly in a browser to preview. No server required; all CSS and JS are inline.

To preview with a local server (avoids any file:// quirks):

```
npx serve .
# or
python -m http.server 8080
```

Deploy by pushing to the `main` branch — GitHub Pages publishes automatically.

## Architecture

Everything lives in `index.html`:

- **Fonts**: loaded from Google Fonts (`Fraunces`, `JetBrains Mono`, `Nunito`)
- **CSS**: single `<style>` block with CSS custom properties in `:root`
- **JS**: single `<script>` block at the bottom handling:
  - Staggered letter animation for the hero name
  - Terminal typewriter effect
  - Floating code snippets in the hero background
  - IntersectionObserver-based scroll reveal (`.reveal` → `.on`)
  - Nav border tint on scroll

## Design conventions

- Color palette via CSS variables (`--bg-dark`, `--orange`, `--green`, `--cream`, etc.)
- Section numbering: hero → `#chi-sono` (01) → `#cosa-insegno` (02) → `#contatti` (03)
- Reveal animation: add class `reveal` to an element; add `d1`/`d2`/`d3` for staggered delays
- All copy is in Italian
