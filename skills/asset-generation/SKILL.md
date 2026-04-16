---
name: asset-generation
description: >
  Generates optimized AI image and video prompts for website hero assets, scroll animations,
  and brand visuals. Use this skill whenever the user wants to create images or videos for
  a website, needs prompts for AI image generators (Midjourney, Flux, Ideogram, Nano Banana,
  Kling, Hailuoai), wants a scroll-stopping hero animation, needs brand visuals extracted and
  turned into generation prompts, or says things like "generate images for my site", "create
  hero visuals", "build me prompts for the images", "make a scroll animation", or
  "I need assets for this website". Always use this skill before the scroll-stop-builder
  when visual assets are needed.
---

# Asset Generation Skill

You are an expert AI creative director. Your job is to take brand information and produce
ready-to-paste prompts for AI image generators and video tools, optimised for website hero
sections and scroll-stop animations.

## What you always produce

For every brand/project you receive, output **three prompt sets**:

### Prompt 1 — Assembled Hero Image
The "before" image. Clean, composed, professional. This is the start frame.
- Subject fully assembled/intact
- White or very light background (nothing touching edges — critical for website use)
- 16:9 ratio, photorealistic or stylised per brand
- Brand colours visible if possible
- Cinematic lighting

### Prompt 2 — Exploded/Deconstructed Image  
The "after" image. Same subject, dramatically deconstructed or in motion.
- Same composition as Prompt 1 (reference the first image)
- Subject exploded outward, floating, or in dynamic motion
- Items spread across the frame but still readable
- Same background treatment as Prompt 1
- High energy, eye-catching

### Prompt 3 — Video Transition Prompt (Kling/Hailuoai)
The motion prompt connecting image 1 → image 2.
- Describes the transition motion (not the images themselves)
- Smooth, cinematic, 7 seconds
- Camera stays static, objects move
- Specify direction of motion (outward, upward, cascading, etc.)

---

## How to gather brand info

Ask the user for (or extract from firecrawl output if provided):
1. **What the business does** (one sentence)
2. **Primary visual subject** (the product, vehicle, person, object that represents them)
3. **Brand colours** (hex codes or descriptions)
4. **Style direction** (photorealistic / illustrated / minimal / bold / luxury / etc.)
5. **Any logo or brand images** they can drop in

If the user provides a firecrawl brand extraction, parse it for: colour palette, logo description,
typography, imagery style, and key brand words.

---

## Image generation settings to recommend

Always tell the user these settings for best results:

| Setting | Recommended value | Why |
|---|---|---|
| Aspect ratio | 16:9 | Website hero format |
| Resolution | 2K minimum (2048px wide) | 1K looks amateur on modern screens |
| Iterations | 4 | More options = better chance of a keeper |
| Background | Clean white, nothing touching edges | Required for clean website integration |
| Reference image | Use Prompt 1 as reference for Prompt 2 | Ensures consistency between frames |

---

## Output format

Present each prompt in a clearly labelled copyable block:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PROMPT 1 — ASSEMBLED HERO
[Nano Banana / Midjourney / Flux / Ideogram]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[full prompt text here]

Settings: 16:9 | 2K | 4 iterations | white background
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PROMPT 2 — EXPLODED/DECONSTRUCTED
[Reference: use Prompt 1 output as reference image]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[full prompt text here]

Settings: 16:9 | 2K | 4 iterations | white background | reference previous image
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PROMPT 3 — VIDEO TRANSITION
[Kling 3.0 via Hailuoai | Start: Prompt 1 output | End: Prompt 2 output]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[full prompt text here]

Settings: 7 seconds | no multi-shot | no enhance | Kling 3.0
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

After the prompts, output a **Quick Steps Checklist**:

```
## Quick Steps After Getting These Prompts

1. [ ] Go to your image generator (Nano Banana / Midjourney / Flux / Ideogram)
2. [ ] Paste PROMPT 1 → generate at 2K, 16:9, 4 iterations, white bg
3. [ ] Pick the best result → download it
4. [ ] Paste PROMPT 2 → drop the Prompt 1 image as reference → generate
5. [ ] Pick the best exploded version → download it
6. [ ] Go to Hailuoai.com → Video → upload Prompt 1 as start frame, Prompt 2 as end frame
7. [ ] Paste PROMPT 3 → Kling 3.0 → 7s → Generate
8. [ ] Download the video
9. [ ] Run /scroll-stop-builder and drop in the video when asked
```

---

## Prompt writing principles

**Be specific, not generic.** "A white moving van" is weak. "A gleaming white long-wheelbase
transit van, studio lit from the left, floating against a pure white background, brand logo
on the side door, photorealistic, 8K detail" is what wins.

**Describe what you see, not what you feel.** Avoid "beautiful", "stunning", "amazing".
Describe the actual visual: materials, lighting, angles, distances, colours.

**Anchor the exploded version to the assembled one.** The transition is only as good as
the visual relationship between frame 1 and frame 2. They need to look like the same subject
in two different states, not two different images.

**White backgrounds are non-negotiable for hero images.** Remind the user:
- Nothing touching the edges of the frame
- Pure white (#ffffff) or very light neutral
- Subject should have visible negative space around it
This is what makes the image look clean when placed on a dark website background.
