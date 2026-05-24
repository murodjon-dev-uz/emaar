# emaar

English · **[Русский](README.md)**

A responsive single-page landing for Emaar Properties (Dubai Creek Harbour) — static frontend only, no build step or backend.

| | |
|---|---|
| **Live demo** | [murodjon-dev-uz.github.io/emaar](https://murodjon-dev-uz.github.io/emaar) |
| **Repository** | [github.com/murodjon-dev-uz/emaar](https://github.com/murodjon-dev-uz/emaar) |
| **Author** | Murodjon Nuritdinov |
| **Year** | 2023 |

---

## About

**emaar** is an educational portfolio project: the visual layer of a real-estate promo site for Emaar Properties focused on Dubai Creek Harbour. A single HTML page demonstrates typical property-landing UX — hero, project catalog, an interactive location map, payment highlights, and a contact screen.

Copy and prices are fixed in markup; “request a call”, “download brochure”, and “project details” flows are **static mockups** — links use `#`, form submission is not implemented.

The repository ships production artifacts only (`style.min.css`, `app.min.js`); unminified SCSS/JS sources and a bundler are not included.

---

## Implementation highlights

- **Hero & KPIs** — full-bleed background (`ibg`), headline stats (booking, payment plan, price from).
- **Three Swiper carousels** — available units for Creek Rise, The Cove, and Creek Gate with pagination and arrows.
- **Location map** — Tippy.js tooltips on three districts (Dubai Creek Harbour, Dubai Hills Estate, Emaar South).
- **Projects block** — sticky sidebar (`data-sticky`), community filter (radio), accordions (`data-spoller`), anchor nav via `data-goto`, active section via `data-watch="navigator"`.
- **Modals** — brochure, special offer, and a detailed project popup (POI map, lightGallery, floor plans, payment, form UI).
- **Motion** — GSAP 3.12 and ScrollTrigger (CDN) for scroll scenes; cursor parallax on info-block (`data-prlx-mouse`).
- **Gallery** — lightGallery 2.7.1 inside the project modal (`data-gallery`).
- **Images** — `<picture>` (WebP + JPG/PNG), lazy loading via `data-src` / `data-srcset` with a 1×1 placeholder.
- **Responsive** — block repositioning with `data-da` (offer popup, breakpoint 767.98px).
- **Typography** — Lato, Alethia Pro, Manrope (Google Fonts), icon font `_icon-*`.
- **Static asset caching** — version query strings on CSS/JS (`?_v=...`) and favicon (`?v=...`); bump the number in `index.html` when you update a file.

Brand colors in CSS: `#071c35` (dark), `#3fb1ce` (accent), `#ffffff`.

---

## Stack

| Layer | Technologies |
|-------|----------------|
| Markup | HTML5, semantic landmarks |
| Styles | CSS3, BEM-style naming, mobile-first |
| Scripts | Vanilla JS in `app.min.js` (Swiper, Tippy, popups, lazy-load, spollers, sticky, in-page nav) + GSAP/ScrollTrigger from CDN |
| Fonts | Self-hosted: Lato, Alethia Pro, icons; Manrope via Google Fonts |
| Hosting | GitHub Pages |

No bundler (npm, Vite, Webpack).

---

## Structure

```
emaar/
├── index.html
├── favicon.ico
├── css/style.min.css
├── js/app.min.js
├── fonts/
├── img/
│   ├── header/, homes/, top-projects/, location/
│   ├── projects/ (creek-rise, the-cove, creek-gate)
│   ├── info-block/, footer/, gallery/
│   └── popup-*/ (brochure, offer, project)
└── README.md, README.en.md
```

---

## Quick start

```bash
git clone https://github.com/murodjon-dev-uz/emaar.git
cd emaar
python3 -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000). Alternative: `npx --yes serve .`

---

## Deploy

Published on **GitHub Pages**:

**https://murodjon-dev-uz.github.io/emaar**

Source: [murodjon-dev-uz/emaar](https://github.com/murodjon-dev-uz/emaar), `main` branch, root `/`. After CSS/JS changes, increment `?_v=`; after favicon changes, increment `?v=` in `index.html`.

---

## Page sections

| Section / module | Content |
|------------------|---------|
| Header | Logo, Dubai Creek Harbour title, KPIs, “See project” CTA |
| Homes | Company intro, financial highlights, “see more” → brochure popup |
| Top projects | Three project cards with pricing |
| Location | Map with Tippy district tooltips |
| Projects | Sidebar + three projects with unit Swipers |
| Info block | Payment Option & More About Emaar (parallax) |
| Contact | “Speak to a specialist” (form UI only) |
| Footer | Nav, placeholder phone, messenger links |
| Popups | Brochure, unique offer, detailed popup-project |

---

## Limitations

- No API, CRM, or lead handling — `action="#"`, phone `+971 56XXX-XX-XX`.
- Links and social profiles are placeholders (`href="#"`).
- No Open Graph / Twitter Card tags (meta description only).
- Layout edits go into minified files or an external source project.

---

## License

© 2023 **Murodjon Nuritdinov**. All rights reserved. Copying, distribution, and commercial use without the author’s permission are prohibited.
