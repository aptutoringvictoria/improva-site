# Improva — launch website

A small, self-contained **static website** for the Improva iOS app:
a marketing landing page plus the three App-Store-required pages (Privacy,
Terms, Support). Hand-coded HTML/CSS, **no framework, no build step, no
trackers**. Works with JavaScript disabled.

## Files

```
website/
  index.html      Landing page (full feature breadth + JSON-LD + optional notify)
  privacy.html    Privacy Policy (shell — paste content in)
  terms.html      Terms of Use (shell — paste content in)
  support.html    Support / contact + FAQ
  404.html        Friendly styled 404 (GitHub Pages serves it automatically)
  robots.txt      Allow all + sitemap pointer
  sitemap.xml     index / support / privacy / terms
  style.css       Shared theme (green #39D353 / indigo #5B5FEF)
  assets/         Generated SVG brand assets + placeholder image slots
    logo.svg        Header brand mark (generated placeholder — swappable)
    favicon.svg     Favicon (generated placeholder — swappable)
    og-image.svg    1200x630 social image (generated; export to PNG for scrapers)
    README.txt      What to add / swap before launch
  README.md       This file
```

All pages are static HTML/CSS, work with JavaScript disabled, and carry a
consistent header/footer, a health/fitness disclaimer, and `theme-color` /
canonical / Open Graph / Twitter meta. The landing page adds `SoftwareApplication`
+ `Organization` JSON-LD for richer search results.

There is no build step. Open `index.html` in a browser to preview locally, or
run a tiny static server from the `website/` folder:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Deploy to GitHub Pages (free)

1. Create a new GitHub repository (e.g. `fitness-locker-site`). This is a
   separate project from the iOS app — do not add it to the app repo.
2. Put the site at the repo root (or in a `/docs` folder). If you want the repo
   root served, move the contents of `website/` to the repo root; if you prefer
   `/docs`, copy `website/` to `docs/`.
3. Commit and push:
   ```bash
   git init
   git add .
   git commit -m "Improva launch site"
   git branch -M main
   git remote add origin git@github.com:<you>/fitness-locker-site.git
   git push -u origin main
   ```
4. In the repo: **Settings → Pages**. Under "Build and deployment", set
   **Source: Deploy from a branch**, pick **Branch: `main`** and the folder
   (**`/root`** or **`/docs`** to match step 2). Save.
5. Wait ~1 minute. Your site is live at
   `https://<you>.github.io/fitness-locker-site/`.

### Custom domain (later)

When you have a domain: in **Settings → Pages → Custom domain**, enter it and
save (this adds a `CNAME` file). Then create a DNS record at your registrar —
a `CNAME` to `<you>.github.io` for a subdomain like `www`, or the four GitHub
Pages `A` records for an apex domain. Tick **Enforce HTTPS** once the
certificate is issued.

## Find-replace TODO list (before launch)

Everything not yet finalised is a clearly-marked placeholder. Search the whole
`website/` folder for `TODO` to find each one. In order:

1. **Domain — DONE 2026-09-10 (`https://improva.fit`).** Was: replace the placeholder domain
   everywhere — canonical links + Open Graph / Twitter URLs + JSON-LD `url`s in
   `index.html`, plus `robots.txt` (the `Sitemap:` line) and `sitemap.xml` (the
   `<loc>` entries). One find-replace covers most; check `robots.txt` /
   `sitemap.xml` separately.
2. **Support email — DONE 2026-09-10 (`support@improva.fit`).** Was: confirm or replace the placeholder (footer +
   support page mailto + the optional notify mailto). Matches the app's
   `LegalLinks` placeholder.
3. **Brand assets.** `assets/logo.svg`, `favicon.svg`, and `og-image.svg` are
   generated placeholders in the app palette — swap them for the real app icon
   whenever ready (keep the filenames or update the references). Also add a PNG
   `og-image.png` (safest for social scrapers), `favicon.png`, and
   `apple-touch-icon.png` — the pages already link them as fallbacks/TODO.
4. **Screenshots.** Add `app-icon.png` + `screenshot-1..4.png` to `assets/`,
   then swap the placeholder `<div class="placeholder …">` boxes in `index.html`
   (hero + "A look inside" gallery) for `<img>` tags (keep the `alt` text). See
   `assets/README.txt`.
5. **App Store link.** Once the app is live, turn the "Coming to the App Store"
   badge in `index.html` into a real link/badge pointing at the App Store URL.
6. **Legal copy.** Paste the finalised Privacy Policy and Terms drafts into the
   `<!-- CONTENT: … -->` blocks in `privacy.html` / `terms.html`, and set the
   "Last updated: [DATE]" line on each.
7. **Optional — notify at launch.** `index.html` has a "Get notified at launch"
   section using a `mailto:` (no backend). To collect emails instead, uncomment
   the Formspree `<form>` and set a real form ID, or delete the section. No
   trackers either way.

## No analytics — by design

The site ships with **no analytics, no trackers, no third-party scripts, and no
cookies**, to match the app's local-only / no-tracking ethos and keep the
Privacy Policy honest. If you ever want traffic stats, a privacy-friendly,
cookieless option such as [Plausible](https://plausible.io) could be added — but
the site ships with none.
