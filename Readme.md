# Vertex Digital Solutions — Multi-Page Website (Task 7)

A responsive, 4-page marketing site for a fictional software/cloud consultancy,
built as a clean structural example for Task 7 (no build step required).

## Pages

| Page          | File            | Purpose                                              |
|---------------|-----------------|-------------------------------------------------------|
| Home          | `index.html`    | Hero, stats, service overview, featured work, CTA     |
| About         | `about.html`    | Company story, timeline, values, leadership team      |
| Services      | `services.html` | Service list, process, pricing tiers, FAQ              |
| Contact       | `contact.html`  | Contact details, map placeholder, validated form      |

## Structure

```
task7-website/
├── index.html
├── about.html
├── services.html
├── contact.html
├── css/
│   └── style.css     # design tokens + all styles
├── js/
│   └── script.js     # nav toggle, FAQ accordion, form validation
└── assets/            # empty — drop real images/logo here if needed
```

## Features

- **Responsive design** — fluid type, CSS Grid/Flexbox layouts, and a
  hamburger nav that appears under ~880px width. Tested down to ~360px.
- **Consistent navigation** — the same header/footer markup (with
  `aria-current="page"` on the active link) appears on every page.
- **Consistent UI** — a single `css/style.css` design-token file (color,
  type, spacing, radius, shadow) drives every page, so buttons, cards and
  sections look and behave the same everywhere.
- **Accessible details** — visible focus states, semantic landmarks
  (`header`/`main`/`footer`), `aria-label`s on icon-only links, and a
  `prefers-reduced-motion` override for the hero animation.
- **No build tools required** — open `index.html` directly in a browser, or
  serve the folder with any static file server.

## Running it

Just open `index.html` in a browser. For a local server (recommended so
relative paths behave exactly as in production):

```bash
cd task7-website
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Customizing

- **Colors/fonts** — all defined as CSS variables at the top of
  `css/style.css` (`:root { ... }`). Change them once, every page updates.
- **Copy/content** — each page is plain HTML; edit the text directly.
- **Contact form** — currently client-side only (validates and shows a
  confirmation message, no network request). To make it functional, point
  the form at a backend endpoint or a form service (e.g. Formspree) and
  replace the `preventDefault` logic in `js/script.js` with a real `fetch()`
  call.