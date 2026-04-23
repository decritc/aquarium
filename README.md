# Virtual Aquarium

This repository is the starting point for a browser-based virtual aquarium game.

The project is currently documentation-first. The immediate goal is to define the
game clearly enough that future agents can implement it in phases without needing
to rediscover core product decisions.

## Game premise

Players manage one or more aquariums populated with animated 3D fish.

The experience supports:

- **Breeder career mode** with limited starting capital, progression, and economy
- **Sandbox mode** for freeform tank design and fish experimentation
- **Observer mode** so visitors can view public aquariums created by other users
- **Freshwater and saltwater tanks**
- **Fish breeding and tank design**
- **Idle/simulation gameplay** with optional acceleration through monetization

The product direction is intentionally mode-dependent:

- **Sandbox mode** emphasizes creativity and low friction
- **Career mode** emphasizes breeding strategy and business management
- **Observer mode** emphasizes social discovery and public aquarium browsing

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
- `docs/landing-page-and-seo.md` - premium web landing page, discoverability, and SEO strategy
- `docs/browser-performance-and-rendering.md` - browser rendering quality and performance strategy
- `docs/tank-simulation-spec.md` - first-pass simulation rules, metrics, and placement-mode model
- `docs/ui-flows.md` - primary app navigation and player flow planning
- `docs/tank-editor-ux.md` - tank editor camera, placement, and inspection UX
- `docs/economy-and-progression.md` - money, premium currency, and progression model
- `docs/technical-foundation.md` - recommended implementation direction for agents
- `docs/asset-pipeline.md` - how 3D fish assets and metadata should be organized
- `docs/starter-freshwater-plan.md` - first roster, tank archetypes, compatibility, and unlock ladder
- `docs/starter-item-catalog.md` - starter decor, equipment, substrate, and backdrop catalog
- `docs/tank-presentation-and-environment.md` - side-view tank presentation and environment simulation rules
- `docs/founder-decisions.md` - accepted answers to the initial design questionnaire
- `docs/open-questions.md` - decisions still unresolved or intentionally deferred

## Next steps

1. Turn the current simulation and UI planning into an exact first playable milestone spec.
2. Define the premium web landing page and first marketing/presentation assets.
3. Validate starter content and rendering plans against browser performance targets.
4. Design the fish genetics system as a layered system that can grow over time.
5. Add early concept assets and example fish metadata JSON files.
