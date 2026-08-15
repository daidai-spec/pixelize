# Effect Reference Guide

## Purpose

Use the bundled images as the accepted visual calibration for the apparent effect strength of each content type and detail preset. Calibrate pixel-cluster scale, retained information, simplification, and completion level from them. Do not treat them as subject, composition, palette, or style-copying references.

## Reference map

### Character-primary

- `16`: `assets/effect-references/character-16.png`
- `32`: `assets/effect-references/character-32.png`
- `64`: `assets/effect-references/character-64.png`

### Scene-primary

- `16`: `assets/effect-references/scene-16.png`
- `32`: `assets/effect-references/scene-32.png`
- `64`: `assets/effect-references/scene-64.png`

Resolve these paths from the skill root. Inspect the relevant file with an image-viewing tool before constructing the generation prompt. When the user requests multiple presets for comparison, inspect every requested reference and generate each result independently.

## Calibrate from the images

Match these properties:

- apparent square pixel-cluster size relative to the subject or canvas
- overall information density and number of retained subdivisions
- balance between major silhouettes, structural divisions, and small details
- degree of stepped shading and clustered highlights
- overall finish level and the visible distance between `16`, `32`, and `64`

Translate the visual calibration into verbal prompt constraints. Do not attach a calibration image to the generation request by default when doing so could leak its subject or composition into the output.

## Do not copy

Do not copy or infer any of these properties from the calibration images:

- character identity, anatomy, pose, hairstyle, costume, accessories, or background
- architecture, region, landscape, props, people, camera angle, or spatial layout
- palette, lighting, weather, atmosphere, or material treatment
- labels, symbols, logos, or text

The user's source image or description controls content and composition. The style guides control the pixel-art construction rules. The bundled images control only the accepted effect degree.

## Validate

Compare the result with the relevant calibration image at similar displayed size. Reject and regenerate when the result:

- is visibly closer to another preset's cluster scale or information density
- preserves too much or too little information for the requested level
- copies recognizable content from a calibration image
- changes the user's subject or scene merely to resemble the calibration example
