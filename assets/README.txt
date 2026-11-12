Assets folder for the Improva website.

WHAT IS HERE
------------
  logo.png                 The app icon (512x512): three rising bars on the
                           Today wash. The Organization logo in the JSON-LD.
                           The header draws the same mark as inline SVG.
  favicon.svg              Favicon (vector), and favicon.png (32x32) for
                           browsers without SVG favicons.
  apple-touch-icon.png     Apple touch icon (180x180), linked from every page.
  og-image.png             Social share image (1200x630): the mark and "One app
                           instead of four" on the Today wash. Linked from the
                           Open Graph / Twitter tags.
  The icon files are drawn from the bars geometry in
  screenshots/redesign-2026-11/work/compose.py (rendered at 4x, downsampled).

  Homepage screens (webp, real captures from design_capture/wraps-after/
  pro-light/ unless noted, framed or cropped as compose.py does; sized for 2x):
  hero-tiles.webp          The six fortnight-overview tiles (hero).
  blocking-toggle.webp     The Enable app blocking switch (lock band).
  lock-card.webp           Home's Apps locked card, from
                           design/swap-plates-pr-locked/home-locked-card.png.
  done-card.webp           Home with today's workout Done (lock band).
  spare-key-card.webp      The top of the Spare Key screen (Spare Key band).
  coach-intake.webp        Running coach setup (training band, behind).
  coach-plan.webp          Running plan preview (training band, in front).
  micronutrients.webp      Home micronutrients, cleaned as compose.py's
                           clean_micro(); the top of the phone only, because
                           the band's edge crops the rest.
  meal-week.webp           The meal week (meal-plan band, in front).
  shopping-list.webp       The shopping list (meal-plan band, behind).

  app-store-badge-black.svg / app-store-badge-white.svg
                           Apple's official "Download on the App Store" badge,
                           downloaded from Apple's marketing tools. Not shown
                           yet: Apple requires it to link to the live listing.
                           The markup is commented out in index.html.
  fonts/                   Archivo SemiExpanded ExtraBold (headlines) and
                           Archivo SemiBold (subtitles, eyebrows, pills), woff2
                           subset to Latin, with the licence, Archivo-OFL.txt.
                           Converted from the app's FitnessLocker/Resources/Fonts.

Keep the filenames, or update the references in the HTML and style.css.
