# Technical Foundation

This document proposes a practical starting architecture for implementing the
virtual aquarium game in phases.

## Confirmed direction

The current product direction is:

- Desktop web first
- TypeScript monorepo for shared product logic
- React-based browser client
- GLB as the primary runtime fish asset format
- Offline progression as bounded catch-up instead of exact always-on simulation
- A mode-driven product structure where sandbox, career, and observer flows have
  materially different goals and constraints
- Professional-quality landing page and SEO are first-class product requirements
- Browser performance and animation smoothness are first-class technical requirements

The founder also noted that the backend may eventually require performance-
critical services beyond TypeScript and that frontend rendering or simulation may
benefit from WebAssembly in later phases.

## Goals

- Support a browser-based aquarium simulation
- Render animated 3D fish and tank decorations
- Persist user aquariums, progression, and breeding outcomes
- Allow public viewing of selected aquariums
- Keep content definitions data-driven so new fish can be added without major
  code changes
- Deliver a premium-quality marketing/landing page that can convert new visitors
- Keep fish motion and interaction smooth in a web browser rather than accepting
  choppy "web demo" quality

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
- A fixed side-view 2.5D tank renderer with layered depth rather than a free-camera
  aquarium explorer for the first implementation
- Consider WebAssembly selectively for heavy simulation, genetics, or crowd-style
  fish motion only after profiling shows a clear bottleneck

### Server

- Node.js with TypeScript for the first implementation
- A framework such as Next.js API routes, NestJS, or Fastify
- PostgreSQL for accounts, ownership, economy state, breeding history, and tank
  configuration
- Redis for caching and event queues if real-time/public aquarium traffic grows
- Keep performance-sensitive systems isolated behind service boundaries so they
  can later be moved to Rust, Go, or another faster runtime if scaling requires
  it

### Content and validation

- JSON or JSONC content files for fish and item definitions
- JSON Schema and/or Zod validation for asset metadata and content ingestion

## Implementation phases

### Phase 1: Documentation and content contracts

- Finalize the design docs
- Establish file conventions for fish assets and metadata
- Define shared data schemas

### Phase 2: Smallest playable sandbox

- Guest-accessible local or lightly persisted sandbox
- Single aquarium with a curated subset of fish and decorations
- Render fish swimming on simple loops in a fixed side-view tank
- Basic environment controls, backdrop selection, and substrate choice
- Free-rotation edit mode with quick top/side/front snaps for placement review
- Authored decor placement rules for heavy, floating, rooted, and mounted items
- Visible algae/cleanliness state
- Upgrade prompts for expanded asset access and additional tanks

### Phase 3: Account-backed breeder mode

- User accounts
- Persistent tanks
- Basic currency and shop
- Fish purchasing and resale
- Multiple-tank strategy under constrained starting capital

### Phase 4: Breeding and genetics

- Breeding rules
- Egg or fry lifecycle
- Trait inheritance and rarity

### Phase 5: Observer mode and social features

- Public aquarium profiles
- Shareable links
- Likes, follows, comments, and discovery surfaces
- Search across owner, tags, species, and popularity

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

3. **Cozy life-sim UI presentation**
   The interface should lean playful, rounded, and inviting rather than
   mechanical or enterprise-like. Think comforting life-sim readability over
   dense control panels, especially in sandbox and observer flows.

4. **Readable 2.5D presentation**
   The renderer should prioritize a calm, single side-view framing with layered
   depth, allowing 3D fish and decor to feel dimensional without requiring a
   free-look camera during normal viewing.

5. **Editing camera is not the presentation camera**
   The placement/editing experience should support free orbit plus quick angle
   snaps so players can judge decor scale, terrain shape, and front/back depth
   before returning to the primary side-view aquarium presentation.

6. **Client prediction where safe**
   Non-economy actions may feel immediate on the client, but authoritative
   economy and breeding outcomes should be server-backed once multiplayer/public
   persistence exists.

7. **Graceful idle progression**
   Offline progress should be computed from timestamps and bounded formulas,
   rather than requiring the simulation to run continuously on the server.

8. **Mode-specific rules over one-size-fits-all design**
   Sandbox, career, and observer mode should share rendering and content systems
   where possible, but they should be allowed to differ in economy rules,
   progression, public visibility, and difficulty tuning.

9. **Selectable director profiles**
   The simulation should allow an AI-director-style layer to adjust pressure,
   recovery opportunities, and challenge intensity, but players should be able
   to choose the general tone of that director from more relaxed/zen profiles to
   more demanding profiles.

10. **Observer-safe presentation**
   Observer mode should render tanks as clean viewing experiences. Owner-only
   gauges, diagnostics, and management overlays such as pH or temperature tools
   should remain hidden from public viewing unless a future explicit creator mode
   allows them to be shown.

11. **Landing page quality is product quality**
   The marketing and landing experience should be treated as part of the game's
   core product quality. It should look like a premium, professionally art-
   directed game site rather than a generic template or AI-generated page.

12. **Performance is a feature, not a post-pass**
   Smooth fish motion, responsive controls, and stable frame pacing must be part
   of the initial implementation strategy. The browser target is a constraint to
   engineer around, not an excuse for low-quality animation or rendering.

## Data domains

- Accounts and authentication
- User profiles and public visibility settings
- Aquariums and tank layouts
- Tank backdrop selections and optional user-uploaded backgrounds
- Fish instances and genealogy
- Species definitions and compatibility
- Decorations, filters, substrates, and plants/coral
- Currencies, purchases, ads, and entitlements

## Risks to manage early

- Rendering too many fish in public aquariums on low-end devices
- Simulation complexity growing faster than content authoring discipline
- Monetization pressure harming the relaxing tone of the game
- Asset format drift between GLB models and expected metadata
- AI-director tuning becoming opaque or unfair if not made legible
- Prematurely overengineering high-performance backend paths before real scale
  data exists
- Shipping a weak landing page that makes the game look low-budget despite strong
  underlying design
- Accepting browser frame pacing, stutter, or fish motion jitter that damages the
  premium feel of the aquarium

## Recommendation for the first implementation milestone

The first milestone should likely be a local desktop-web sandbox aquarium with:

- one guest sandbox tank
- a curated subset of fish and decorations
- freshwater only
- fixed side-view presentation with depth-layered fish and decor
- simple feeding and happiness stats
- substrate and built-in backdrop selection
- visible algae/cleanliness state
- optional upsell hooks for account upgrade and expanded content

That creates a playable visual target without overcommitting to backend systems.
