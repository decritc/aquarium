# Basic Tropical Heater - Meshy Prompt

## Asset purpose
- Visible starter heater for freshwater tropical tanks
- Must read clearly in side view without dominating the composition
- Used in betta display, community, and breeder setups

## Style direction
- Match `/workspace/assets/models/MESHY_STYLE_GUIDE.md`
- Cartoon realism: clean shapes, soft edges, premium materials, readable silhouette
- Slightly stylized safety casing so it feels like a life-sim object, not industrial lab equipment

## Meshy generation prompt
Create a stylized-but-realistic small aquarium heater designed for a cozy premium browser aquarium game. The heater should feel believable and functional, but simplified for readability in a side-view aquarium. Use cartoon realism with smooth forms, gentle bevels, crisp silhouette, subtle material definition, and polished shading. The object should be slim, vertical, and designed to mount near the rear glass. Include a dark heater body, a small indicator light region, and a simple protective cap or suction-mount system. Avoid excessive wires, logos, labels, tiny numbers, or high-frequency detail. This asset must look attractive at medium gameplay distance in a side-view tank.

## Negative prompt guidance
- no photoreal grime
- no industrial sci-fi shapes
- no tiny illegible decals
- no giant thick power cable dominating the silhouette
- no broken or rusty surfaces
- no exaggerated toy proportions

## Rendering / output requirements
- Export as optimized `model.glb`
- Origin near mounting center or lower body for easy placement
- Vertical orientation
- Keep material count low
- Preserve a clean silhouette against glass/backdrop layers

## Animation requirements
- No skeletal animation required
- Static model only

## Metadata targets after generation
- category: equipment
- placementBehavior: mounted
- surface: equipment-slot
- allowedTankEnvironments:
  - freshwater-tropical
  - freshwater-planted
  - brackish

## Notes for consistency
- Should visually pair with sponge filter and power filter without looking like a different game
- Should feel premium, friendly, and readable in the same scene as driftwood, plants, and fish
