# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

A single-page marketing landing site for **Glow**, a fictional boutique med spa. It is fully built and deployed. The page has one job: convert a visitor into a lead via the capture form. Everything else on the page exists to build enough trust and desire to get that form filled out.

**Vibe (this is the spec, treat it as a requirement):** clean, warm, premium — the aesthetic of a boutique spa, *not* a hospital. Think soft neutrals, generous whitespace, warm accent tones, elegant type. Avoid clinical blues, hard edges, stock-photo sterility, and anything that reads "medical office." When a design choice is ambiguous, bias toward "boutique spa" over "clinic" every time.

## Stack & files

Static site, **no build step** — plain HTML, CSS, and vanilla JS. Do not add a framework, bundler, or npm dependencies unless there's a concrete reason; a single landing page doesn't need them. Fonts load from the Google Fonts CDN (there is no local `assets/` folder).

```
index.html           # the page
styles.css           # all styles; design tokens live in :root (see below)
script.js            # form validation + light scroll-reveal interactivity
README.md            # non-technical audience doc (what the page is, how to edit copy)
glow-artifact.html   # GENERATED self-contained single-file build (see note)
```

**`glow-artifact.html`** is a build output, not a source file — it's the whole site inlined into one file (CSS + JS inlined, the Cormorant/Jost fonts embedded as base64 `data:` URIs) so it can be shared as a standalone page or published as an Artifact with zero external requests. Don't hand-edit it; regenerate it from `index.html` / `styles.css` / `script.js` when those change.

Preview locally with any static server, e.g. `python3 -m http.server 8000` then open http://localhost:8000.

**Deployed:** live on GitHub Pages at https://anthony59ruiz.github.io/glow-medspa-landing/ (served from `main`).

## Page sections (in order)

1. **Hero** — spa name, a warm one-line value proposition, and a primary CTA that scrolls to / focuses the lead form. Large, calm, image-forward.
2. **Featured services** — exactly three, presented as equal cards: **Botox**, **Facials**, **Laser**. Each gets a short benefit-led blurb, not a clinical description.
3. **Social proof** — testimonials / star ratings / trust signals to reassure before the ask.
4. **Lead-capture form** — the conversion goal. Prominent and easy to reach from the hero.

## Lead form

Fields: **name**, **phone**, **email**, and **service interest** (a select of the three featured services, plus a general/other option).

- Validate on the client (required fields, email + phone format) and show friendly inline errors — no harsh red hospital-form energy.
- On submit, show a warm confirmation state. There is no backend; the submission handler in `script.js` is isolated and clearly marked so a real endpoint can be dropped in later.

## Design system

The palette and type are already encoded as CSS custom properties in `styles.css` (`:root`). Reuse these tokens rather than hard-coding values, so the vibe stays consistent as the page grows.

- **Palette:** warm off-white background (`--cream #faf5ef`, `--cream-deep`), soft `--blush` / `--taupe` accents, muted `--gold #c08a4e` for CTAs (`--gold-deep` on hover), and warm `--charcoal #3a332e` for text (deliberately not pure black). **No clinical blue** — the warm neutrals are the whole point.
- **Type:** an elegant serif for headings — **Cormorant Garamond** (`--serif`) — paired with a clean humanist sans for body — **Jost** (`--sans`). Generous line-height and letter-spacing on headings.
- **Layout:** lots of whitespace, soft rounded corners (`--radius`), gentle shadows (`--shadow-soft` / `--shadow-card`), unhurried vertical rhythm. Premium means restraint — resist clutter.
- **Motion:** subtle only — soft fade/rise on scroll, gentle hover states. Nothing flashy.
