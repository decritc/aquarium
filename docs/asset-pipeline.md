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
    fish/
      freshwater/
        guppy/
          README.md
          model.glb
          metadata.json
      saltwater/
        clownfish/
          README.md
          model.glb
          metadata.json
```

## Recommended file conventions

- One folder per species or display variant
- `model.glb` for the primary runtime model
- `metadata.json` for gameplay and rendering metadata
- Additional textures or source files can live alongside runtime assets if needed
- The intended artist workflow is "drop in a GLB plus metadata JSON" so new fish
  can be added after release with minimal code changes

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

## Future expansion

Later we may add:

- Decoration and tank environment asset metadata schemas
- Animation event naming conventions
- LOD guidance for browser performance
- Thumbnail generation rules
- Import validation scripts
