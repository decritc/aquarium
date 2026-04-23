## Asset Pipeline

This project expects animated 3D fish models authored outside the repository and
imported here with accompanying metadata JSON files.

## Goals

- Keep art assets organized by species and variant
- Make each model self-describing through metadata
- Allow agents to build loading pipelines without reverse-engineering files
- Support both prototype placeholders and production-quality models

## Directory structure

```text
assets/
  models/
    MESHY_STYLE_GUIDE.md
    fish/
      freshwater/
        guppy/
          MESHY_PROMPT.md
          model.glb
          metadata.json
      saltwater/
        clownfish/
          MESHY_PROMPT.md
          model.glb
          metadata.json
```

## Recommended file conventions

- One folder per species or display variant
- `model.glb` for the primary runtime model
- `metadata.json` for gameplay and rendering metadata
- `MESHY_PROMPT.md` for asset-generation instructions where AI-assisted generation is
  being used
- Additional textures or source files can live alongside runtime assets if needed
- The intended artist workflow is "drop in a GLB plus metadata JSON" so new fish
  can be added after release with minimal code changes

## Meshy prompt workflow

If Meshy AI or a similar generation tool is used, each starter asset folder should
also include a generation brief.

Recommended structure:

- `MESHY_STYLE_GUIDE.md` at `assets/models/` for the shared visual direction
- `MESHY_PROMPT.md` inside each asset folder for asset-specific instructions

The goal is to keep generated assets consistent across:

- silhouette style
- color intensity
- material treatment
- shading behavior
- animation expectations
- browser-performance constraints

Prompt briefs should describe:

- the role of the asset in gameplay
- the intended look and feel
- size and silhouette expectations
- any required animation clips
- rendering or material expectations
- what to avoid so the asset stays within the shared style

## Metadata responsibilities

Each fish metadata file should describe render and model-loading concerns only:

- Species definition linkage and display label
- Asset references for the client to load meshes, animations, and thumbnails
- Variant-level rendering hints such as preferred swim zone or silhouette tags
- Optional clip purposes such as cruise, turn, threat display, or feed

Authoritative gameplay data such as compatibility, aggression, tank rules, and
economy values should live in species content files under `packages/content/`
rather than being duplicated into render-asset metadata.

## Validation

Use `schemas/fish-model.schema.json` to validate fish metadata files.

Gameplay content contracts live alongside it:

- `schemas/fish-species.schema.json`
- `schemas/tank-item.schema.json`
- `schemas/progression-unlock.schema.json`

## Authoring guidance

- Keep IDs stable after publishing content
- Use lowercase kebab-case IDs
- Prefer explicit units for measurements
- Keep descriptive text player-facing and concise
- Avoid baking game balance values into filenames
- Assume Meshy AI or similar tools may be used during model generation, so runtime
  validation should focus on predictable export contracts instead of tool-specific
  assumptions
- Keep all generated assets aligned to the shared "cartoon realism" style guide so
  tanks do not feel like a mixture of unrelated render styles

## Future expansion

Later we may add:

- Decoration and tank environment asset metadata schemas
- Animation event naming conventions
- LOD guidance for browser performance
- Thumbnail generation rules
- Import validation scripts
