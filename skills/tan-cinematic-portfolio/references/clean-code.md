# Minimal Clean-Code Workflow

Apply the Ponytail principle: the shortest correct path is the maintainable path.

## Decision Ladder

Stop at the first option that fully solves the request:

1. Skip a speculative effect or abstraction that has no current requirement.
2. Reuse code, tokens, types, components, or patterns already in the repository.
3. Use the language or browser standard library.
4. Use native CSS, SVG, Canvas, Web Animations, observers, or media queries.
5. Use an already-installed dependency.
6. Write the smallest local implementation.

Do not add a dependency for a few stable lines of platform code.

## Effect Selection

```text
Static CSS
→ CSS transition
→ CSS keyframes
→ Web Animations / DOM library
→ Canvas 2D
→ WebGL
```

Move down only when the previous level cannot deliver the required geometry, particle count, depth, or scroll coupling.

## File Organization

Keep effect code close to its owner:

```text
components/
  sections/
    hero.tsx
  effects/
    hero-particles.tsx
```

Split a file only when it creates a real boundary:

- reusable effect versus section content;
- renderer versus shader source;
- deterministic geometry generation versus React lifecycle;
- shared performance policy used by multiple effects.

Avoid:

- one-use factories;
- interfaces with one implementation;
- generic animation registries;
- configurable systems with only one actual configuration;
- wrapper components that only rename props;
- duplicated mobile and desktop components when media queries or parameters suffice.

## Animation Ownership

Assign one owner per concern:

- CSS owns continuous decorative loops and simple hover states.
- GSAP owns imperative sequences and ScrollTrigger timelines.
- Framer Motion owns component presence and local React-driven states.
- R3F or the renderer owns frame-by-frame 3D mutation.

Never let CSS, GSAP, and Framer Motion write the same transform.

## Data and Render Flow

- Generate deterministic or random buffers once.
- Store rapidly changing values in refs or renderer uniforms.
- Keep React state for UI state that affects rendering semantics.
- Keep project/content data outside animation timelines.
- Pass the smallest stable props into effects.
- Centralize shared scroll progress instead of adding parallel listeners.

## Lifecycle

Every effect should make ownership obvious:

```text
create → subscribe/start → update → unsubscribe/stop → dispose
```

Keep callback references so cleanup removes the exact callback that was registered.

## Root-Cause Fixes

Before patching an animation helper, search every caller. Fix shared lifecycle, sizing, timing, or fallback behavior once at the common boundary instead of adding local workarounds.

## Tests and Comments

- Trivial visual constants need no tests.
- Non-trivial geometry, parser, state mapping, or branching gets one focused runnable check.
- Test behavior or math, not implementation details or screenshots by default.
- Add a `ponytail:` comment only when accepting a real ceiling:

```ts
// ponytail: one active canvas; introduce scene pooling only if overlapping canvases become required.
```
