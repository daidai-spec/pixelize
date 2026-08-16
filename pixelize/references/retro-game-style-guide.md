# Retro Game Illustration Style Guide

## Contents

- [Purpose](#purpose)
- [Core visual language](#core-visual-language)
- [Detail presets and era strength](#detail-presets-and-era-strength)
- [Character-primary treatment](#character-primary-treatment)
- [Scene-primary treatment](#scene-primary-treatment)
- [Composition and camera](#composition-and-camera)
- [Exclusions](#exclusions)
- [Prompt guidance](#prompt-guidance)
- [Validation](#validation)

## Purpose

Render every result as a handcrafted retro game pixel illustration. Use the visual construction language of 8-bit and 16-bit console or arcade art while keeping the user's subject, composition, aspect ratio, and requested background. Treat the output as a display illustration, not a literal game-ready sprite sheet, tile map, or low-resolution asset.

Default to a balanced 16-bit console look. Use an earlier 8-bit or later 16-bit/arcade direction only when the selected detail preset or the user request calls for it. Evoke an era and production constraint; do not copy a specific game's characters, environments, interface, logo, or proprietary visual identity.

## Core visual language

- Construct silhouettes and internal forms from deliberate square pixel clusters with hard stepped edges.
- Use flat color regions, compact color ramps, and discrete light or shadow steps. Do not paint with smooth tonal modeling.
- Favor iconic, game-readable shapes over photographic accuracy and decorative abundance.
- Use selective dark outlines or colored boundary pixels to separate overlapping forms. Do not surround every internal detail with uniform black.
- Keep cluster scale consistent across the subject and environment. Do not mix coarse blocks with fine pseudo-pixel texture.
- Use sparse, patterned dithering only to bridge an important transition, suggest atmosphere, or evoke hardware-era color limits. Never use random noise.
- Use hue-shifted ramps when appropriate: warmer or brighter lights, cooler or more saturated shadows, and a restrained accent color around the focal point.
- Preserve clean negative space and strong value grouping so the image remains readable at thumbnail size.

## Detail presets and era strength

Keep `16`, `32`, and `64` as illustration detail presets rather than literal pixel dimensions.

### 16 — early 8-bit impression

- Use the largest clusters, strongest silhouette, fewest internal divisions, and highest value contrast.
- Keep approximately 4–8 active colors for the main subject or dominant scene group.
- Express faces, accessories, foliage, architecture, and props with emblematic marks rather than small descriptive texture.
- Limit form modeling to one main shadow step and occasional highlights.
- Avoid dense dithering, soft atmosphere, thin decorative lines, and modern lighting effects.

### 32 — balanced 16-bit console look

- Use a readable 16-bit console illustration language by default.
- Keep approximately 8–16 active colors for the main subject or dominant scene group.
- Preserve clear facial or landmark structure, costume or facade divisions, and two or three deliberate value steps.
- Allow restrained hue shifting, selective highlights, small material accents, and limited patterned dithering.
- Keep the result polished but visibly cluster-built rather than digitally painted.

### 64 — late 16-bit or arcade illustration

- Use smaller deliberate clusters and approximately 16–32 active colors while maintaining clear pixel organization.
- Preserve selected material, costume, facial, atmospheric, or environmental detail without reproducing photographic noise.
- Allow richer color ramps, rim highlights, weather accents, and selective dithering, but keep every effect subordinate to silhouette and gameplay-like readability.
- Do not drift into modern high-resolution pixel painting, vector-clean line art, 3D rendering, or smooth anime illustration.

## Character-primary treatment

- Build an iconic sprite-like silhouette even when the output is a large portrait or full-body illustration.
- Preserve identity through head shape, hairstyle, facial mark placement, posture, costume blocks, and signature accessories.
- Simplify anatomy into readable planes and joints rather than soft realistic modeling.
- Use compact facial marks at `16`, clearer eyes and expression at `32`, and selected costume or material accents at `64`.
- Do not add idle-animation frames, sprite sheets, inventory frames, character-select UI, health bars, or dialogue boxes unless requested.

## Scene-primary treatment

- Preserve the scene hierarchy defined in `scene-style-guide.md`, then express it with modular, game-readable shapes.
- Suggest tile-aware rhythms in roads, walls, roofs, foliage, water, and interiors without forcing a visible grid or repeating one tile mechanically.
- Separate foreground, middle ground, and background with clear value groups and limited palette shifts. Use parallax-like layering when it fits the original composition.
- Simplify crowds, merchandise, windows, leaves, masonry, and props into repeated cluster motifs rather than unique micro-details.
- Do not add a HUD, minimap, score, dialogue box, controller prompt, fake game title, CRT frame, scanlines, screen curvature, or readable invented text unless requested.

## Composition and camera

For image conversion, preserve the source framing and camera. Do not force a side view, top-down view, or isometric view merely to make the result look game-like.

For text generation, choose the view that best supports the request:

- side view for platforming, action, or cinematic travel
- top-down or three-quarter view for RPG exploration, interiors, and town scenes
- isometric view for architecture, rooms, and spatial systems
- portrait or full-body framing for character illustrations

When the user does not specify a view, choose a simple composition with one clear focal subject and no interface overlay.

## Exclusions

Exclude these unless the user explicitly asks for them:

- smooth gradients, anti-aliasing, soft brushwork, photographic textures, and vector-perfect curves
- bloom, depth of field, lens flare, volumetric haze, soft glow, and modern cinematic color grading
- random noise, uniform checkerboard dithering, excessive black outlines, and mixed pixel scales
- CRT scanlines, chromatic aberration, screen curvature, phosphor masks, and emulator filters
- HUD elements, life bars, menus, dialogue windows, fake logos, watermarks, and unintended text
- direct imitation of a named game's proprietary characters, world, interface, or exact asset language

## Prompt guidance

Include the following constraints in the generated prompt when relevant:

`retro game pixel illustration + selected era strength + uniform square clusters + limited palette + discrete color ramps + hard stepped edges + content-specific preservation + no modern digital-painting effects`

Treat user-specified era, platform category, view, palette, or mood as an override. When none is supplied, use the balanced 16-bit console look.

## Validation

Reject and regenerate when the result:

- resembles a mosaic filter rather than deliberately drawn game art
- looks like a smooth modern illustration with pixel texture placed on top
- contains mixed pixel scales, blurry edges, gradients, or random speckle
- adds an unsolicited HUD, border, CRT effect, game logo, or invented writing
- copies recognizable content from a specific existing game
- loses the user's character identity, spatial layout, focal landmark, or background contract
- fails to show a clear detail difference between `16`, `32`, and `64`
