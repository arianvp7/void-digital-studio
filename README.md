# VOID Digital Studio — Scroll-Stopping Web Experiences

> A fully animated, single-file landing page system built for high-impact digital presence. Immersive hero animations, particle physics, scroll-reveal storytelling, and cinematic motion — orchestrated through pure HTML, CSS, and vanilla JavaScript. No frameworks. No build step. Just fire.

---

## Overview

This repository is the complete frontend for **VOID Digital Studio** — a creative agency specialising in scroll-stopping web experiences for brands that refuse to be ignored. Rather than relying on bloated frameworks or template builders, every animation in this codebase is hand-authored with precision.

The site demonstrates:
- Custom particle canvas systems with mouse-repulsion physics
- Scroll-triggered IntersectionObserver reveal sequences
- Animated stat counters with cubic ease timing
- Seamless infinite marquee loops
- Frosted-glass navigation with dynamic dark/light mode switching
- CTA breathing glow rings and button shimmer ripple effects

Everything is self-contained in a single `index.html` — no dependencies, no node_modules, no build pipeline. Clone it, open it, ship it.

---

## System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        index.html                                │
│                  (Everything lives here)                         │
└──────────┬─────────────────────────┬───────────────────────────┘
           │                         │
  ┌────────▼────────┐      ┌─────────▼────────┐
  │   Canvas Layer  │      │   CSS Layer       │
  │                 │      │                   │
  │  • 180 particles│      │  • @keyframes     │
  │  • Velocity     │      │  • Custom props   │
  │  • Mouse repel  │      │  • Scroll-reveal  │
  │  • rAF loop     │      │  • Frosted glass  │
  └────────┬────────┘      └─────────┬────────┘
           │                         │
  ┌────────▼─────────────────────────▼────────┐
  │              JavaScript Layer              │
  │                                            │
  │  IntersectionObserver  │  Stat counters    │
  │  Nav dark/light detect │  Marquee engine   │
  │  Custom cursor         │  Parallax hero    │
  └────────────────────────────────────────────┘
```

---

## What's Inside

### Animations Shipped

| Component | Technique | Details |
|---|---|---|
| **Hero Particle Field** | Canvas + rAF | 180 particles, mouse repulsion, scroll-offset compensation |
| **Stat Counters** | requestAnimationFrame | Cubic ease, counts to 47+, 120+, 98%, $2.4M live |
| **Scroll Reveal** | IntersectionObserver | 0.12 threshold, staggered nth-child delays |
| **Marquee Ticker** | CSS translateX | Doubled content, seamless infinite loop |
| **Custom Cursor** | JS mousemove | Purple/cyan gradient, scale-on-hover |
| **Nav Mode Switch** | elementFromPoint() | Reads tile colour under nav, toggles dark/light |
| **CTA Glow Ring** | CSS @keyframes | pulse-ring breathe animation, 3s infinite |
| **Button Shimmer** | ::after translateX | Ripple on hover, cubic-bezier timing |

### Design Tokens

| Token | Value | Used For |
|---|---|---|
| `--void-purple` | `#7c3aed` | Primary brand, cursor, accents |
| `--void-cyan` | `#06b6d4` | Secondary, particle glow, highlights |
| `--void-dark` | `#0d0d0d` | Background, dark sections |
| `--void-card` | `#111111` | Card backgrounds |
| `--void-border` | `rgba(255,255,255,0.06)` | Subtle card borders |

### Page Sections

| Section | Content |
|---|---|
| **Nav** | Frosted glass, VOID logo, dark/light adaptive |
| **Hero** | Full-viewport, particle canvas, animated headline, CTA |
| **Stats** | 4 animated counters — projects, clients, satisfaction, revenue |
| **Work Grid** | 6 project cards with scroll-reveal and hover lift |
| **Services** | 6 service cards — Web Design, Motion, Branding, etc. |
| **Marquee** | Infinite scrolling tagline ticker |
| **CTA** | Email capture, breathing glow, full-width dark section |
| **Footer** | Links, social, copyright |

---

## Quick Start

```bash
# Clone the repo
git clone https://github.com/arianvp7/void-digital-studio.git

# Open in browser — that's it
open index.html
```

No install. No build. No config. One file, full experience.

---

## Deployment

The site is deployed to Vercel as a static site with zero configuration.

**Live URL:** [void-digital-studio.vercel.app](https://void-digital-studio.vercel.app)

Every push to `main` triggers an automatic redeploy.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | Semantic HTML5 |
| Styling | CSS3, custom properties, @keyframes |
| Animation | Vanilla JS, Canvas API, requestAnimationFrame |
| Scroll detection | IntersectionObserver API |
| Deployment | Vercel (static) |
| Version control | GitHub |
| Dependencies | **Zero** |

---

## File Structure

```
void-digital-studio/
└── index.html          # The entire site — HTML, CSS, JS, all inline
```

---

## Built With Claude Code

This site was designed, animated, and deployed using **Claude Code** — Anthropic's AI coding assistant. The entire workflow — from copy to canvas physics to GitHub push to Vercel deploy — was executed through a single AI-assisted session.

---

*VOID Digital Studio — We build what others can't imagine.*
