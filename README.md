# Cinematic Enhanced Portfolio

An AI-agent skill for building reusable 3D effects, scroll choreography, and animation-heavy web experiences with practical performance budgets and minimal clean-code organization.

The skill distills the effects architecture of a production Next.js portfolio into reusable guidance for Codex and other skill-compatible coding agents. It adapts to the host project's colors, typography, layout, and component language.

## What This Skill Creates

Use it to build or improve:

- immersive hero and landing-page effects;
- 3D developer and creative portfolios;
- scroll-driven storytelling;
- WebGL particle and shader effects;
- GSAP transitions and micro-interactions;
- animation-heavy React or Next.js interfaces;
- performance and lifecycle audits;
- clean organization of animation code.

It is not a fixed template, palette, or component library. The skill teaches the agent how to choose, create, organize, and optimize effects without replacing the product's existing identity.

## Brand-Adaptive by Default

The skill does **not** require:

- black or white backgrounds;
- amber accents;
- a specific gradient;
- Outfit or Playfair Display;
- dark mode;
- an Awwwards-style page layout;
- a full visual redesign.

Before generating an effect, the agent inspects the host project's:

- CSS variables and theme tokens;
- background luminance and contrast;
- fonts and type scale;
- radius, border, and shadow language;
- existing animation dependencies;
- responsive layout and reduced-motion policy.

Shader uniforms, glows, fog, particles, trails, and scrims are derived from those tokens. The original amber/black implementation remains only as an optional case study.

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

### Available GSAP Patterns

The guidance includes:

- timelines with staggered text reveals;
- transform-and-opacity-first animation;
- `gsap.context()` cleanup;
- responsive animation through `gsap.matchMedia()`;
- pinned and scrubbed `ScrollTrigger` sections;
- synchronized movement along a 3D helix;
- transitions using staggered blinds or project-specific shapes;
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

Reusable source effects include:

| Effect | Technique |
| --- | --- |
| Infinity ribbon | 6,000 shader-driven GPU points |
| Liquid evolution ribbon | 3,500 morphing points |
| Particle system core | 2,700 points across three states |
| Project helix | Textured cylinder segments |
| Spatial skill wall | CSS 3D transforms and marquees |
| Ambient particles | Lightweight OGL point cloud |

Every effect can be recolored and recomposed for the current product. 3D must carry a narrative or interaction role rather than exist as decoration alone.

## Clean Code and Ponytail

The skill includes a minimal engineering workflow inspired by Ponytail:

```text
Skip speculative work
→ Reuse repository code
→ Use stdlib/browser APIs
→ Use native CSS/SVG/Canvas
→ Use an installed dependency
→ Write the smallest local implementation
```

Its code-organization rules include:

- understand the complete render and scroll flow before editing;
- fix root causes at the shared boundary;
- keep one owner per animation property;
- keep rapidly changing values out of React state;
- generate geometry and buffers once;
- avoid one-use factories, wrappers, and interfaces;
- split files only at real lifecycle or reuse boundaries;
- add one focused check for non-trivial geometry or state mapping;
- document deliberate ceilings with a `ponytail:` comment;
- do not add libraries for effects native CSS or browser APIs already cover.

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
    ├── clean-code.md
    ├── motion-and-3d.md
    ├── performance.md
    └── project-profile.md
```

- `SKILL.md` — workflow, composition rules, motion ownership, 3D rules, and quality gate.
- `design-system.md` — adaptive theming, token mapping, blending, composition, and fallback rules.
- `clean-code.md` — Ponytail decision ladder, file organization, ownership, lifecycle, and root-cause fixes.
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
Use $tan-cinematic-portfolio to add a brand-adaptive, high-performance 3D effect.
```

Example requests:

```text
Use $tan-cinematic-portfolio to add a particle hero while preserving this project's visual identity.
```

```text
Use $tan-cinematic-portfolio to create a particle ribbon using the project's existing color tokens.
```

```text
Use $tan-cinematic-portfolio to audit the GSAP, ScrollTrigger, and WebGL performance of this page.
```

```text
Use $tan-cinematic-portfolio to organize these GSAP and Three.js effects with the fewest clean abstractions.
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
The host project owns its colors and typography.
Reuse and native features before new dependencies.
Performance and accessibility before spectacle.
```

The goal is not “more effects.” The goal is a memorable portfolio whose motion, typography, layout, and 3D language all communicate the same identity.
