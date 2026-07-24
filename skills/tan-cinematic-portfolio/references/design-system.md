# Design System

## Visual Direction

The style is a hybrid of:

- cinematic/Awwwards portfolio staging;
- editorial light-theme case studies;
- sci-fi particle and shader imagery;
- restrained luxury branding through warm amber, serif italics, and large whitespace.

The emotional arc alternates “void and energy” with “clarity and proof.” Dark sections establish identity and spectacle; white sections explain experience and work.

## Palette

Core colors:

| Role | Value | Usage |
| --- | --- | --- |
| Deep stage | `#020202` | Primary cinematic background |
| Pure black | `#000000` | Root background, high contrast |
| Elevated dark | `#0a0a0a` / `#111111` | Cards, modal, dark controls |
| Paper | `#ffffff` | Editorial sections |
| Ink | `#111111` / `#222222` | Headings on paper |
| Body gray | `#555555` / `#666666` | Supporting copy |
| Line gray | `#b0b5b9` | Quiet separators |
| Soft media gray | `#e0e3e5` | Project image beds |
| Signature amber | `#ffaa40` | Brand signal |
| Deep amber | `#ff8800` / `#d97706` | Gradient endpoint and accessible icon tone |

Use purple only as a rare atmospheric secondary accent. Avoid broad rainbow gradients. Amber-to-white or amber-to-dark transitions fit the identity.

## Typography

- Primary: Outfit, weights 400–900. Use for headings, body, controls, and oversized display words.
- Accent: Playfair Display, normal/italic, weights 400–800. Use italic for one meaningful phrase, never whole paragraphs.
- Technical labels: the platform monospace stack through `font-mono`.
- Display treatment: tight tracking, `0.95–1.05` line-height, very large responsive sizing.
- Body treatment: 14–20px, relaxed line-height, muted foreground, narrow measure around 28–40rem.
- Labels: 10–14px, uppercase, `0.2em` tracking.

The contrast between geometric sans and expressive serif creates the premium signature. Do not introduce a third decorative family.

## Spacing and Shape

- Content max width: approximately 1400–1800px depending on stage.
- Page gutters: 24px mobile, 48px tablet, 96px large desktop where composition permits.
- Section rhythm: 96–128px for standard sections; viewport-height or multi-viewport stages for narrative scroll.
- Media radius: 20–40px.
- CTA radius: full pill or 32–40px.
- Borders: low-contrast hairlines.
- Shadows: sparse and diffuse; media hover may use one soft elevation.

## Layout Archetypes

1. Hero stage: full viewport; copy occupies the left 50–60%; 3D focal object sits right/behind.
2. Spatial marquee: oversized plane rotated in 3D with centered foreground copy.
3. Scroll narrative: 300–400vh section with a sticky viewport and three content states.
4. Project theatre: long sticky WebGL stage with oversized typography crossing the scene.
5. Editorial work index: 45/55 sticky split; fixed heading left, vertical project stream right.
6. Closing stage: centered CTA and orbital visual on a dark background.

On mobile, move copy toward the bottom, reduce visual scale, add a contrast scrim, and collapse split layouts into a single stream.

## Component Language

- Primary CTA: white or amber pill, dark text, circular arrow capsule.
- Secondary action: quiet underline or bordered white pill.
- Skill cards: elevated-dark surface, low-opacity white border, large radius.
- Project media: fixed aspect ratio, image zoom around 1.03, subtle inner ring.
- Modal: near-black translucent panel, fine border, small amber top glow.
- Header/cursor: mix-blend-difference for contrast over theme transitions.

## Avoid

- Generic three-column card grids.
- Amber covering large page areas.
- Multiple competing serif phrases in one viewport.
- Heavy shadows, generic glassmorphism, or blue SaaS gradients.
- Decorative 3D without a narrative role.
- Uniform dark sections with no editorial breathing room.
