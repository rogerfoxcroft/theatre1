# Theatre1 Website

A static, multi-page site highlighting Theatre1’s upcoming production and company history. The current season promotes **If/Then**, with archive and founders content on dedicated pages.

## Current Structure

| File | Purpose |
| --- | --- |
| `index.html` | Homepage hero for *If/Then*, CTA, production copy, navigation |
| `past.html` | Featured recap of *Songs for a New Decade* plus reverse-chronological archive cards |
| `founders.html` | Grid of founder bios and headshots |
| `assets/` | Posters, headshots, favicons (`site.webmanifest`, PWA icons, logo, etc.) |
| `CNAME` | Points GitHub Pages to `theatre1.org.uk` |
| `README.txt` | Legacy setup notes (kept for reference) |

## Design & Styling Notes

- **Palette:** Burgundy/gold scheme derived from the If/Then artwork, configured via Tailwind CDN (`brand.*` colors in each HTML head). All pages share the same palette and typography via repeated config blocks.
- **Layout:** Responsive Flexbox—homepage stacks on mobile and uses a split image/text layout on desktop (`flex-col lg:flex-row`). Past and founders pages use grid layouts with consistent card styling.
- **Interactive Elements:**
  - “Buy Tickets” button triggers an `alert('Tickets on sale soon')` placeholder instead of navigating.
  - No other JavaScript beyond the Tailwind CDN (purely static pages).

## Editing Guidelines

1. **Update hero show details** in `index.html` (poster path, copy, CTA behavior). Keep desktop/mobile layout classes aligned.
2. **Past performances** live in two blocks:
   - Featured spotlight (currently *Songs for a New Decade*) near the top of `past.html`.
   - Archive grid listed newest → oldest. Duplicate an existing card and adjust poster/metadata when adding a show; maintain ordering manually.
3. **Founders** cards in `founders.html` mirror each other—duplicate a card block for new bios and add the portrait to `assets/`.
4. **Palette changes** require updating the Tailwind config in each HTML head (it’s inlined three times). Consider centralizing in the future if the palette will change often.

## Development & Deployment

- Fully static; open the HTML files directly or run a lightweight static server (e.g., `python3 -m http.server 8080`).
- Hosted via GitHub Pages (custom domain set by `CNAME`). Deploy by pushing to the default branch; no build step.
- Tailwind is pulled from `https://cdn.tailwindcss.com`. If you need custom plugins or tree-shaking, migrate to a build process.

## Future Considerations

- Consolidate repeated Tailwind config into a shared layout or build step to avoid manual sync across pages.
- Replace the alert-based CTA with a proper modal or ticketing link once on-sale info is available.
- Introduce routing or a generator if additional pages (news, galleries, etc.) are planned, so shared navigation/footer logic isn’t duplicated.
