# Pixel Style Guide

## Purpose

Generate clean, intentional pixel-art images from either a reference image or a text description. Preserve recognizability, use a consistent pixel grid, and avoid results that merely look like a pixelation filter. Apply the retro game era language, palette behavior, and exclusions from `retro-game-style-guide.md` to every result.

## Input modes

### Image to pixel

Convert the provided image into pixel art. Preserve the original subject, silhouette, proportions, composition, key details, and background by default. Change only the rendering style. Add restrained pixel-art form modeling only where it reinforces readability: simple stepped shadows, small highlights, and separation between overlapping parts.

Override the background only when the user explicitly requests a white background, transparent background, or replacement scene.

### Text to pixel

Generate a complete pixel-art image that directly represents the user's text. Choose a simple, readable composition when the user does not specify one. Keep the main subject clear and make all supporting elements relevant to the requested content.

## Pixel grid

Use one consistent pixel-cluster scale across the entire image. `16`, `32`, and `64` are hand-drawn pixel-art detail presets, not literal output-pixel or block dimensions. Keep the displayed subject size unchanged; reconstruct the image with intentional pixel clusters rather than mechanically shrinking it.

- `16`: simplified sprite detail; retain silhouette and defining features.
- `32`: standard, polished pixel illustration; retain facial features, clothing structure, and readable stepped shading.
- `64`: high-detail pixel illustration; retain fine visual features through smaller, deliberate pixel clusters.

Keep every pixel block at the same scale. Use square pixels, clean pixel clusters, hard edges, and nearest-neighbor scaling. Never mix pixel sizes.

For non-square outputs, preserve the selected hand-drawn detail level across the requested aspect ratio.

## Shape and detail

Simplify details into readable pixel clusters while preserving defining features. Prioritize silhouette, proportions and composition, identity-defining features, important objects and landmarks, then decorative details.

Do not add unrelated objects, extra limbs, distorted anatomy, or meaningless details.

## Color and shading

Use a limited, deliberate palette with discrete color steps.

- `16`: 4–8 colors.
- `32`: 8–16 colors.
- `64`: 16–32 colors.

Use flat color regions, compact hue-shifted ramps, and clear value separation. Apply simple stepped shading when needed; do not use smooth gradients. Use bright accent colors only to clarify the focal point or an important detail. Prefer colored shadows and colored highlights over pure black and pure white whenever possible. Use patterned dithering sparingly and intentionally; never use it as uniform surface noise.

For a character or object conversion, use a restrained enhancement layer: a simple shadow under a helmet rim or chin, small darker overlap planes, selective garment-fold clusters, and occasional clustered highlights on curved or hard surfaces. Prefer a clear outline and 1–2 discrete shading steps over dense rendering. Preserve the source identity, pose, and composition; do not invent unrelated props, change the design, over-texture surfaces, or turn the source into a different character.

## Composition

For image conversion, retain the original framing and background by default. For text generation, establish a clear focal subject and readable visual hierarchy. Add scene detail only when it supports the requested content. Use isometric or angled views only when they improve a scene; do not force them for portraits, products, or faithful image conversions.

## Avoid

- anti-aliasing
- blurry pixels
- soft-focus rendering
- smooth gradients
- photographic texture
- generic pixelation filters
- random pixel noise
- inconsistent pixel density
- mixed pixel block sizes
- unreadable text
- logos or watermarks unless explicitly requested
