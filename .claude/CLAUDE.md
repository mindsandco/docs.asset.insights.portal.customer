# Project: Asset Insights Portal — customer sales portal

Customer-facing marketing and documentation site for **Asset Insights Portal by Antire**,
a platform for energy and renewables operators to see every asset they own and operate in
one trusted view. This repo is the **sales/marketing portal**, not the product. Its job is
to help C-level prospects understand the value and buy. Content leads with business
outcomes, not technology.

## Tech stack

- **Docsify 4** (runtime markdown renderer, loaded from jsDelivr CDN). No build step, no
  bundler, no `node_modules`.
- Plain HTML/CSS/Markdown. One inline vanilla-JS plugin (the pricing calculator) in
  `docs/index.html`.
- Hosted on **GitHub Pages**.

## Commands

- **Preview locally:** `npx docsify-cli serve docs` (or any static server rooted at `docs/`,
  e.g. `python3 -m http.server -d docs`). Docsify renders the markdown at runtime.
- **Build:** none. There is no compile step.
- **Deploy:** push to `main`. `.github/workflows/jekyll-gh-pages.yml` uploads `docs/`
  directly to GitHub Pages. Despite the filename, it does **not** run a Jekyll build.

## Layout

Everything the site serves lives under `docs/`:

- `index.html` — Docsify bootstrap + config (`loadSidebar`, `loadNavbar`, `coverpage`,
  search, pagination). Also holds the inline pricing-calculator plugin.
- `_coverpage.md` — hero landing (heading, value prop, two CTAs).
- `_sidebar.md` — full navigation tree. Update when adding a content page.
- `_navbar.md` — top-bar links (a subset of the sidebar).
- `README.md` — home/overview page (served at `/`).
- Content pages: `what-is-it.md`, `what-we-solve.md`, `how-we-solve-it.md`,
  `product-tour.md`, `features.md`, `architecture.md`, `pricing.md`, `get-in-touch.md`.
- `assets/styles.css` — custom CSS overriding the Docsify `vue.css` theme.
- `assets/` — `favicon.svg`, `architecture-flow.svg`, `ot-it-bridge.svg`, `screenshots/`.
- `.nojekyll` — **must stay.** Prevents GitHub Pages from running Jekyll, which would strip
  the underscore-prefixed files (`_coverpage.md`, `_sidebar.md`, `_navbar.md`).

## Conventions

- **Adding a page:** create `docs/<name>.md`, then add it to `_sidebar.md` and (if it
  belongs in quick-access) `_navbar.md`. Nothing else registers a route.
- **Styling:** edit `assets/styles.css`, not inline styles. Cover-page button contrast and
  navbar/sidebar layout are handled there (the navbar needs a `left` matching the sidebar
  width, or it overlaps).
- **Images:** put in `assets/` (or `assets/screenshots/`) and reference with a relative
  path. `zoom-image` is enabled.
- **Sentence case** for all headings and copy (see brand voice below).

## Brand voice — non-negotiable for all customer copy

This is customer-facing Antire content. When writing or editing any page text, follow the
Antire tone of voice (load the `antire-tov` skill; `antire-brand-guidelines` for facts,
offer, palette). The rules that break the brand if ignored:

- **No em dashes (—) anywhere.** Rewrite the sentence. Do a literal search for `—` before
  finishing.
- **Sentence case** everywhere. Not Title Case.
- **American spelling** (optimize, meters, fulfill).
- Lead with the **outcome**, not the technology. Back claims with real numbers.
- Value proposition, verbatim: **"Bridging your goals with trusted AI."** Do not paraphrase.
- Always capitalize **Antire** and **AI**; **people-first** is hyphenated, lowercase.

## Product truth — do not invent capabilities

The authoritative product spec is the **internal** repo `mindsandco/docs.asset.insights.portal`,
not this one. This portal has drifted from real capabilities before. Before adding or
changing any claim about what the product does, cross-check the internal docs. Do not
describe features not confirmed there.

Product domain facts (energy/renewables, solar PV and wind): tracks assets, production
(kW/kWh), availability, performance ratio, and portfolio overview. Architecture spans three
zones — **OT/Edge**, **IT Cloud**, **SINKS (customer)**. Data flow: field assets push to
the Field Gateway (OT) → Ingest API → raw Dapr Pub/Sub (RabbitMQ) in IT Cloud → Worker
harmonizes → Harmonized Pub/Sub in the SINKS zone → customer custom apps subscribe. The
Worker publishes **only** to the harmonized Pub/Sub in SINKS; IT platform services
(Ingest, Uptime, Management, Notifications) form their own mesh in IT Cloud and do not
subscribe to the harmonized queue. The Portal SPA talks only to Management (its BFF). Keep
`architecture.md` and the SVGs consistent with this.

## Pricing calculator

Lives inline in `docs/index.html` (a Docsify `hook.doneEach` plugin) and binds to
`#pc-fields` / `#pc-result` elements rendered from `pricing.md`. Tiers and prices (EUR) are
hardcoded in that script. Change pricing in **both** the calculator constants and the
`pricing.md` copy so they agree.

## Boundaries

- Never delete `.nojekyll`.
- Don't add a bundler, framework, or `node_modules` — the site is intentionally build-free.
- Don't claim product capabilities not backed by the internal docs repo.
- Ask before changing pricing numbers or the deploy workflow.
