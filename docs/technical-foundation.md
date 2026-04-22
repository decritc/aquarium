# Technical Foundation

This document proposes a practical starting architecture for implementing the
virtual aquarium game in phases.

## Goals

- Support a browser-based aquarium simulation
- Render animated 3D fish and tank decorations
- Persist user aquariums, progression, and breeding outcomes
- Allow public viewing of selected aquariums
- Keep content definitions data-driven so new fish can be added without major
  code changes

## Recommended implementation approach

Use a monorepo with a clear split between:

- **apps/web**: browser game client
- **apps/server**: API and account services
- **packages/simulation**: deterministic simulation rules and breeding systems
- **packages/content**: fish, decorations, tank rules, and balancing data
- **packages/shared**: shared types and validation

## Suggested stack

This is a recommendation, not a final decision.

### Client

- TypeScript
- React for UI
- React Three Fiber or Babylon.js for 3D aquarium rendering
- Zustand or Redux Toolkit for client state
- Tailwind CSS or a similar pragmatic UI styling solution

### Server

- Node.js with TypeScript
- A framework such as Next.js API routes, NestJS, or Fastify
- PostgreSQL for accounts, ownership, economy state, breeding history, and tank
  configuration
- Redis for caching and event queues if real-time/public aquarium traffic grows

### Content and validation

- JSON or JSONC content files for fish and item definitions
- JSON Schema and/or Zod validation for asset metadata and content ingestion

## Implementation phases

### Phase 1: Documentation and content contracts

- Finalize the design docs
- Establish file conventions for fish assets and metadata
- Define shared data schemas

### Phase 2: Smallest playable sandbox

- Single local aquarium
- Place fish into a tank
- Render fish swimming on simple loops
- Basic environment controls

### Phase 3: Account-backed breeder mode

- User accounts
- Persistent tanks
- Basic currency and shop
- Fish purchasing and resale

### Phase 4: Breeding and genetics

- Breeding rules
- Egg or fry lifecycle
- Trait inheritance and rarity

### Phase 5: Observer mode and social features

- Public aquarium profiles
- Shareable links
- Featured aquariums and discovery

### Phase 6: Monetization and live ops

- Ads
- Premium currency
- Quality-of-life purchases
- Events and seasonal content

## Architecture principles

1. **Data-driven content first**
   Fish species, tank requirements, breeding rules, and shop items should live
   in content definitions instead of hard-coded logic.

2. **Deterministic simulation core**
   The simulation package should be testable without the renderer. Rendering
   should visualize simulation state, not define it.

3. **Client prediction where safe**
   Non-economy actions may feel immediate on the client, but authoritative
   economy and breeding outcomes should be server-backed once multiplayer/public
   persistence exists.

4. **Graceful idle progression**
   Offline progress should be computed from timestamps and bounded formulas,
   rather than requiring the simulation to run continuously on the server.

## Data domains

- Accounts and authentication
- User profiles and public visibility settings
- Aquariums and tank layouts
- Fish instances and genealogy
- Species definitions and compatibility
- Decorations, filters, substrates, and plants/coral
- Currencies, purchases, ads, and entitlements

## Risks to manage early

- Rendering too many fish in public aquariums on low-end devices
- Simulation complexity growing faster than content authoring discipline
- Monetization pressure harming the relaxing tone of the game
- Asset format drift between 3D models and expected metadata

## Recommendation for the first implementation milestone

The first milestone should likely be a local sandbox aquarium with:

- one tank
- three fish species
- one environment type
- simple feeding and happiness stats
- no accounts yet

That creates a playable visual target without overcommitting to backend systems.
