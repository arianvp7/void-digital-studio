# The Jack Roberts $10K Website Workflow
## Claude Code + Nano Banana 2 — Complete Step-by-Step

---

## What You're Building
A scroll-stopping, mobile-responsive, multi-page, SEO-optimised website for any client
or business — in under an hour, using Claude Code skills + AI image tools.

---

## Your Skills (already installed)
| Skill | Command | What it does |
|---|---|---|
| Asset Generation | `/asset-generation` | Creates image + video prompts |
| Scroll Stop Builder | `/scroll-stop-builder` | Builds the animated HTML site |
| Scroll Stop Prompter | `/scroll-stop-prompter` | Writes the copy/headlines |
| SEO Optimizer | `/seo-optimizer` | Audits + fixes SEO, HTML report |

---

## The 5-Step Process

---

### STEP 1 — Brand Extraction

**Tool: firecrawl.dev**

1. Go to [firecrawl.dev](https://firecrawl.dev)
2. Left sidebar → **Scrape** → **Markdown** → **Branding**
3. Enter the client's website URL
4. Copy the full branding output (colours, logo, typography, imagery)
5. Paste it into Claude Code and say:

```
Here is the brand extraction from [client website].
Run /asset-generation and create my image and video prompts.
```

---

### STEP 2 — Generate Assets (Images + Video)

Claude will give you 3 prompts. Use them in order:

#### Image Tool (Nano Banana 2 / Midjourney / Flux / Ideogram)
- **Prompt 1** → Assembled hero image → **16:9 | 2K | 4 iterations | white background**
- Pick your favourite result → download it
- **Prompt 2** → Paste Prompt 1 output as reference image → Exploded version → same settings
- Pick your favourite → download it

#### Video Tool (Hailuoai.com — free)
1. Go to [hailuoai.com](https://hailuoai.com) → Video
2. Upload Prompt 1 image as **Start Frame**
3. Upload Prompt 2 image as **End Frame**
4. Paste **Prompt 3** (the video transition prompt)
5. Settings: **Kling 3.0 | 7 seconds | no multi-shot | no enhance**
6. Generate → download the video

---

### STEP 3 — Build the Website

#### Option A: Fresh build
In Claude Code:
```
/scroll-stop-builder
```
When it asks for the scroll animation file → point it to the video you just downloaded.
Claude will ask about brand colours, copy, and pages — answer from the firecrawl data.

#### Option B: Clone + improve an existing site (Jack's HTML Reference technique)
1. Google **"HTML website extractor"** → use the first result
2. Enter the client's current website URL → download as HTML
3. In Claude Code:
```
I've just downloaded the HTML from [client's current website].
I would like to use that HTML to recreate it with new copy and
the scroll-stopping animation included within it please.
The animation video is the last file I downloaded.
```
Claude will replicate their structure, keep their branding, and inject the animation.

**Pro tip from Jack:** Set Claude to **Edit Automatically** mode (not Plan mode) to skip
confirmation dialogs and move faster. Hit `Shift+Tab` until you see "Edit automatically".

---

### STEP 4 — Add Multiple Pages + SEO

Once the homepage MVP is working, paste this prompt exactly:

```
I have an existing website. Look at my current site and understand
the existing design language. Ask me which pages I want to create.
For each page, match the existing design exactly. Add full SEO
optimization. Include structured data. Make it fully responsive
and update the navigation across all the pages. After creating all
the pages, run a full SEO audit across every page, giving me a report.
Show me what's optimized and any ranking improvements.
```

Claude will ask which pages you want. Suggest: **About, Services/Work, Contact**
(or whatever makes sense for the client).

After pages are built, run the SEO skill:
```
/seo-optimizer
```
This will fix all pages and open an HTML report with a score out of 100.

---

### STEP 5 — Publish

Claude Code already has GitHub + Vercel connected. Just say:

```
Create me a GitHub repo, publish it, and deploy to Vercel.
Give me both links when done.
```

Then to push updates:
```
Push the new version live please.
```

**To add a custom domain:**
1. Go to vercel.com → find your project → **Domains**
2. Type the domain you want → assign it
3. Done.

**To add analytics:**
1. Vercel dashboard → **Analytics** → **Enable**
2. Copy the code snippet it shows
3. Paste into Claude Code: `Add this analytics code to my website: [paste code]`

---

## The "MONEY" Framework (how to sell this)

| Letter | Step |
|---|---|
| **M** — Map | Find boring niches: plumbers, movers, gyms, dentists, restaurants |
| **O** — Obtain | Get leads: Google Maps scrape, LinkedIn, local directories |
| **N** — Nail | Build a beautiful site using this exact workflow |
| **E** — Execute | Give the first site to them **for free** — it costs you 30 mins |
| **Y** — Yield | Sell recurring: hosting ($99/mo), SEO ($299/mo), updates ($199/mo) |

**Target price point:** £2,000–£5,000 one-time + monthly retainer
**Time to build:** 30–60 minutes once you know this workflow

---

## Quick Reference — Prompts That Work

**Brand extraction handoff:**
```
Here is the brand data from [URL]. Run /asset-generation and give me my prompts.
```

**HTML clone:**
```
I've downloaded the HTML from their existing website. Use it to recreate their
site with our new scroll animation. Keep their logo, colours, and typography.
```

**Multi-page:**
```
Look at my current site, understand the design language, ask me which pages
I want, match the design exactly, add full SEO, make it responsive, update nav.
After all pages are done, run a full SEO audit and show me the report.
```

**Deploy:**
```
Create a GitHub repo, publish it, deploy to Vercel. Give me both links.
```

**Push update:**
```
Push the new version live please.
```

---

## Tools Summary

| Tool | URL | Cost | What for |
|---|---|---|---|
| Firecrawl | firecrawl.dev | Free tier | Brand extraction |
| Nano Banana 2 | (Jack's tool — check video description) | Paid | AI image generation |
| Midjourney | midjourney.com | $10/mo | Alternative image gen |
| Flux / Ideogram | ideogram.ai | Free tier | Alternative image gen |
| Hailuoai | hailuoai.com | Free tier | Kling video generation |
| GitHub | github.com | Free | Code hosting |
| Vercel | vercel.com | Free hobby plan | Website hosting |

---

*Built with Claude Code + VOID Digital Studio workflow*
