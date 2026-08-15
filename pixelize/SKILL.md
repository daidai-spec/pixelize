---
name: pixelize
description: Generate clean, grid-consistent pixel-art images from a user-provided image or text description. Use when Codex needs to convert an image into pixel art while preserving its subject and composition, or create a pixel-art scene, character, landscape, object, or other visual from text. Support 16, 32, and 64 logical pixel grids plus preserved, white, transparent, or replaced backgrounds.
---

# Pixel Art Generator

Read [references/pixel-style-guide.md](references/pixel-style-guide.md) before starting. Use the image generation tool to redraw the source as intentional, handcrafted pixel art. Do not use mechanical downscaling or mosaic filtering as the default conversion method.

Classify the content before generating:

- **Character-primary**: a person, creature, or isolated object is the main subject and the environment is supporting context. Use the general style guide.
- **Scene-primary**: the environment, architecture, interior, landscape, route, or spatial layout is the main subject. Also read [references/scene-style-guide.md](references/scene-style-guide.md) and use its information hierarchy.

For mixed images, choose scene-primary when recognizing the place or spatial layout matters more than recognizing any single character.

## Workflow

1. Identify the input mode:
   - **Image to pixel**: the user supplies a reference image.
   - **Text to pixel**: the user supplies a description only.
2. Classify the content as character-primary or scene-primary. For scene-primary work, read and apply the scene style guide.
3. Determine the pixel-art detail level. Use the user-specified `16`, `32`, or `64`; default to `32`.
4. Read [references/effect-reference-guide.md](references/effect-reference-guide.md) and inspect the visual calibration image for the selected content type and detail level. For a multi-level comparison, inspect every requested calibration image before generating.
5. Determine the background behavior:
   - For image-to-pixel, preserve the original background and composition by default.
   - Use a pure white background only if requested.
   - Use transparency only if requested.
   - Replace the background only if the user asks for a new scene.
6. Compose a concise generation prompt from the user's content, the applicable style guide, and the calibrated effect level, then generate the image.
7. Verify that the result matches the corresponding calibration image in pixel-cluster scale, information density, and completion level while preserving the user's own content. Do not accept a result that resembles a mechanical mosaic or visually falls into another preset.

## Image-to-pixel requirements

Preserve the original subject, proportions, framing, key details, spatial layout, and background unless the user explicitly requests a change. For character-primary work, deliberately reconstruct the silhouette, facial features, clothing panels, and modest stepped shading with purposeful pixel clusters. Retain clear dark outlines and restrained 2-step form modeling where it clarifies the source. For scene-primary work, preserve the spatial skeleton and landmarks, then simplify environmental information according to the scene style guide. Do not over-render materials, add dense texture, change the source identity, or add unrelated content. Do not use a filter-like conversion.

## Text-to-pixel requirements

Create a complete, readable pixel-art image that directly represents the request. Use a simple composition by default. Add scene elements only when they support the requested content.

## Prompt construction

Include these elements when relevant:

`mode + subject + essential visual features + composition/background + logical grid + palette/shading constraints + exclusions`

Always state that pixels must be uniform square blocks with hard edges and no anti-aliasing, blur, smooth gradients, random noise, watermarks, or unintended text.

## Grid selection

- **16**: simplified sprite detail; preserve the defining silhouette and the few most recognizable features.
- **32**: default; a polished, readable hand-drawn pixel illustration with clear character features and clothing structure.
- **64**: high-detail pixel illustration; preserve fine costume, facial, object, or environmental details using smaller clusters.

For scene-primary work, use the scene-specific definitions in [references/scene-style-guide.md](references/scene-style-guide.md). Generate each requested preset as an independent redraw; never create `16` or `32` by shrinking a more detailed result.

Use the bundled calibration images only as effect-degree references. Do not copy their character identity, pose, costume, architecture, landscape, camera angle, palette, lighting, background, or objects into a new request.

Treat these as detail presets, not literal output-pixel or block dimensions. Keep the displayed subject size and requested aspect ratio unchanged.

## Output

Present the generated image without adding a post-generation explanation. If essential input is missing, ask one concise question before generating.
