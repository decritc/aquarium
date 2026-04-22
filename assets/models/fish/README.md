## Fish model assets

This folder will store 3D fish models and their metadata.

Recommended layout:

- `freshwater/<species-id>/model.glb`
- `freshwater/<species-id>/metadata.json`
- `saltwater/<species-id>/model.glb`
- `saltwater/<species-id>/metadata.json`

Each `metadata.json` file should validate against `schemas/fish-model.schema.json`.

Current example:

- `freshwater/example-guppy/metadata.json`

Example species folders are included to demonstrate naming and structure.
