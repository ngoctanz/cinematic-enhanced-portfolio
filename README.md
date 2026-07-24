# Cinematic Enhanced Portfolio

An AI-agent skill for designing and building cinematic developer portfolios with a premium editorial identity, scroll choreography, purposeful 3D visuals, and practical performance budgets.

The skill distills the visual system of a production Next.js portfolio into reusable guidance for Codex and other skill-compatible coding agents.

## What This Skill Creates

Use it to build or improve:

- cinematic portfolio homepages;
- immersive hero sections;
- 3D developer and creative portfolios;
- scroll-driven storytelling;
- editorial project showcases;
- WebGL particle and shader effects;
- premium transitions and micro-interactions;
- animation-heavy React or Next.js interfaces;
- performance and visual-consistency audits.

It is not a component library or fixed template. The skill teaches the agent how to reproduce the design language while adapting composition and implementation to each project.

## Design Direction

The visual style combines:

- Awwwards-inspired cinematic staging;
- dark sci-fi environments with particles and shaders;
- clean editorial sections on white backgrounds;
- oversized geometric typography;
- expressive italic serif accents;
- asymmetric layouts and large whitespace;
- warm amber branding;
- restrained agency-style motion.

The typical experience alternates between immersive and informational modes:

```text
Dark spectacle
→ Spatial tech stack
→ Theme transition
→ White editorial content
→ Scroll-driven 3D story
→ Cinematic project theatre
→ Editorial project list
→ Dark closing CTA
```

Dark sections create identity and emotion. White sections provide clarity, proof, and breathing room.

## Color System

| Role | Color | Usage |
| --- | --- | --- |
| Cinematic background | `#020202` | Hero, skill stage, closing CTA |
| Root black | `#000000` | Page foundation |
| Elevated dark | `#0a0a0a`, `#111111` | Cards, modal, controls |
| Editorial paper | `#ffffff` | About, evolution, project sections |
| Primary ink | `#111111`, `#222222` | Headings on white |
| Supporting gray | `#555555`, `#666666` | Descriptions and metadata |
| Separator | `#b0b5b9` | Quiet borders and rules |
| Media surface | `#e0e3e5` | Project image backgrounds |
| Signature amber | `#ffaa40` | Brand accent |
| Deep amber | `#ff8800`, `#d97706` | Gradients, icons, contrast |

Amber is treated as a signal rather than a large background fill. It appears in particles, highlighted words, focus rings, separators, icons, and primary calls to action.

## Typography

The source system pairs:

- **Outfit** — geometric sans for display headings, body copy, navigation, and controls.
- **Playfair Display** — expressive serif, usually italic, for emotional emphasis.
- **Monospace** — uppercase technical labels, categories, indexes, and secondary actions.

Typical treatment:

```text
Outfit oversized + tight tracking
Playfair italic for one meaningful phrase
Mono uppercase + wide tracking for metadata
```

The skill avoids adding extra decorative fonts. Hierarchy comes from scale, weight, whitespace, and contrast.

## Layout Language

The included guidelines cover:

- full-viewport hero stages;
- left-copy/right-visual split compositions;
- sticky multi-viewport narratives;
- editorial `45/55` project layouts;
- oversized typography used as scenery;
- full-bleed WebGL project theatres;
- 3D perspective marquees;
- image-led case-study rows;
- dark-to-light blind transitions;
- responsive mobile recomposition.

Mobile layouts are treated as their own composition: visuals are reduced, copy moves to safer positions, contrast scrims are introduced, and sticky splits collapse into readable vertical flows.

## Motion System

The skill gives each animation tool a clear responsibility:

| Requirement | Preferred tool |
| --- | --- |
| Hover, simple transition, infinite marquee | CSS |
| Component entrance, modal, presence state | Framer Motion |
| Sequenced reveal and imperative interaction | GSAP |
| Pinned or scrubbed scroll narrative | GSAP ScrollTrigger |
| Smooth wheel scrolling | Lenis synchronized with GSAP |
| React-based 3D scene | Three.js + React Three Fiber |
| Stars, float, textures, helper geometry | React Three Drei |
| Small isolated particle canvas | OGL |

### GSAP Patterns

The guidance includes:

- timelines with staggered text reveals;
- transform-and-opacity-first animation;
- `gsap.context()` cleanup;
- responsive animation through `gsap.matchMedia()`;
- pinned and scrubbed `ScrollTrigger` sections;
- synchronized movement along a 3D helix;
- theme transitions using staggered blinds;
- high-frequency pointer tracking through `gsap.quickTo()`;
- correct Lenis and GSAP ticker integration;
- reduced-motion behavior.

One animation library should own each property. GSAP, Framer Motion, and CSS should not compete over the same transform.

## 3D and WebGL

The skill documents reusable patterns for:

- particle-based infinity ribbons;
- wave-to-helix-to-infinity morphing;
- galaxy-to-atom-to-sphere particle transitions;
- project screenshots arranged along a 3D helix;
- GPU buffer attributes and shader uniforms;
- branchless state interpolation with GLSL `mix` and `smoothstep`;
- additive versus normal blending;
- mobile particle reduction;
- capped device pixel ratio;
- scroll progress passed through mutable refs;
- CSS perspective when real WebGL is unnecessary.

The original visual vocabulary includes:

| Effect | Technique |
| --- | --- |
| Infinity ribbon | 6,000 shader-driven GPU points |
| Liquid evolution ribbon | 3,500 morphing points |
| Particle system core | 2,700 points across three states |
| Project helix | Textured cylinder segments |
| Spatial skill wall | CSS 3D transforms and marquees |
| Ambient particles | Lightweight OGL point cloud |

3D must carry a narrative role—continuity, architecture, evolution, or project exploration—not exist as decoration alone.

## Performance Guidelines

The skill enforces:

- one dominant continuously rendering canvas per visible viewport;
- capped DPR, usually `1–1.5`;
- reduced particle counts on mobile;
- memoized typed arrays, geometry, materials, and uniforms;
- ref mutation instead of React state inside render loops;
- transform and opacity animation;
- passive scroll listeners;
- cancellation of animation frames and event listeners;
- GSAP timeline, context, ticker, and ScrollTrigger cleanup;
- off-screen and hidden-tab suspension;
- static or reduced-motion fallbacks;
- careful use of oversized blur layers;
- stable image aspect ratios and optimized images.

It also teaches the agent to choose the cheapest sufficient technique:

```text
Static CSS
→ CSS transition
→ CSS keyframes
→ DOM animation
→ Canvas/WebGL
```

## Accessibility Baseline

Visual polish must not remove:

- native cursor fallback;
- keyboard focus indicators;
- semantic links and buttons;
- readable contrast over moving visuals;
- reduced-motion support;
- touch scrolling;
- non-WebGL access to project content;
- useful image alternatives.

Pinned sections must not trap keyboard or touch users.

## Included Files

```text
skills/tan-cinematic-portfolio/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── design-system.md
    ├── motion-and-3d.md
    ├── performance.md
    └── project-profile.md
```

- `SKILL.md` — workflow, composition rules, motion ownership, 3D rules, and quality gate.
- `design-system.md` — palette, typography, spacing, shapes, layouts, and component language.
- `motion-and-3d.md` — animation responsibilities, GSAP choreography, shader patterns, and scroll architecture.
- `performance.md` — rendering budget, lifecycle checklist, performance risks, and accessibility.
- `project-profile.md` — source stack, page sequence, installed skills, strengths, and known inconsistencies.
- `openai.yaml` — Codex-facing display metadata and default prompt.

## Installation

The skill follows the shared `SKILL.md` format and can be installed for multiple coding agents with the same CLI.

### Interactive Installation

Let the CLI detect installed agents and ask where to place the skill:

```bash
npx skills add ngoctanz/cinematic-enhanced-portfolio \
  --skill tan-cinematic-portfolio
```

### Install for One Agent

| Agent | Command |
| --- | --- |
| Codex | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a codex` |
| Claude Code | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a claude-code` |
| Antigravity | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a antigravity` |
| Antigravity CLI | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a antigravity-cli` |
| Cursor | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a cursor` |
| Gemini CLI | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a gemini-cli` |
| GitHub Copilot | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a github-copilot` |
| OpenCode | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a opencode` |
| Cline | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a cline` |
| Windsurf | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a windsurf` |
| Kiro CLI | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a kiro-cli` |
| Roo Code | `npx skills add ngoctanz/cinematic-enhanced-portfolio -s tan-cinematic-portfolio -a roo` |

The long flags `--skill` and `--agent` are equivalent to `-s` and `-a`.

### Install for Several Agents at Once

Repeat `--agent` for each target:

```bash
npx skills add ngoctanz/cinematic-enhanced-portfolio \
  --skill tan-cinematic-portfolio \
  --agent codex \
  --agent claude-code \
  --agent antigravity \
  --agent cursor \
  -g -y
```

This installs the skill globally for all four agents without interactive prompts.

### Install for Every Detected Agent

```bash
npx skills add ngoctanz/cinematic-enhanced-portfolio \
  --skill tan-cinematic-portfolio \
  --agent "*" \
  -g -y
```

To install every skill from the repository for every detected agent:

```bash
npx skills add ngoctanz/cinematic-enhanced-portfolio --all
```

### Project or Global Scope

Project installation is the default:

```bash
npx skills add ngoctanz/cinematic-enhanced-portfolio \
  -s tan-cinematic-portfolio \
  -a claude-code
```

Use `-g` when the skill should be available in every project:

```bash
npx skills add ngoctanz/cinematic-enhanced-portfolio \
  -s tan-cinematic-portfolio \
  -a claude-code \
  -g
```

Common destinations include:

| Agent | Project location | Global location |
| --- | --- | --- |
| Claude Code | `.claude/skills/` | `~/.claude/skills/` |
| Antigravity | `.agents/skills/` | `~/.gemini/antigravity/skills/` |
| Antigravity CLI | `.agents/skills/` | `~/.gemini/antigravity-cli/skills/` |

The CLI normally uses a canonical copy with agent-specific symlinks. Add `--copy` when the environment does not support symlinks:

```bash
npx skills add ngoctanz/cinematic-enhanced-portfolio \
  -s tan-cinematic-portfolio \
  -a claude-code \
  --copy
```

### Use Without Installing

Generate a temporary prompt:

```bash
npx skills use \
  ngoctanz/cinematic-enhanced-portfolio@tan-cinematic-portfolio
```

Or start a supported agent with the temporary skill:

```bash
npx skills use ngoctanz/cinematic-enhanced-portfolio \
  --skill tan-cinematic-portfolio \
  --agent claude-code
```

### Manage Installed Skills

List installed skills:

```bash
npx skills list
```

Update an installed copy:

```bash
npx skills update tan-cinematic-portfolio
```

Remove it:

```bash
npx skills remove tan-cinematic-portfolio
```

The core `SKILL.md` and reference files are cross-agent instructions. `agents/openai.yaml` adds Codex-specific presentation metadata and is harmless when another agent does not use it.

## Usage

Invoke the skill explicitly:

```text
Use $tan-cinematic-portfolio to design a cinematic developer portfolio.
```

Example requests:

```text
Use $tan-cinematic-portfolio to redesign this portfolio without changing its content.
```

```text
Use $tan-cinematic-portfolio to create a full-screen hero with an amber particle ribbon.
```

```text
Use $tan-cinematic-portfolio to audit the GSAP, ScrollTrigger, and WebGL performance of this page.
```

```text
Use $tan-cinematic-portfolio to build an editorial project showcase that transitions from black to white.
```

```text
Use $tan-cinematic-portfolio to add reduced-motion and mobile fallbacks to these 3D sections.
```

## Recommended Stack

The skill works with any frontend stack, but its source implementation uses:

- Next.js;
- React;
- TypeScript;
- Tailwind CSS;
- GSAP and ScrollTrigger;
- Framer Motion;
- Lenis;
- Three.js;
- React Three Fiber;
- React Three Drei;
- OGL.

Do not install all of these automatically. Reuse the current project stack and add a dependency only when the requested effect genuinely requires it.

## Philosophy

```text
One visual idea per section.
One owner per animation.
One dominant focal object per viewport.
Performance and accessibility before spectacle.
```

The goal is not “more effects.” The goal is a memorable portfolio whose motion, typography, layout, and 3D language all communicate the same identity.
