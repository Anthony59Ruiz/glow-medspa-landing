# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

A single-page marketing landing site for **Glow**, a fictional boutique med spa. The goal of the page is one thing: convert a visitor into a lead via the capture form. Everything else on the page exists to build enough trust and desire to get that form filled out.

**Vibe (this is the spec, treat it as a requirement):** clean, warm, premium — the aesthetic of a boutique spa, *not* a hospital. Think soft neutrals, generous whitespace, warm accent tones, elegant type. Avoid clinical blues, hard edges, stock-photo sterility, and anything that reads "medical office."

## Stack

Static site, **no build step** — plain HTML, CSS, and vanilla JS. Do not add a framework, bundler, or npm dependencies unless there's a concrete reason; a single landing page doesn't need them. Keep it to:

```
index.html      # the page
styles.css      # all styles (use CSS custom properties for the design tokens below)
script.js       # form handling + any light interactivity
assets/         # images, fonts, icons
```

Preview locally with any static server, e.g. `python3 -m http.server 8000` then open http://localhost:8000.

## Page sections (in order)

1. **Hero** — spa name, a warm one-line value proposition, and a primary CTA that scrolls to / focuses the lead form. Large, calm, image-forward.
2. **Featured services** — exactly three, presented as equal cards: **Botox**, **Facials**, **Laser**. Each gets a short benefit-led blurb, not a clinical description.
3. **Social proof** — testimonials / star ratings / trust signals to reassure before the ask.
4. **Lead-capture form** — the conversion goal. Make it prominent and easy to reach from the hero.

## Lead form

Fields: **name**, **phone**, **email**, and **service interest** (a select of the three featured services, plus a general/other option).

- Validate on the client (required fields, email + phone format) and show friendly inline errors — no harsh red hospital-form energy.
- On submit, show a warm confirmation state. There is no backend yet; keep the submission handler in `script.js` isolated and clearly marked so a real endpoint can be dropped in later.

## Design direction

Encode these as CSS custom properties in `styles.css` so the vibe stays consistent as the page grows:

- **Palette:** warm off-white / cream background, soft blush or warm-taupe accents, a muted gold or terracotta for CTAs, deep warm charcoal (not pure black) for text. No clinical blue.
- **Type:** an elegant serif for headings paired with a clean, humanist sans for body. Generous line-height and letter-spacing on headings.
- **Layout:** lots of whitespace, soft rounded corners, gentle shadows, unhurried vertical rhythm. Premium means restraint — resist clutter.
- **Motion:** subtle only (soft fade/rise on scroll, gentle hover states). Nothing flashy.

When making design choices, bias toward "boutique spa" over "clinic" every time it's ambiguous.
