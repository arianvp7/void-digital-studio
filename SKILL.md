---
name: 3d-asset-generator-website
description: >
  Builds a complete website with a 3D asset generator panel on the left side. Use this skill whenever the user asks to create, build, or add a 3D asset generator, 3D model viewer, 3D object creator, or any interactive 3D panel to a website — even if they don't say "skill" or "Three.js". This includes requests like "build a site with a 3D generator on the left", "add a 3D model panel", "create a website with a 3D viewer", "make something with Three.js on the side", or "I want a 3D asset creator layout". Always invoke this skill for any website featuring a 3D panel, viewer, or generator.
---

## Purpose

Generate a complete, interactive website with a 3D asset generator panel on the left and a controls/output panel on the right. The 3D panel uses Three.js for rendering and supports real-time generation and manipulation of 3D assets. Output is a single self-contained HTML file (with embedded CSS and JS) saved to the `assets/` directory.

---

## Default layout

```
┌──────────────────────┬──────────────────────┐
│                      │                      │
│   3D Asset Panel     │   Controls / Info    │
│   (Three.js canvas)  │   Panel              │
│                      │                      │
│   - Orbit controls   │   - Asset type       │
│   - Live preview     │   - Parameters       │
│   - Animated render  │   - Generate button  │
│                      │   - Export option    │
└──────────────────────┴──────────────────────┘
```

| Setting | Default |
|---|---|
| Layout | 50/50 split, left = 3D panel, right = controls |
| Renderer | Three.js (CDN) with OrbitControls |
| Background | Dark (#0f0f0f) with subtle grid or gradient |
| Asset types | Geometric primitives by default (customize per request) |
| Animation | Auto-rotate on idle, pause on interact |
| Output | Single HTML file in `assets/` |

---

## Step-by-step workflow

### Step 1 — Understand the request

Identify:
- What kind of 3D assets to generate (shapes, models, terrain, particles, custom geometry?)
- What parameters the user wants to control (size, color, complexity, material, etc.)
- Any style preferences (dark/light theme, minimal/detailed UI)
- Whether export/download of the 3D asset is needed

If critical details are missing, make sensible defaults and note them — don't ask for everything upfront.

### Step 2 — Plan the page

Decide:
- Left panel: what's in the 3D scene (lights, camera, asset, background)
- Right panel: what controls to expose and how to lay them out
- Color scheme and overall aesthetic
- Any animations or interactivity beyond orbit controls

### Step 3 — Build the HTML file

Write a single self-contained HTML file with:

**Structure:**
```html
<!DOCTYPE html>
<html>
<head>
  <!-- meta, title, embedded CSS -->
</head>
<body>
  <div class="app">
    <div class="panel-3d">
      <canvas id="three-canvas"></canvas>
    </div>
    <div class="panel-controls">
      <!-- controls, sliders, buttons, info -->
    </div>
  </div>
  <!-- Three.js from CDN + OrbitControls + embedded JS -->
</body>
</html>
```

**Three.js setup (always include):**
- Load Three.js and OrbitControls from CDN (use unpkg or jsdelivr)
- Set up `WebGLRenderer` sized to fill the left panel, with `antialias: true`
- Add `AmbientLight` + `DirectionalLight` for good default lighting
- Add `OrbitControls` with damping enabled
- Use `requestAnimationFrame` render loop
- Handle window resize to keep canvas responsive

**Controls panel (right side):**
- Use range sliders, color pickers, select dropdowns, or number inputs as appropriate
- Wire every control to update the 3D scene in real time (no page reload)
- Include a prominent "Generate" or "Randomize" button
- Show asset metadata (vertex count, dimensions, etc.) if useful

**Style principles:**
- Dark theme by default (`#0f0f0f` background, `#1a1a2e` panels, accent in blue/purple)
- Clean sans-serif font (system font stack or Google Fonts)
- Responsive: panels stack vertically on narrow screens
- Smooth transitions on UI interactions

### Step 4 — Save the file

Save the output to `assets/[descriptive-name].html`. Use a name that describes the generator, e.g.:
- `assets/3d-geometry-generator.html`
- `assets/3d-terrain-generator.html`
- `assets/3d-particle-generator.html`

### Step 5 — QA checklist

Before finishing, verify:
- [ ] Three.js loads correctly from CDN (no CORS or path issues in a standalone file)
- [ ] Canvas fills the left panel and resizes with the window
- [ ] OrbitControls work (rotate, zoom, pan)
- [ ] All controls on the right actually update the 3D scene
- [ ] No JavaScript errors in the console
- [ ] Page looks good at 1280px wide and at mobile widths
- [ ] "Generate" action produces a visible, meaningful change

Report the file path and a brief description of what controls are available.

---

## CDN references (use these)

```html
<!-- Three.js core -->
<script src="https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.min.js"></script>
<!-- OrbitControls -->
<script src="https://cdn.jsdelivr.net/npm/three@0.160.0/examples/js/controls/OrbitControls.js"></script>
```

---

## Example assets to generate

| Request | What to build |
|---|---|
| "geometric shapes" | Randomizable geometry (box, sphere, torus, icosahedron) with material controls |
| "terrain" | Procedural heightmap plane with noise-based displacement |
| "particles" | Particle system with count, speed, spread, and color controls |
| "low-poly" | Low-poly mesh generator with face color randomization |
| "crystals" | Extruded crystal/gem shapes with metalness and roughness controls |

Default to geometric shapes if the user doesn't specify.
