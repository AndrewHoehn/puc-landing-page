# Pullman Urgent Care — Coming Soon

Static coming-soon landing page for [Pullman Urgent Care](https://pullmanurgentcare.com), a new walk-in clinic opening fall 2026 at 421 NE Stadium Way, Pullman, WA.

**Live preview:** https://andrewhoehn.github.io/puc-landing-page/

## Stack

- HTML + CSS — no framework, no build step
- [Leaflet](https://leafletjs.com/) + [Mapbox Dark v10](https://www.mapbox.com/maps/dark) for the location map
- [Fraunces](https://fonts.google.com/specimen/Fraunces) + [Inter Tight](https://fonts.google.com/specimen/Inter+Tight) via Google Fonts

## Local dev

No dependencies. Just serve the folder:

```
python3 -m http.server 8000
# → http://localhost:8000
```

Or open `index.html` directly in a browser.

## Deploying

Any static host works (Netlify, Vercel, Cloudflare Pages, S3, GitHub Pages). Upload the repo root — nothing to build.

## Notes

- `MedicalClinic` / `Organization` / `WebSite` JSON-LD structured data lives in `<head>` for search + AI indexing.
- `robots.txt` allows major AI crawlers (GPTBot, ClaudeBot, Google-Extended, PerplexityBot).
- Mapbox token in `index.html` is URL-restricted at the Mapbox dashboard.
- When a custom domain is wired up, update the canonical URL in `index.html` and the `<loc>` entries in `sitemap.xml`.
