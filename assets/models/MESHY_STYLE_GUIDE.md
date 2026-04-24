## Meshy style guide

Use this guide for every starter asset so the project keeps one coherent look and
feel across fish, tanks, decor, plants, and equipment.

## Core visual direction

The project style is:

- cartoon realism
- bright but believable color
- soft premium shading
- readable silhouettes
- browser-friendly detail density

Target feel:

- premium life-sim aquarium
- stylized realism rather than hard realism
- friendly and approachable, not toy-like in a cheap way
- suitable for polished marketing shots and in-game side-view presentation

Avoid:

- hyper-photoreal realism
- muddy/desaturated palettes
- horror lighting
- gritty decay unless specifically requested
- exaggerated chibi proportions
- low-detail “mobile placeholder” look
- inconsistent texture treatment between assets

## Material and shading direction

- Prefer clean, simplified surface breakup over noisy micro-detail
- Use bright readable local colors with believable gradients
- Surfaces should respond well to soft aquarium lighting
- Keep contrast clear enough for side-view readability
- Use stylized but believable materials:
  - fish scales should read cleanly, not overly noisy
  - glass should be subtle and efficient
  - rocks and wood should have strong shape readability before texture detail

## Lighting assumptions for render previews

Assume the runtime and marketing look will favor:

- soft top lighting
- gentle front fill
- subtle underwater bounce
- bright, premium readable shading

Render previews should look good with:

- teal/aqua ambient fill
- mild caustic influence
- no harsh black shadows that kill detail

## Geometry and performance

- Prefer clean silhouettes over dense geometry
- Keep shapes readable at gameplay distance
- Avoid unnecessary tiny fins, leaves, ridges, or knobs that disappear in browser view
- Favor efficient meshes and material counts

## Animation style for fish

Fish animation should feel:

- smooth
- fluid
- alive
- readable in side view

Avoid:

- robotic body bends
- harsh pose snapping
- excessive tail whip that looks arcade-like
- drifting with no steering intent

General expectations:

- cruise motion should feel continuous and relaxed
- turns should arc smoothly
- feed motion should read clearly but stay elegant
- threat-display motion should be legible without becoming monstrous

## Export expectations

Where possible, assets should be generated or refined with the expectation that the
final deliverable will include:

- `model.glb`
- preview image
- clean forward orientation
- sensible scale
- origin and pivot appropriate to the asset type

### Pivot/origin guidance

- Fish: centered for animation/routing
- Floor decor: origin at the base
- Floating decor: center or balance point appropriate to waterline placement
- Tanks: origin at floor center
- Plants: origin at root/base
- Equipment: origin at mounting base or body center as appropriate

## Prompt-writing rule

Every asset-specific Meshy prompt should include:

1. what the asset is
2. what gameplay role it serves
3. what visual mood it should support
4. how realistic vs stylized it should be
5. any animation expectations
6. browser-performance awareness

