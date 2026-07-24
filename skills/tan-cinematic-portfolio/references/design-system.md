# Adaptive Composition and Theming

## Preserve the Host Brand

Treat the existing product or portfolio as the source of truth. Inspect:

- CSS variables and design tokens;
- current background and surface hierarchy;
- text and accent colors;
- font loading and type scale;
- radius, border, and shadow language;
- existing component variants;
- light, dark, and system themes.

Do not impose a predefined palette, background, gradient, or font. Effects must inherit the interface rather than repaint it.

## Map Tokens Into Effects

Prefer CSS custom properties so DOM and WebGL share one theme:

```css
:root {
  --effect-primary: var(--color-accent);
  --effect-secondary: var(--color-foreground);
  --effect-background: var(--color-background);
  --effect-muted: var(--color-muted);
}
```

Pass resolved tokens into shader uniforms or Three.js colors. When themes can change at runtime, update uniforms without rebuilding geometry.

Derive:

- particle core and edge colors from primary/secondary accents;
- fog and clear colors from the current surface;
- glow opacity from background luminance;
- text scrims from measured contrast needs;
- borders and trails from muted foreground tokens.

Use hard-coded colors only for a deliberately fixed art direction requested by the user.

## Contrast Modes

Choose blending from context:

- Additive blending works for luminous particles on darker surfaces.
- Normal alpha blending is more predictable on light or mixed surfaces.
- Multiply-like dark particles may work on bright editorial surfaces.
- Avoid `mix-blend-mode` when text or controls become unpredictable across sections.

Test every effect against the actual surrounding content. A shader that looks good on black may disappear or bloom badly on another background.

## Layout Archetypes

Use composition independently of palette:

1. Hero stage: full viewport with one dominant 3D object and a protected copy area.
2. Spatial marquee: oversized CSS perspective plane behind readable foreground content.
3. Scroll narrative: tall outer section, sticky viewport, and two or three meaningful states.
4. Project theatre: scroll-controlled 3D media path paired with semantic project links.
5. Sticky split: fixed context on one side and a normal document flow on the other.
6. Closing stage: restrained ambient effect supporting one clear action.

## Integration Rules

- Keep one dominant focal object per viewport.
- Protect readable content with placement, masking, fog, or a local scrim—not a forced page-wide background.
- Use oversized typography only when it matches the project's type system.
- Keep supporting copy narrow and stable while the visual moves.
- Preserve current radii and component shapes.
- On mobile, recompose rather than shrinking desktop geometry.
- Provide a static frame or lightweight CSS fallback.

## Source Palette as an Optional Example

The source portfolio uses near-black and editorial-white sections with amber accents, Outfit, and Playfair Display. These values explain the original screenshots only. They are not requirements of this skill and must not override another project's identity.
