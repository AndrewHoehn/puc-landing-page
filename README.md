# Pullman Urgent Care — Coming Soon

Static coming-soon landing page for [Pullman Urgent Care](https://pullmanurgentcare.com), a new walk-in clinic opening fall 2026 at 421 NE Stadium Way, Pullman, WA.

**Live site:** https://pullmanurgentcare.com
**Repo:** https://github.com/AndrewHoehn/puc-landing-page

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

Production (`pullmanurgentcare.com`) is hosted on a **Cloudflare Worker** (static-assets type), project **`pullman-urgent-care`** in the `andrew.hoehn@gmail.com` Cloudflare account. The Worker is connected to this GitHub repo and builds from `main`, so:

- **Pushing to `main` auto-deploys to production.** No build step — the repo root is served as static assets.
- Workers.dev URL: `pullman-urgent-care.andrew-hoehn.workers.dev`
- Custom domains: `pullmanurgentcare.com` (+ `www`).
- A GitHub Pages copy also exists at https://andrewhoehn.github.io/puc-landing-page/ — it's a leftover preview surface, **not** production.

Any static host works as an alternative (Netlify, Vercel, Cloudflare Pages, S3, GitHub Pages) — upload the repo root, nothing to build.

## Email signatures

HTML email-signature install pages live in `signatures/`. Each is a standalone page (open in a browser, copy the card, paste into Gmail). Because they deploy with the site, each is reachable at a URL — e.g. https://pullmanurgentcare.com/signatures/shauna.html — for sending directly to staff.

These are intentionally **unlisted**: not linked from the site, marked `noindex, nofollow`, and disallowed in `robots.txt`. They are *not* password-protected, so treat the URLs as shareable-but-unadvertised. `signatures/_template.html` is the working template and is gitignored (never published).

## Notes

- `MedicalClinic` / `Organization` / `WebSite` JSON-LD structured data lives in `<head>` for search + AI indexing.
- `robots.txt` allows major AI crawlers (GPTBot, ClaudeBot, Google-Extended, PerplexityBot).
- Mapbox token in `index.html` is URL-restricted at the Mapbox dashboard.
- When a custom domain is wired up, update the canonical URL in `index.html` and the `<loc>` entries in `sitemap.xml`.
