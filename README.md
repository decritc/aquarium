# Virtual Aquarium

This repository is the starting point for a browser-based virtual aquarium game.

The project is currently documentation-first. The immediate goal is to define the
game clearly enough that future agents can implement it in phases without needing
to rediscover core product decisions.

## Game premise

Players manage one or more aquariums populated with animated 3D fish.

The experience supports:

- **Breeder career mode** with a starting bankroll, progression, and economy
- **Sandbox mode** for freeform tank design and fish experimentation
- **Observer mode** so visitors can view public aquariums created by other users
- **Freshwater and saltwater tanks**
- **Fish breeding and tank design**
- **Idle/simulation gameplay** with optional acceleration through monetization

## Repository layout

- `docs/` - living game design and technical planning documents
- `schemas/` - JSON schemas for assets and data definitions
- `assets/models/fish/` - placeholder structure for fish models and metadata
- `apps/web/` - planned browser client
- `apps/server/` - planned API and account backend
- `packages/simulation/` - planned simulation logic package
- `packages/content/` - planned content definitions for fish, tanks, items, and balancing data
- `packages/shared/` - planned shared types, schemas, and validators

## Key documents

- `docs/game-design-document.md` - core product and system design
- `docs/economy-and-progression.md` - money, premium currency, and progression model
- `docs/technical-foundation.md` - recommended implementation direction for agents
- `docs/asset-pipeline.md` - how 3D fish assets and metadata should be organized
- `docs/open-questions.md` - decisions to make together before implementation

## Next steps

1. Refine the core game loop and player fantasy.
2. Define the fish genetics and breeding depth.
3. Confirm the technical stack for the browser client and backend.
4. Add early concept assets and example fish metadata JSON files.
5. Decide what the smallest playable milestone should be.
