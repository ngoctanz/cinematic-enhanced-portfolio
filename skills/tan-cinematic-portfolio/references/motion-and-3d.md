# Motion and 3D

## Library Ownership

| Need | Use |
| --- | --- |
| Infinite marquee or simple hover | CSS animation/transition |
| Entrance, presence, modal, local scroll value | Framer Motion |
| Sequenced reveal or imperative interaction | GSAP |
| Pinned/scrubbed narrative | GSAP ScrollTrigger |
| Smooth wheel integration | Lenis synchronized with GSAP ticker |
| React 3D scene | Three.js through React Three Fiber |
| Helpers, stars, float, texture, line | React Three Drei |
| Lightweight isolated particle canvas | OGL |

Do not let two libraries control the same property.

## Motion Grammar

- Entrances: translate 30–60px, fade, optional blur from 10px; 0.6–1.4s; strong ease-out.
- Stagger: about 0.1–0.15s for headings and lists.
- Hover: scale no more than 1.03–1.05 for media; rotate arrows about 45°; 300–700ms.
- Scroll: scrub linearly for spatial travel; ease content transitions separately.
- Ambient: slow rotation, float, star movement, or particle flow with low amplitude.
- Theme transition: five horizontal blinds scaling on Y with a short stagger.

## Source 3D Vocabulary

- Infinity ribbon: 6,000 GPU points following a parametric figure-eight, source-themed luminous shader, slow flow.
- Liquid ribbon: 3,500 points morphing between wave, helix, and infinity according to scroll progress.
- Particle core: 2,700 points morphing between galaxy, gyroscope/atom, and Fibonacci sphere.
- Project helix: screenshots mapped onto cylinder segments and moved along a helix by synchronized rotation and Y translation.
- CSS spatial grid: four marquees on a plane transformed with `rotateX(60deg) rotateZ(-35deg)`.
- OGL particles: lightweight standalone point cloud with mobile count reduction and scroll-time render skipping.

## Shader Patterns

- Store per-particle curve coordinate, width, random offset, size, and color in buffer attributes.
- Compute deformation in the vertex shader.
- Use `gl_PointCoord` and discard outside a circle in the fragment shader.
- Use squared distance when the exact length is unnecessary.
- Disable depth writes for transparent points.
- Choose additive blending for luminous dust on suitable dark surfaces and normal blending when the background makes additive bloom unreadable.
- Interpolate narrative states branchlessly with `smoothstep` and `mix`.

## Scroll Architecture

- Use a tall outer section and one `position: sticky` viewport.
- Map normalized progress to a small state machine.
- Pass progress into WebGL through a mutable ref to avoid React renders per scroll frame.
- Use one GSAP timeline per scroll stage.
- Use `gsap.matchMedia()` for genuinely different mobile travel distances.
- Revert GSAP contexts and matchMedia instances on unmount.

## Reduced Motion

When `prefers-reduced-motion: reduce`:

- remove Lenis smoothing;
- disable scrubbed/pinned theatre where it harms navigation;
- render 3D in a stable representative state or use a static fallback;
- stop marquees and ambient loops;
- keep short opacity-only feedback for state clarity.
