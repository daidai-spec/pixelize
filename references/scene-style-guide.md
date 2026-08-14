# Scene Pixel Style Guide

## Purpose

Use this guide when the place, environment, architecture, landscape, interior, or spatial route is the primary subject. Keep the general pixel language, palette ranges, background behavior, and output rules from `pixel-style-guide.md`. Change only how scene information is selected and organized.

## Preserve scene identity

Preserve these properties across all detail presets:

- aspect ratio, framing, camera angle, perspective, and vanishing direction
- horizon, skyline, terrain, paths, roads, rivers, and major depth layers
- position and proportion of dominant buildings, trees, landscape masses, or interiors
- focal landmark, main activity, and principal color relationships

Adapt palette, lighting, weather, architecture, materials, and atmosphere to the source or user request. Do not impose one universal scene mood or regional style.

When producing `16`, `32`, and `64` for comparison, redraw the same scene independently. Keep its composition and identity stable while changing the amount of retained information.

## Organize information by priority

Preserve scene information in this order:

1. **Spatial skeleton**: horizon, route, terrain, large masses, depth layers, and focal placement.
2. **Recognition landmarks**: distinctive buildings, large trees, bridges, vehicles, dominant furniture, or major signs.
3. **Narrative objects**: doors, window groups, stalls, shelves, people groups, plants, pipes, tables, or working equipment.
4. **Surface detail**: individual bricks, tiles, leaves, products, cracks, reflections, readable text, and decorative marks.

Use four operations deliberately:

- **Preserve** a shape when it defines space, recognition, or focus.
- **Merge** repeated objects into one readable cluster.
- **Symbolize** small objects or signs with intentional pixel marks.
- **Remove** detail that does not support scene identity.

Do not invent readable words. If source text cannot be represented reliably, preserve the sign's placement, size, color role, and rhythm using abstract pixel marks.

## Scene detail presets

### 16 — spatial summary

- Preserve the spatial skeleton, major light and dark masses, broad foreground/middle-ground/background separation, and only the strongest landmarks.
- Use a moderately coarse cluster scale. Apply another `10%` refinement from the previous calibration: compared with the initial scene calibration, make the dominant pixel clusters about `19%` smaller overall so the image feels less blocky without approaching `32`.
- Keep the semantic information budget at the original `16` level. Use the finer cluster scale only to improve stepped edges and the readability of existing masses; do not add more objects, landmarks, decorative layers, or narrative information.
- Build architecture, trees, ground, and sky from coherent clusters. Allow a few more grid steps inside an already-preserved major building, tree, route, or focal landmark, but do not create new subdivisions that behave like additional scene content.
- Merge repeated windows, merchandise, foliage, roof patterns, paving, flowers, and small props.
- Remove individual bricks, leaves, products, cracks, wires, tiny signs, and surface texture.
- The result should read immediately at thumbnail size and look intentionally simplified, but not like an extreme low-resolution mosaic.

### 32 — structural scene

- Preserve the complete spatial skeleton and recognizable landmark structure.
- Apply another `10%` reduction from the previous calibration. Target about `63%` of the information density allowed by the initial scene calibration; remove or merge the lowest-priority `37%` of narrative and surface information.
- Refine the pixel granularity by about `10%` from the previous calibration while keeping the `63%` semantic information budget unchanged. Use the smaller clusters only to improve stepped contours, perspective edges, and the internal readability of already-preserved structures; do not restore removed objects or surface detail.
- Separate only the major facade sections, roof planes, doors, main window groups, paths, vegetation masses, and a small set of important props.
- Retain narrative objects only when they explain the place, activity, or focal point. Merge secondary furniture, merchandise, flowers, roof tiles, masonry, and paving into larger symbolic clusters.
- Use very limited symbolic material texture. Do not describe repeated detail object by object.
- The result should feel clearly more developed than `16`, but visibly simplified rather than polished or richly rendered.

### 64 — descriptive environment

- Preserve spatial, landmark, and primary narrative information with smaller deliberate clusters.
- Target about `80%` of the information density allowed by the initial scene calibration; merge or remove the smallest `20%` of secondary and surface information.
- Describe selected secondary structures, furniture groups, product groups, major branches, foliage groups, roof rhythms, masonry joints, reflections, or weather effects, but never all of them at once.
- Keep fine details subordinate to the focal hierarchy.
- The result should remain the most descriptive preset while still looking visibly reduced and pixel-organized.
- Do not reproduce photographic noise, every leaf, every brick, every product, every flower, or every highlight.

## Validation

Reject a scene result when:

- `16`, `32`, and `64` differ mainly in sharpness or pixel size rather than retained information
- the spatial layout, viewpoint, focal landmark, or scene identity changes between presets
- small texture competes with large spatial masses
- the result resembles a mosaic filter or mixes pixel-cluster scales
- generated lettering appears where abstract sign marks were required
