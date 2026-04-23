# Content Contracts

This document defines the core data contracts that future implementation agents
should use when building content pipelines, simulation logic, and admin tooling.

The system is intentionally split into multiple layers:

- **Fish model metadata** describes rendering assets and animation files
- **Fish species data** describes simulation, compatibility, and breeding rules
- **Tank item data** describes decor, equipment, plants, and structural items
- **Progression unlock data** describes how content becomes available by mode

This separation keeps the project data-driven while allowing the art pipeline to
stay simple: drop in a GLB and JSON files without hard-coding species behavior.

## 1. Fish model metadata

Schema:

- `schemas/fish-model.schema.json`

Purpose:

- identify a runtime model
- reference GLB scene files and previews
- describe animation clips and optional animation tags
- provide simple physical/rendering hints

What belongs here:

- model filenames
- animation clip names
- render scale hints
- swim-zone defaults used by animation/renderer systems

What does not belong here:

- species compatibility rules
- breeding logic
- economy balance
- tank-type restrictions beyond broad environment tagging

## 2. Fish species content

Schema:

- `schemas/fish-species.schema.json`

Purpose:

- define the gameplay and simulation identity of a fish species
- express habitat rules such as freshwater, saltwater, tropical, temperate, or reef
- express social and aggression behavior
- drive breeding, market value, unlocks, and care difficulty

Key design intent:

- fish should behave like their real-world counterparts where it improves the
  simulation
- tank compatibility should not be reduced to a single "can share tank" flag
- species should be authorable after release by adding metadata instead of code

### Habitat model

Species data should define:

- water type
- climate band
- habitat tags
- recommended tankmates
- incompatible tankmate tags/species

Examples:

- tropical freshwater fish should be grouped with other tropical freshwater fish
- reef species may require a saltwater reef-compatible setup
- brackish species may need a narrower allowed range

### Behavior and aggression

Species data should express:

- default temperament
- aggression triggers
- territorial behavior
- schooling or solitude needs
- fin-nipping, chasing, or stress-causing tendencies

Example:

- a betta can be marked as territorial and aggressive toward specific silhouettes,
  fin types, or species tags
- if placed with incompatible fish, simulation should show credible behavior such
  as chasing, stress, or conflict penalties rather than silently ignoring the mismatch

This does **not** require complex predator AI in the first milestone. Early
versions can represent these dynamics through:

- compatibility warnings before placement
- stress/health modifiers
- chase animations or behavior-state swaps
- reduced breeding success or lowered tank rating

## 3. Tank item content

Schema:

- `schemas/tank-item.schema.json`

Purpose:

- define aquarium decor, structural items, equipment, substrate, plant life, and
  theme items
- provide placement and compatibility rules
- express whether an item affects simulation, cosmetics, or both

Examples:

- filters and heaters affect tank conditions
- caves and plants increase shelter value
- coral and reef structures affect habitat suitability for saltwater species
- themed decorations primarily affect aesthetics and tank rating

## 4. Progression unlock content

Schema:

- `schemas/progression-unlock.schema.json`

Purpose:

- define how fish, items, tanks, or systems unlock in sandbox, career, or social
  contexts
- keep progression logic declarative and mode-aware

Examples:

- guest sandbox gets one tank and a curated starter content set
- career mode unlocks saltwater systems after progression milestones
- observer/social tools unlock when a player creates an account

## Recommended repository layout

Suggested future content layout:

```text
packages/content/
  fish/
    species/
      freshwater/
        betta.json
        guppy.json
      saltwater/
        clownfish.json
  tank-items/
    decor/
    equipment/
    plants/
    substrate/
  progression/
    sandbox/
    career/
    social/
```

## Cross-schema responsibilities

### Fish model metadata should answer:

- What files should the renderer load?
- Which animation clips exist?
- How should the fish be rendered or previewed?

### Fish species data should answer:

- What kind of tank does this fish belong in?
- What water/climate/habitat tags does it require?
- How does it behave with other fish?
- What breeding and economy rules apply?

### Tank item data should answer:

- What can the player place?
- Where can it be placed?
- Does it affect care, shelter, compatibility, or aesthetics?

### Progression data should answer:

- When does content become available?
- In which game mode is it available?
- What unlock path or entitlement exposes it?

## Authoring rule of thumb

If the information is primarily about **how the fish looks or animates**, it
belongs in fish model metadata.

If the information is primarily about **how the fish behaves, breeds, survives,
or interacts with the tank**, it belongs in fish species data.
