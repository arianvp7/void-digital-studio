# VOID Digital Studio — Scroll-Stopping Web Experiences

> A fully animated, multi-page website system built for high-impact digital presence. Immersive hero animations, particle physics, scroll-reveal storytelling, cinematic motion — plus a complete Claude Code skill stack for building, optimising, and deploying premium client websites at scale. No frameworks. No build step. Just fire.

---

## Overview

This repository is the complete frontend and skill system for **VOID Digital Studio** — a creative agency specialising in scroll-stopping web experiences for brands that refuse to be ignored. Built entirely through **Claude Code** with custom skills, this project also serves as a live demonstration of the full AI-assisted website workflow: brand → assets → build → SEO → deploy.

The site demonstrates:
- Custom particle canvas systems with mouse-repulsion physics
- Scroll-triggered IntersectionObserver reveal sequences
- Animated stat counters with cubic ease timing
- Seamless infinite marquee loops
- Frosted-glass navigation with dynamic dark/light switching
- CTA breathing glow rings and button shimmer ripple effects
- Multi-page architecture: Home, Work, About, Contact — all SEO-optimised

Everything is self-contained in plain HTML — no dependencies, no node_modules, no build pipeline. Clone it, open it, ship it.

---

## System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    VOID Digital Studio                           │
│              Multi-Page Website + Skill System                   │
└────────────┬────────────────────────────┬────────────────────────┘
             │                            │
  ┌──────────▼──────────┐     ┌──────────▼──────────┐
  │    Website Layer     │     │    Skills Layer       │
  │                      │     │                       │
  │  index.html          │     │  /asset-generation    │
  │  work.html           │     │  /scroll-stop-builder │
  │  about.html          │     │  /scroll-stop-prompter│
  │  contact.html        │     │  /seo-optimizer       │
  └──────────┬──────────┘     └──────────┬──────────┘
             │                            │
  ┌──────────▼──────────┐     ┌──────────▼──────────┐
  │    Canvas Layer      │     │    Eval System        │
  │                      │     │                       │
  │  • 180 particles     │     │  evals.json (3 cases) │
  │  • Velocity physics  │     │  benchmark.json       │
  │  • Mouse repulsion   │     │  100% vs 38.7% delta  │
  │  • rAF loop          │     │  graded + reported    │
  └──────────────────────┘     └──────────────────────┘
```

---

## What's Inside

### Pages

| Page | File | SEO Schema |
|---|---|---|
| **Home** | `index.html` | Organization + WebSite JSON-LD |
| **Work** | `work.html` | CollectionPage JSON-LD |
| **About** | `about.html` | AboutPage + Organization JSON-LD |
| **Contact** | `contact.html` | ContactPage JSON-LD |

Every page has: title (50–60 chars), meta description (150–160 chars), Open Graph, Twitter Card, canonical URL, robots, structured data.

### Skills

| Skill | What it does |
|---|---|
| **`/asset-generation`** | Takes brand data → outputs AI image + video prompts (Nano Banana / Flux / Kling) |
| **`/scroll-stop-builder`** | Builds full animated HTML site from brief + scroll animation video |
| **`/scroll-stop-prompter`** | Writes scroll-stopping copy: headlines, hero text, CTAs |
| **`/seo-optimizer`** | Audits + fixes SEO across all pages, outputs HTML report with A–F grade |

### Animations Shipped

| Component | Technique | Details |
|---|---|---|
| **Hero Particle Field** | Canvas + rAF | 180 particles, mouse repulsion, scroll-offset compensation |
| **Stat Counters** | requestAnimationFrame | Cubic ease, live counters |
| **Scroll Reveal** | IntersectionObserver | 0.12 threshold, staggered nth-child delays |
| **Marquee Ticker** | CSS translateX | Doubled content, seamless infinite loop |
| **Custom Cursor** | JS mousemove | Purple/cyan gradient, scale-on-hover |
| **Nav Mode Switch** | elementFromPoint() | Reads tile colour under nav, toggles dark/light |
| **CTA Glow Ring** | CSS @keyframes | pulse-ring breathe animation, 3s infinite |
| **Button Shimmer** | ::after translateX | Ripple on hover, cubic-bezier timing |

### Design Tokens

| Token | Value | Used For |
|---|---|---|
| `--accent` | `#a855f7` | Primary brand, cursor, accents |
| `--accent2` | `#06b6d4` | Secondary, gradients, highlights |
| `--bg` | `#050508` | Background |
| Inter 300–900 | Google Fonts | All typography |

---

## The Workflow (WORKFLOW.md)

This repo includes the complete **[Jack Roberts $10K Website Workflow](WORKFLOW.md)** — a 5-step system for building and selling premium websites with Claude Code:

```
Step 1 → firecrawl.dev       Brand extraction from any client website
Step 2 → /asset-generation   AI image + video prompts → Nano Banana / Kling
Step 3 → /scroll-stop-builder  Build the animated site
Step 4 → Multi-page prompt   Add pages, full SEO, HTML audit report
Step 5 → GitHub + Vercel     Deploy in one command
```

See [WORKFLOW.md](WORKFLOW.md) for all prompts, settings, and the MONEY framework for selling sites.

---

## SEO Benchmark Results

The `/seo-optimizer` skill was validated against 3 test cases:

| Eval | Test | With Skill | Without Skill |
|---|---|---|---|
| eval-0 | VOID homepage (bare) | 8/8 ✅ | 3/8 ❌ |
| eval-1 | Morning Knead coffee shop (inline HTML) | 11/11 ✅ | 5/11 ❌ |
| eval-2 | VOID about page (gaps only) | 6/6 ✅ | 2/6 ❌ |
| **Total** | | **100% pass rate** | **38.7% pass rate** |

**Delta: +61.3pp** — the skill makes a measurable, consistent difference across all three scenarios.

Full benchmark data in [`workspace/iteration-1/benchmark.json`](workspace/iteration-1/benchmark.json).

---

## Quick Start

```bash
# Clone the repo
git clone https://github.com/arianvp7/void-digital-studio.git

# Open in browser — that's it
open index.html
```

No install. No build. No config.

---

## Deployment

**Live URL:** [void-digital-studio.vercel.app](https://void-digital-studio.vercel.app)

Every push to `main` triggers an automatic Vercel redeploy. Vercel Analytics is enabled — visitor data visible in the Vercel dashboard.

---

## File Structure

```
void-digital-studio/
├── index.html              # Home — particle canvas, scroll animations
├── work.html               # Work — portfolio grid, filter bar, stats
├── about.html              # About — studio story, team, values, process
├── contact.html            # Contact — split layout, form, FAQ
│
├── WORKFLOW.md             # Complete 5-step $10K website workflow
│
├── skills/
│   ├── asset-generation/
│   │   └── SKILL.md        # AI image + video prompt generator
│   └── seo-optimizer/
│       ├── SKILL.md        # SEO audit + HTML report skill
│       └── evals.json      # 3 test cases used for validation
│
├── assets/
│   ├── scroll-animated-site.html   # Original scroll-stop template
│   ├── moving-company.html         # Moving company demo
│   └── apple-animated.html         # Apple-style demo
│
├── workspace/
│   └── iteration-1/
│       ├── benchmark.json  # Skill eval results (100% vs 38.7%)
│       └── benchmark.md    # Benchmark summary
│
└── evals/
    └── evals.json          # Legacy eval prompts
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | Semantic HTML5 |
| Styling | CSS3, custom properties, @keyframes |
| Animation | Vanilla JS, Canvas API, requestAnimationFrame |
| Scroll detection | IntersectionObserver API |
| AI workflow | Claude Code + custom skills |
| Deployment | Vercel (static, auto-deploy) |
| Analytics | Vercel Web Analytics |
| Version control | GitHub |
| Dependencies | **Zero** |

---

## Built With Claude Code

This entire project — site design, animation system, multi-page architecture, SEO optimisation, skill creation, eval framework, and deployment pipeline — was built using **Claude Code** through a single AI-assisted session.

---

*VOID Digital Studio — We build what others can't imagine.*
