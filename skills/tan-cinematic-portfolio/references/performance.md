# Performance and Accessibility

## Performance Budget

- Prefer one continuously rendering WebGL canvas in the visible viewport.
- Cap DPR around `1–1.5`; use `1` for dense scenes and mobile.
- Begin around 2,000–6,000 shader points, then profile on mid-range mobile.
- Generate typed arrays, geometries, materials, and uniforms once.
- Mutate Three.js objects through refs; do not set React state in `useFrame`.
- Use passive scroll listeners and `requestAnimationFrame` for pointer work.
- Suspend, invalidate, or stop loops when off-screen or when the document is hidden.
- Use `next/image` for raster media and keep stable aspect ratios.

## Cheap Effects First

1. Static CSS.
2. CSS transform/opacity transition.
3. CSS keyframes.
4. Framer Motion or GSAP on DOM transforms.
5. Canvas/WebGL only when thousands of elements, geometry, depth, or shaders justify it.

Large blurred layers can be more expensive than expected. Limit their number, size, and overlap on mobile.

## Lifecycle Checklist

- Keep the same callback reference when adding and removing GSAP ticker callbacks.
- Cancel every animation frame.
- Remove resize, scroll, mouse, and media-query listeners.
- Kill timelines and revert GSAP contexts.
- Destroy Lenis/OGL renderers and dispose Three.js resources where ownership is manual.
- Avoid timers that simulate loading when real readiness can be observed.

## Current Source Strengths

- Hero caps DPR and disables antialiasing.
- Particle buffers and uniforms use memoization.
- Scroll progress reaches shaders through refs.
- Particle fragment shader uses squared distance in the hero.
- Infinite skill marquees use CSS instead of per-frame React animation.
- OGL particles reduce count on mobile and skip rendering during active scroll.
- Pointer-only cursor is hidden below desktop.
- GSAP contexts and matchMedia are generally reverted.

## Current Source Risks to Fix Before Calling It Optimized

- Several React Three Fiber canvases render continuously even off-screen.
- Large 120–200px CSS blurs and oversized layers can increase raster cost.
- `SmoothScrolling` adds an anonymous ticker callback and removes a different function, so cleanup may leak.
- Reduced-motion handling is missing across Lenis, GSAP, Framer Motion, marquee, and WebGL.
- The custom cursor hides the native cursor globally even when JS/WebGL behavior fails.
- The preloader simulates delay rather than reflecting real asset readiness.
- The project theatre uses a very tall `900vh` scroll distance.
- Multiple animation systems increase coordination and bundle cost.
- WebGL canvas fallback and context-loss handling are absent.

## Accessibility Baseline

- Never hide the native cursor on coarse pointers or reduced-motion devices.
- Preserve visible focus rings.
- Keep semantic links and buttons under visual layers.
- Mark decorative canvases and icons hidden from assistive technology.
- Provide useful image alternatives and a non-WebGL route to project content.
- Do not let pinned sections trap keyboard or touch users.
- Maintain readable contrast on moving backgrounds.
