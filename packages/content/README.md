# Content Package Placeholder

This package will eventually contain structured game data such as:

- fish species definitions
- rarity tiers
- genetics traits
- decoration items
- tank equipment
- shop inventories
- economy balance tables
- progression unlock tracks

## Planned content contract layout

```text
packages/content/
  fish-species/
    freshwater/
      betta.json
      guppy.json
    saltwater/
      clownfish.json
  tank-items/
    decor/
      river-rocks.json
    equipment/
      sponge-filter-basic.json
    plants/
      java-fern.json
  progression/
    career/
      starter-unlocks.json
```

The content package should distinguish between:

- **asset metadata**: how a model or texture is loaded
- **species definitions**: how a fish behaves and what it needs
- **tank item definitions**: what decor or equipment does in the simulation
- **progression definitions**: how content is unlocked in different modes

In a future implementation phase, the package should export typed content that can
be shared by the web client, simulation logic, admin tooling, and backend
services.
