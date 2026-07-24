---
name: tan-cinematic-portfolio
description: Design, build, audit, or extend cinematic web experiences with reusable 3D/WebGL effects, GSAP scroll choreography, adaptive visual theming, strict performance budgets, and minimal clean-code organization. Use for portfolio pages, landing sections, 3D hero visuals, particle or shader effects, motion systems, animation architecture, or performance reviews of animation-heavy frontends.
---

# Tan Cinematic Portfolio

Create cinematic effects that adapt to the host project's brand. Preserve clarity, accessibility, maintainability, and performance before spectacle.

## Workflow

1. Inspect the existing stack, components, assets, tokens, and animation ownership before editing.
2. Preserve the project's existing colors, typography, and component language unless the user requests a redesign.
3. Define one visual idea and one hero effect. Avoid stacking unrelated effects.
4. Read [design-system.md](references/design-system.md) for adaptive theming, composition, and effect integration.
5. Read [motion-and-3d.md](references/motion-and-3d.md) when adding animation, scroll choreography, shaders, particles, or WebGL.
6. Read [performance.md](references/performance.md) before implementing or reviewing any continuous animation.
7. Read [clean-code.md](references/clean-code.md) before choosing dependencies, abstractions, or file structure.
8. Implement mobile and reduced-motion behavior with the desktop effect.
9. Validate responsive layout, keyboard focus, contrast, hydration, cleanup, and production build.

## Composition Rules

- Derive shader colors, glows, text contrast, and transparent layers from the host project's tokens.
- Do not introduce black, white, amber, gradients, or a new font unless they belong to the brief.
- Keep one dominant focal object per viewport.
- Protect content readability with placement, masking, contrast, or a local scrim.
- Preserve the host project's spacing, shape, typography, and layout language.
- Recompose effects for mobile instead of shrinking desktop geometry.

## Clean-Code Rules

- Understand the complete render and scroll flow before editing.
- Reuse an existing helper, component, token, or installed library before creating anything.
- Prefer CSS and browser APIs before JavaScript animation; prefer an installed dependency before adding one.
- Keep the smallest number of effects, components, files, props, and abstractions that solve the request.
- Give each animation one owner and each resource one lifecycle.
- Fix shared root causes instead of adding guards to every caller.
- Add one focused check for non-trivial animation or state logic.
- Record deliberate performance ceilings and their upgrade path in a `ponytail:` comment.

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
