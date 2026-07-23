# Eastwood Global — IB Webinar Landing Page

Landing page for the free live webinar **"What Top Universities Really Look For — and how the IB builds it before Grade 11."** Single action throughout: **Reserve Your Place** (Typeform).

## Structure

```
.
├── index.html          # the page (self-contained markup, styles, and scripts)
├── assets/
│   ├── eg-logo.png         # header + footer wordmark
│   ├── hero-students.png   # webinar hero background
│   └── michel-khoury.png   # host portrait
└── README.md
```

## Running locally

It's a static page — serve the folder with any static server, e.g.:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` directly (file://) also works.

## Dependencies (loaded from CDN — internet required)

- **Google Fonts** — Inter + Bodoni Moda
- **d3 7.9.0** and **topojson-client 3.1.0** — render the interactive world-clock map
- **Natural Earth geometry** — `world-atlas@2.0.2/countries-110m.json` (public domain)

The world map draws real country geometry with a Natural Earth projection; every city
pin is placed through that same projection, so positions are geographically exact.
All CDN tags are version-pinned with subresource-integrity hashes.

> For a fully offline single-file version, see the bundled build
> (`Eastwood Global Webinar Landing.html`) produced from this source.

## Configuration notes

- **CTA:** all four buttons point to the Typeform `z8G6hwZ0`, each with a distinct
  `utm_content` (header / hero / footer / sticky-mobile). Swap the form ID in `index.html`.
- **Session details** (date/time) live inline in the hero and reserve sections.
- Motion respects `prefers-reduced-motion`.
