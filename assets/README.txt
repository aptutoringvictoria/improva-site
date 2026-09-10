Assets folder for the Improva website.

GENERATED PLACEHOLDER BRAND ASSETS (shipped, swappable)
-------------------------------------------------------
These simple SVGs are in the app palette (green #39D353 / indigo #5B5FEF) so
the site looks finished without waiting on a designer. Replace them with the
real app icon / brand assets whenever you like — the filenames are referenced
by the HTML, so keep the names or update the references.

  logo.svg         Header brand mark (also the Organization logo in JSON-LD).
  favicon.svg      Favicon (modern browsers use SVG; a .png fallback is linked too).
  og-image.svg     1200x630 social share image (see PNG note below).

REAL IMAGE FILES TO ADD BEFORE LAUNCH (still placeholders)
----------------------------------------------------------
Drop these real files here (same filenames). Until then the pages render CSS
placeholder boxes / the generated SVGs, so nothing breaks.

  app-icon.png         App icon (square, e.g. 512x512 or 1024x1024).
  screenshot-1.png     iPhone screenshot (portrait, ~1290x2796 or similar).
  screenshot-2.png     iPhone screenshot.
  screenshot-3.png     iPhone screenshot.
  screenshot-4.png     iPhone screenshot (optional).
  og-image.png         Social share image (1200x630). PNG is the safest format
                       for social scrapers (some don't render SVG OG images);
                       export og-image.svg to PNG and the OG/Twitter <meta>
                       tags already point at og-image.png.
  favicon.png          PNG favicon fallback (e.g. 32x32 or 180x180).
  apple-touch-icon.png Apple touch icon (180x180), linked from every page.

The hero + gallery screenshots use styled placeholder boxes. When you add the
real screenshots, swap the placeholder <div class="placeholder ...">s in
index.html for <img> tags (keep the alt text).
