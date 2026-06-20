# NestGenie — marketing site (draft)

Landing page for NestGenie, "Your Always-On AI Parenting Partner." This repo
hosts the in-progress static site, built from the team's Figma design.

## Files

- `index.html` — current working site. Single self-contained file (HTML + CSS +
  JS inline). Fully responsive: two-column hero above 1024px, single-column
  below, hamburger menu under 900px.
- `nestgenie-v2.html` — the colleagues' original first pass, kept for reference.

## Status

Roughly an 85% match to the Figma. Built before Figma Dev access, so spacing is
matched by eye and the hero's curved wave is a CSS approximation.

## TODO before launch

- **⚠️ Remove the `noindex` tag** — `index.html` has a
  `<meta name="robots" content="noindex, nofollow">` near the top to keep the
  staging draft out of search engines. DELETE it before going live or the real
  site won't be indexed by Google.
- **Hero visual** — the desktop hero (photo + phone + sparkles + blue curve) is a
  single image, `assets/hero-visual.webp`, cropped straight from the Figma design
  export so it's pixel-faithful, with the flat background made transparent so the
  hero's own background shows through (no seam) and it scales as one unit. The
  phone/chat is therefore baked into the image (decorative); the headline, body,
  and buttons remain live HTML. Mobile uses its own composition image,
  `assets/hero-mobile.webp` (cropped from the Figma Website Mobile design, also
  transparent-background), stacked below the text under 1024px. (The
  individual `hero-bg.svg` / `sparkle.svg` / `phone-mockup.webp` are now unused on
  desktop but kept in case the layout is ever rebuilt from parts.)
- **Assets — fully self-hosted.** The visible page no longer depends on the
  GoHighLevel CDN; everything is in `/assets`: hero photo (`hero.webp`), hero
  background blob (`hero-bg.svg`), 3 sparkles (`sparkle.svg`), phone mockup
  (`phone-mockup.webp`), nav logo (`logo.png`), footer white logo
  (`logo-white.png`), favicon (`favicon.png`), the 4 solution-card icons
  (`icon-*.svg`), and the 3 episode photos (`episode-1/2/3.webp`). The hero
  section background is the exact Figma radial-gradient (inline CSS, no image).
  **One CDN reference remains on purpose:** the `og:image` meta tag — social
  scrapers need an absolute URL, so replace it with a hosted 1200×630 share image
  (a normal pre-launch task), not a Figma export.
- **Video areas** — the 3 Diary episode thumbnails now use real photos
  (`episode-1/2/3.webp`, from exports Frame 29/37/38). The 3 **Reels** tiles are
  still branded gradient placeholders — add real reel thumbnails when available.
  The old shared CDN placeholder image has been removed from all six.
- **Waitlist form** — set `FORM_ENDPOINT` in the `<script>` at the bottom of
  `index.html` to the GoHighLevel inbound-webhook URL (ask Lisa). Left blank, the
  form runs in demo mode (shows the success state without sending). Do NOT commit
  the live URL to a public repo.
- **Episode / reel thumbnails** are placeholders (currently tinted duplicates).
- **Social links** in the Reels section point to `#` — add real URLs.
- **Hero photo + phone mockup** appeared blank in the GHL library; confirm /
  replace with real imagery.
- Add a real 1200×630 Open Graph share image and a proper favicon.

## Hosting

Intended as a staging/preview deploy (GitHub Pages from a private repo). The
final hosting decision — standalone vs. keeping it inside GoHighLevel — is still
open. Whatever is used here is disposable.

## Local preview

Open `index.html` in a browser, or run a static server from this folder:

```
python3 -m http.server 8000
# then visit http://localhost:8000
```
