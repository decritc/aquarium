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

## Metadata responsibilities

Each fish metadata file should describe:

- Species and display name
- Water type compatibility
- Rarity and acquisition source
- Breeding tags and trait hooks
- Basic simulation hints such as size, swim zone, and schooling behavior
- Asset references for the client to load animations and thumbnails

## Validation

Use `schemas/fish-model.schema.json` to validate fish metadata files.

## Authoring guidance

- Keep IDs stable after publishing content
- Use lowercase kebab-case IDs
- Prefer explicit units for measurements
- Keep descriptive text player-facing and concise
- Avoid baking game balance values into filenames

## Future expansion

Later we may add:

- Decoration and tank environment asset metadata schemas
- Animation event naming conventions
- LOD guidance for browser performance
- Thumbnail generation rules
- Import validation scripts
