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

- **Assets** — every image currently loads from the GoHighLevel media CDN
  (`assets.cdn.filesafe.space`). Search the code for `CDN-ASSET`. Once Figma Dev
  access lands, export the real assets into an `/assets` folder and replace the
  URLs so the site no longer depends on the GHL account.
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
