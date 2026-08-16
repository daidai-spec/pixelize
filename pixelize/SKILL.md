---
name: pixelize
description: Generate handcrafted retro game pixel illustrations from a user-provided image or text description. Use when Codex needs to convert a character, object, landscape, architecture, interior, or scene into an 8-bit or 16-bit-inspired pixel illustration while preserving its identity and composition, or create new retro game art from text. Support 16, 32, and 64 visual detail presets plus preserved, white, transparent, or replaced backgrounds.
---

# Retro Game Pixel Illustration Generator

Read [references/pixel-style-guide.md](references/pixel-style-guide.md) and [references/retro-game-style-guide.md](references/retro-game-style-guide.md) before starting. Use the image generation tool to redraw the source as intentional, handcrafted retro game pixel art. Do not use mechanical downscaling, mosaic filtering, or a smooth illustration with superficial pixel texture.

Classify the content before generating:

- **Character-primary**: a person, creature, or isolated object is the main subject and the environment is supporting context. Use the general style guide.
- **Scene-primary**: the environment, architecture, interior, landscape, route, or spatial layout is the main subject. Also read [references/scene-style-guide.md](references/scene-style-guide.md) and use its information hierarchy.

For mixed images, choose scene-primary when recognizing the place or spatial layout matters more than recognizing any single character.

## Workflow

1. Identify the input mode:
   - **Image to pixel**: the user supplies a reference image.
   - **Text to pixel**: the user supplies a description only.
2. Classify the content as character-primary or scene-primary. For scene-primary work, read and apply the scene style guide.
3. Determine the retro game direction. Honor a user-specified era or substyle; otherwise use the balanced 16-bit console look defined in the retro game style guide.
4. Determine the pixel-art detail level. Use the user-specified `16`, `32`, or `64`; default to `32`.
5. Read [references/effect-reference-guide.md](references/effect-reference-guide.md) and inspect the visual calibration image for the selected content type and detail level. Use it only to calibrate cluster scale, information density, and finish; use the retro game style guide to control the visual era and rendering language. For a multi-level comparison, inspect every requested calibration image before generating.
6. Determine the background behavior:
   - For image-to-pixel, preserve the original background and composition by default.
   - Use a pure white background only if requested.
   - Use transparency only if requested.
   - Replace the background only if the user asks for a new scene.
7. Compose a concise generation prompt from the user's content, retro game direction, applicable content guide, and calibrated effect level, then generate the image.
8. Verify that the result matches the corresponding calibration image in pixel-cluster scale, information density, and completion level while following the retro game style guide and preserving the user's own content. Do not accept a result that resembles a mechanical mosaic, a modern smooth illustration, or another preset.

## Image-to-pixel requirements

Preserve the original subject, proportions, framing, key details, spatial layout, and background unless the user explicitly requests a change. For character-primary work, deliberately reconstruct the silhouette, facial features, clothing panels, and modest stepped shading with purposeful sprite-like clusters. Retain selective dark or colored outlines and restrained discrete form modeling where it clarifies the source. For scene-primary work, preserve the spatial skeleton and landmarks, then simplify environmental information into modular game-readable forms according to the scene and retro game style guides. Do not over-render materials, add dense texture, change the source identity, or add unrelated content. Do not use a filter-like conversion or force a game camera that changes the source framing.

## Text-to-pixel requirements

Create a complete, readable retro game pixel illustration that directly represents the request. Use a simple composition and the balanced 16-bit console look by default. Add scene elements only when they support the requested content. Do not add a HUD, dialogue box, screen border, CRT effect, logo, or game text unless requested.

## Prompt construction

Include these elements when relevant:

`mode + subject + essential visual features + retro game direction + composition/background + detail preset + limited palette/discrete shading + exclusions`

Always state that pixels must be uniform square clusters with hard stepped edges, limited color ramps, and no anti-aliasing, blur, smooth gradients, random noise, modern digital-painting effects, unsolicited interface elements, watermarks, or unintended text.

## Grid selection

- **16**: early 8-bit impression; use the largest clusters, strongest silhouette, fewest internal divisions, and approximately 4–8 active colors for the dominant subject group.
- **32**: default balanced 16-bit console look; retain readable features and structural divisions with approximately 8–16 active colors and restrained stepped shading.
- **64**: late 16-bit or arcade illustration; preserve selected fine details with smaller clusters, approximately 16–32 active colors, and richer but still discrete color ramps.

For scene-primary work, use the scene-specific definitions in [references/scene-style-guide.md](references/scene-style-guide.md). Generate each requested preset as an independent redraw; never create `16` or `32` by shrinking a more detailed result.

Use the bundled calibration images only as effect-degree references. Do not copy their character identity, pose, costume, architecture, landscape, camera angle, palette, lighting, background, objects, or non-retro rendering qualities into a new request. The retro game style guide is authoritative for visual language.

Treat these as detail presets, not literal output-pixel or block dimensions. Keep the displayed subject size and requested aspect ratio unchanged.

## Output

Present the generated image without adding a post-generation explanation. If essential input is missing, ask one concise question before generating.
