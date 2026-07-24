---
name: tan-cinematic-portfolio
description: Design, build, audit, or extend cinematic developer portfolios with Tan's near-black and editorial-white visual system, amber accents, expressive serif typography, scroll choreography, restrained WebGL/Three.js scenes, and strict performance budgets. Use for portfolio pages, landing sections, project showcases, 3D hero visuals, motion systems, visual consistency reviews, or performance reviews of animation-heavy React/Next.js frontends.
---

# Tan Cinematic Portfolio

Create a premium, cinematic portfolio without turning every section into a demo reel. Preserve clarity, accessibility, and performance before spectacle.

## Workflow

1. Inspect the existing stack, components, assets, tokens, and animation ownership before editing.
2. Define the page's one visual idea and one hero effect. Avoid stacking unrelated effects.
3. Read [design-system.md](references/design-system.md) for color, type, layout, and component rules.
4. Read [motion-and-3d.md](references/motion-and-3d.md) when adding animation, scroll choreography, shaders, particles, or WebGL.
5. Read [performance.md](references/performance.md) before implementing or reviewing any continuous animation.
6. Reuse the project's existing libraries. Do not add an animation or 3D dependency when CSS or an installed library covers the effect.
7. Implement mobile and reduced-motion behavior at the same time as the desktop effect.
8. Validate responsive layout, keyboard focus, contrast, hydration, cleanup, and production build.

## Composition Rules

- Alternate immersive near-black stages with calm editorial-white sections.
- Use amber as a signal, not a fill: highlights, particles, focus rings, separators, and primary actions.
- Pair a geometric sans for structure with an italic display serif for emotional emphasis.
- Build hierarchy through scale, whitespace, sticky composition, and asymmetry before borders or shadows.
- Keep one dominant focal object per viewport.
- Use oversized typography as scenery; keep supporting copy narrow and readable.
- Prefer full-bleed stages, sticky split layouts, and image-led case-study rows over generic card grids.
- Use rounded geometry deliberately: pills for actions, large soft radii for media, circles for micro-controls.

## Motion Rules

- Assign one owner per effect: CSS for loops, Framer Motion for local React state/entrances, GSAP for timelines and ScrollTrigger, WebGL for geometry and particles.
- Animate transforms and opacity. Do not animate layout properties during scroll.
- Map scroll to a small number of meaningful visual states; do not animate every element.
- Keep continuous motion slow and ambient. Make interaction feedback short and decisive.
- Pause or reduce off-screen, hidden-tab, mobile, and reduced-motion animation.
- Keep custom cursors desktop-only and preserve the native cursor as a fallback.

## 3D Rules

- Use shaders and instanced/point geometry for thousands of repeated particles.
- Generate buffers and uniforms once; mutate refs inside the render loop.
- Cap device pixel ratio and lower particle counts on coarse pointers or narrow viewports.
- Prefer one active Canvas per viewport. Reuse or suspend scenes before adding another perpetual render loop.
- Use CSS perspective for decorative depth when real lighting, occlusion, or geometry is unnecessary.
- Treat 3D as narrative: infinity for continuity, helix for systems, particles morphing for evolution.

## Quality Gate

- Confirm the interface still works with WebGL disabled or reduced motion enabled.
- Confirm all effects clean up listeners, animation frames, tickers, timelines, and GPU resources.
- Confirm text remains legible over every visual state.
- Confirm the mobile layout does not merely shrink desktop composition.
- Confirm no visual effect blocks navigation, selection, touch scrolling, or keyboard use.
- Run the smallest existing lint/build check that exercises the changed surface.

## Source Profile

Read [project-profile.md](references/project-profile.md) when reproducing the source portfolio closely or explaining how its current implementation works.
