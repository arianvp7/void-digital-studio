---
name: scroll-stop-builder
description: >
  Builds a complete, visually striking single-file HTML landing page from a product or service description. Use this skill whenever the user asks to build, create, or generate a landing page, hero section, or website for a business — even if they don't say "skill" or "HTML". This includes requests like "build me a landing page for X", "make a website for my Y business", "create a hero section for Z", "design a page for my moving company", "I need a site for my [business type]", or any request that combines copy + visual design into a deliverable webpage. Always invoke this skill for any landing page or hero section build request. Works best paired with scroll-stop-prompter for copy.
---

## Purpose

Turn a business description into a complete, self-contained HTML landing page with:
- Scroll-stopping headline copy (generated using scroll-stop-prompter principles)
- A bold, animated hero section with a relevant visual metaphor
- Clear sections: nav, hero, social proof/stats, services/features, CTA
- Dark, modern aesthetic with a brand accent color
- Saved as a single `.html` file in `assets/`

---

## Output spec

| Property | Value |
|---|---|
| Output | Single self-contained `.html` file |
| Styling | Embedded `<style>` — no external CSS frameworks |
| Fonts | Google Fonts via `@import` (Inter or similar) |
| JS | Vanilla, embedded `<script>` — no frameworks |
| Animation | CSS keyframes + vanilla JS for interactive elements |
| Save location | `assets/[business-slug].html` |
| Theme | Dark by default (`#0d0d0d` bg) with one brand accent color |

---

## Step-by-step workflow

### Step 1 — Understand the brief

Extract from the request:
- **Business type** — what they do
- **Target customer** — who they serve and what pain they have
- **Key differentiator** — what makes this business stand out
- **Visual concept** — what the hero animation/illustration should show (if specified)
- **Brand accent color** — default to orange `#f97316` if not specified

If a visual concept isn't given, invent one that's specific to the business. Good visual metaphors are dynamic and unexpected — not a generic stock-photo vibe.

### Step 2 — Generate copy using scroll-stop-prompter principles

Before writing any HTML, draft the copy package:
- **Angle**: choose pain-first / outcome-first / curiosity gap / identity
- **Headline**: under 10 words, active verb, specific
- **Subheadline**: 1–2 sentences expanding the promise
- **CTA**: first-person, action-oriented, 2–5 words
- **Stats**: invent 3–4 plausible, specific social proof numbers
- **Services**: 4–6 service cards with icon + title + one-line description

No generic phrases ("world-class", "innovative", "seamless"). Sound human.

### Step 3 — Design the hero visual

The hero visual is the most important part. It must be:
- **Specific to the business** — not a generic gradient or abstract blob
- **Animated** — CSS keyframes bring it to life
- **Built with SVG, CSS, or emoji** — no external images needed
- **Emotionally resonant** — the animation should reinforce the headline promise

Good hero visual patterns:
| Business type | Visual idea |
|---|---|
| Moving company | Furniture flying out of a van |
| Bakery | Rising bread/steam, flying pastries |
| SaaS / productivity | Dashboard widgets snapping into place |
| Fitness | Weights lifting, progress bars filling |
| Cleaning service | Dirt particles disappearing, sparkles |
| Real estate | Houses assembling from pieces |
| Finance / accounting | Numbers resolving into clean totals |
| Photography | Camera shutter opening, photos developing |

Use emoji as SVG `<foreignObject>` or absolutely positioned `<div>` elements with CSS animation. Use SVG shapes for structural elements (vehicles, buildings, objects).

### Step 4 — Build the HTML file

Structure:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- meta, Google Fonts, embedded CSS -->
</head>
<body>
  <nav><!-- logo, links, CTA button --></nav>
  <section class="hero">
    <!-- eyebrow, h1, p, CTA buttons -->
    <!-- animated visual scene -->
  </section>
  <div class="stats"><!-- 3-4 stat numbers --></div>
  <section class="services"><!-- card grid --></section>
  <section class="cta-section"><!-- final CTA + email/zip form --></section>
  <footer><!-- simple one-liner --></footer>
</body>
</html>
```

**CSS rules to follow:**
- `box-sizing: border-box` global reset
- Responsive: `clamp()` for font sizes, `auto-fit` grid for cards
- Nav fixed with backdrop blur
- Hero `min-height: 100vh`, centered flex column
- Cards: subtle border + background, hover lift effect
- Mobile: nav links hidden, panels stack vertically at 600px

**Animation rules:**
- Hero items: `@keyframes` with `animation: name duration delay easing infinite`
- Stagger delays with CSS custom properties (`--delay`)
- Shockwave / pulse rings on the focal point of the visual
- Auto-rotate or drift animations on idle 3D/floating elements

### Step 5 — QA checklist

Before saving:
- [ ] Headline is scroll-stopping (under 10 words, active, specific)
- [ ] Hero visual is animated and specific to the business
- [ ] All nav links, buttons, and form inputs are present (non-functional is fine)
- [ ] Stats section has 3–4 credible numbers
- [ ] Service cards: 4–6 cards with icon, title, description
- [ ] Final CTA section with form input + button
- [ ] Responsive at 375px and 1280px
- [ ] No broken references (all fonts/scripts load from CDN or are inline)
- [ ] File saved to `assets/[business-slug].html`

### Step 6 — Report back

Tell the user:
- File saved to: `assets/[filename].html`
- Copy angle chosen and headline used
- What the hero animation shows
- Offer to tweak color, copy, or layout

---

## Design tokens (defaults — override per brand)

```
Background:     #0d0d0d
Surface:        rgba(255,255,255,0.04)
Border:         rgba(255,255,255,0.08)
Text primary:   #ffffff
Text secondary: #888888
Accent:         #f97316  (orange — change per brand)
Accent hover:   darken accent by ~8%
Border radius:  8px (small), 16px (cards)
```

---

## Example accent colors by industry

| Industry | Accent |
|---|---|
| Moving / logistics | `#f97316` orange |
| Health / wellness | `#10b981` green |
| Finance | `#3b82f6` blue |
| Creative / agency | `#8b5cf6` purple |
| Food / bakery | `#f59e0b` amber |
| Tech / SaaS | `#06b6d4` cyan |
| Real estate | `#6366f1` indigo |
