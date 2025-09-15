# Theatre1 Website

A simple, static website for Theatre1 to promote upcoming and past performances and introduce the founders. The current homepage highlights the production “High Fidelity – A New Musical,” with links to past performances and founders.

## Features
- Home hero with poster, dates, venue, and ticket link
- Sections for past performances and founders with images and bios
- Dark theme styling and responsive layout via Tailwind CSS CDN
- Fully static: no server, database, or build step required

## Tech Stack
- HTML: Single page in `index.html` with three sections (Home, Past, Founders)
- CSS: Tailwind CSS via CDN (`https://cdn.tailwindcss.com`), dark mode enabled with `class` strategy
- JavaScript: Small inline script for client-side section switching (vanilla JS)
- Assets: Images and icons in `assets/`
- Hosting: Suitable for any static host; repo includes `CNAME` for a GitHub Pages custom domain (`theatre1.org.uk`)

## Project Structure
- `index.html` — Main site markup, Tailwind CDN, inline navigation script
- `assets/` — Posters, headshots, logos, and PWA icons; includes `site.webmanifest`
- `CNAME` — Custom domain for GitHub Pages (`theatre1.org.uk`)
- `README.txt` — Original simple notes (superseded by this `README.md`)

## How It Works
- Navigation links (`Home`, `Past Performances`, `Founders`) are normal anchors, but a small script intercepts clicks and toggles which `<section>` is visible. There are no separate `past.html` or `founders.html` pages; all content lives in `index.html`.
- Tailwind is configured via CDN with `darkMode: 'class'`, and the `<html>` tag includes `class="dark"` to enable the dark theme.

## Local Development
1. Clone or download the repository.
2. Open `index.html` directly in your browser (no server required).

Optional: If you prefer a local server for better caching/paths, run any static server (e.g., `python -m http.server 8080`) and open `http://localhost:8080`.

## Deployment
- GitHub Pages: Push to the repo’s default branch. With `CNAME` present, Pages will serve at `https://theatre1.org.uk/` once DNS is configured.
- Alternatives: Netlify, Vercel, Cloudflare Pages, or any static host; just deploy the root folder.

## Editing Content
- Update show details, dates, and links in `index.html` (hero section)
- Add/remove past performances by duplicating the existing card pattern under the `Past Performances` section
- Update founders’ bios and images in the `Founders` section; headshots live in `assets/`

## Notes & Considerations
- Direct navigation to `past.html` or `founders.html` will 404 on static hosts because those files do not exist; the inline JS handles section toggling only after the homepage loads. Consider converting to real routes or hash-based URLs if deep links are needed.
- The `site.webmanifest` references icon paths at the root (`/android-chrome-*.png`) while icons are stored under `assets/`. Update paths if enabling PWA installability.
- Tailwind via CDN is convenient for a small static site. For larger sites or custom design systems, consider a build step with Tailwind CLI or a bundler to enable tree-shaking and custom config.

