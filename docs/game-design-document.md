# Virtual Aquarium Game Design Document

## Document purpose

This document defines the product vision and first-pass design for a browser-based
virtual aquarium game. It is intended to guide future implementation agents so
they can build the game in phases with a shared understanding of the experience.

This is a living document. Confirmed founder decisions are tracked in
`docs/founder-decisions.md`, while remaining unknowns should be tracked in
`docs/open-questions.md`.

## Vision

Create a mode-driven aquarium platform where players can either design, breed, or
observe animated 3D fish aquariums in the browser, with each mode emphasizing a
different player fantasy.

The game should support three complementary player fantasies, selected primarily
through game mode:

1. **Aquarium artist** - design visually impressive tanks in sandbox mode
2. **Fish breeder** - build a profitable operation through genetics and progression in career mode
3. **Observer/visitor** - explore and admire aquariums built by others in observer mode

## Mode-driven product strategy

The primary fantasy depends on the user's selected mode rather than a single
global product identity.

- **Sandbox mode** prioritizes creativity, low friction, and presentation.
- **Career mode** prioritizes breeding strategy, economy, and long-term planning.
- **Observer mode** prioritizes social discovery and ambient viewing.

This principle should guide UX, monetization, progression rules, and difficulty.

## Experience pillars

### 1. Living aquariums

Tanks should feel active and soothing even when the player is not making direct
inputs. Fish movement, schooling, idling, feeding, and tank ambience should make
the aquarium enjoyable to watch.

### Presentation target

The game should present tanks primarily from a fixed side-view camera. Fish and
decor should still be 3D and depth-aware, but the viewing experience should feel
like a polished aquarium diorama rather than a free-roam camera simulation.

### 2. Meaningful progression

Career mode should reward long-term planning. Players start with constrained
capital, gradually earn more money, unlock better fish and equipment, and improve
their breeding program.

### 3. Creative expression

Players should be able to create tanks with different themes, decorations, layouts,
and species mixes within tank rules and habitat compatibility constraints.

### 4. Social visibility

Public aquariums should be easy to browse. Observer mode should make it rewarding
to visit tanks created by other players through viewing, likes, follows, comments,
and curated discovery.

### 5. Low-pressure simulation

The game should feel idle-friendly and accessible. It should encourage planning and
experimentation more than punishing micromanagement.

## Core game modes

## 1. Breeder career mode

Career mode is the main progression and economy mode.

Player starts with:

- A small bankroll
- A starter tank or enough capital to choose how to allocate early spending
- A limited catalog of fish and decorations
- Basic water-quality and habitat tools

Player goals:

- Buy fish and equipment
- Create tanks that meet species needs
- Breed fish with desirable traits
- Sell fish for profit
- Expand into additional tanks when financially viable
- Unlock new species, decorations, and systems

Core pressure:

- Limited starting funds across tank purchases, livestock, and decor choices
- Habitat constraints
- Breeding cooldowns and maturity time
- Gradual unlocking of premium fish and larger tank options

Career play should allow multiple viable strategies:

- conservative single-tank design-first play
- aggressive breeder-first multi-tank play
- balanced play focused on aesthetics plus profitability

## 2. Sandbox mode

Sandbox is a creative mode with fewer economy constraints and a lower barrier to
entry than career mode.

Likely features:

- Spawn fish directly
- Place decorations freely
- Change tank parameters quickly
- Build showcase aquariums
- Optionally share public tanks for observer mode

Guest or no-account sandbox should allow:

- one aquarium
- a curated starter set of fish and decor assets
- prompts to upgrade for more tanks, more assets, and persistence features

Account-backed sandbox can unlock:

- more tank slots
- more asset libraries
- more persistent showcase features

This mode is useful for players who want expression without progression pressure.

## 3. Observer mode

Observer mode allows visitors to view public aquariums from other accounts.

First-pass observer features:

- Browse public tanks
- View tank name, owner, theme, species list, and summary stats
- Watch fish behavior in real time or near-real time
- View featured/popular/recent aquariums
- Like or favorite tanks
- Follow creators
- Leave comments subject to moderation rules

Later possibilities:

- Ranked showcases
- Event tanks or contests
- Curator picks and editorial collections

## Target audience

- Players who enjoy relaxing simulation and idle games
- Players who enjoy design/customization games
- Collectors who like breeding rare variants
- Viewers who enjoy ambient browser experiences

## Session model

The experience should support both:

- **Short sessions**: collect earnings, check breeding status, buy upgrades
- **Long sessions**: build tanks, compare fish traits, watch aquariums, browse social content

## World model

### Tank categories

The design should explicitly support:

- Freshwater tanks
- Saltwater tanks

Potential later extension:

- Brackish tanks
- Specialty biome tanks
- Planted tanks
- Reef systems

### Tank composition

Each aquarium should be defined by:

- Tank size
- Water type
- Capacity rules
- Background/theme
- Substrate
- Decorations/plants/coral/rocks
- Filters, heaters, lights, and other equipment
- Fish population
- Water condition metrics
- Backdrop selection
- Cleanliness/algae state

### Tank archetypes

Early design and progression should explicitly support multiple tank archetypes:

- **Betta display tank** for a single centerpiece fish
- **Tropical community tank** for layered peaceful stocking
- **Breeder utility tank** for profit-focused setups with lighter decoration
- **Cleanup-assisted planted tank** where ecological balance matters

See `docs/starter-freshwater-plan.md` for the current first-pass archetypes.

### Presentation layers

Tank presentation should use layered content that remains readable from a single
side angle:

1. backdrop layer
2. rear decor layer
3. midground fish/gameplay layer
4. foreground decor layer
5. substrate/ground-cover layer

This should allow depth, parallax, and lighting without requiring a moving camera.

## Fish systems

Each fish species should eventually have structured data covering:

- Species identity
- Water type
- Size class
- Rarity
- Preferred tank conditions
- Compatibility notes
- Breeding rules
- Sale value range
- Visual model references
- Habitat category compatibility
- Tankmate behavior rules

The species-level simulation and compatibility contract should live separately from
the render-asset metadata so future fish can be added by pairing:

1. a GLB model plus `metadata.json` for asset loading, and
2. a species-definition JSON file for simulation, behavior, compatibility, and economy

See `docs/content-contracts.md` for the current content model.

### Fish trait layers

To support breeding gameplay, fish should eventually have multiple trait layers:

1. **Species traits** - fixed biological/species rules
2. **Individual stats** - health, growth, fertility, temperament
3. **Visual traits** - color variants, patterns, fin shapes, markings
4. **Inherited genetics** - traits that influence offspring outcomes

### First-pass breeding goals

The breeding system should start readable and expand over time. The first versions
should favor clarity over simulation depth, with room to grow toward deeper
genetics later.

Candidate outcomes from breeding:

- Better sale price
- Rare visual variants
- Improved hardiness
- Faster growth or fertility
- Collector-value lineage combinations

### Hybridization policy

The default expectation should be realism. Hybridization may be supported across
closely related species where it makes sense, with a few curated exceptions for
surprise or easter-egg content.

### Lineage visibility

Fish should retain pedigree/history suitable for advanced players and collectors.
This information should be accessible, but not forced into the primary UX whenever
fish are born or acquired.

### Habitat and social compatibility

Fish should not be treated as generic animated decorations. Species compatibility
must reflect aquarium categories and known behavioral tendencies.

Examples:

- tropical freshwater fish should generally be grouped with other tropical freshwater species
- saltwater fish should require saltwater-compatible tanks and tankmates
- coldwater, brackish, and specialty species should carry explicit habitat requirements
- territorial or aggressive species should behave differently from schooling fish

This means the content model should encode:

- water type compatibility
- habitat category tags such as tropical, coldwater, reef, planted, or blackwater
- school size preferences
- aggression/territoriality
- explicit tankmate restrictions and conflict tags
- cleanup roles such as algae-grazer or detritus-scavenger

### Behavioral authenticity

When players combine fish that do not get along, the simulation should show that
through behavior and tank outcomes instead of silently allowing unrealistic mixes.

Examples of expected behavior:

- a betta placed with incompatible tankmates may chase, posture, or harass them
- schooling fish that are kept in numbers that are too low may behave as stressed or skittish
- territorial fish may defend hideouts or preferred swim zones
- peaceful community fish should spend more time schooling, foraging, or avoiding conflict

The first implementation does not need full biological realism, but species should
have authored behavior profiles that make common aquarium knowledge legible in play.

### Ecological roles and maintenance support

Some fish should contribute to the health and readability of a tank ecosystem.
Examples include:

- algae grazers that reduce algae pressure
- bottom scavengers that reduce leftover waste pressure
- peaceful schooling fish that improve the look and behavior of community tanks
- territorial display fish that create strong solo-tank identity

These support roles should matter, but they should never replace active player
maintenance entirely.

## Economy overview

Career mode should include:

- Standard soft currency earned through gameplay
- Optional premium currency purchasable for acceleration or convenience
- Ad-supported free experience
- Paid ad removal
- Microtransactions focused on quality of life and acceleration

Detailed assumptions are in `docs/economy-and-progression.md`.

## Monetization guardrails

The monetization model should avoid making the game feel hostile or mandatory-pay.

Guidelines:

- Ads should not interrupt core viewing moments excessively
- Premium currency should accelerate progression, not invalidate it
- Purchases should favor convenience, cosmetics, or time-saving
- Sandbox should remain enjoyable without spending
- Monetization should account for hosting, storage, and scaling costs without
  turning progression into a hard paywall

## Content progression

Suggested unlock vectors:

- New fish species
- Expanded tank sizes
- Higher-end decorations
- Advanced breeding tools
- Additional aquarium slots
- Social/public showcase features

## Simulation assumptions

Initial implementation should aim for semi-realistic aquarium behavior presented in
a clear, readable way. It should feel authentic enough for experienced hobbyists
without overwhelming casual players.

### Adaptive difficulty director

Career mode should eventually include an adaptive "director" layer that tunes
challenge and assistance based on player behavior. The goal is to keep the game
fun and tense without pushing players into unwinnable states too easily.

Director responsibilities may include:

- detecting whether a player is casual, design-oriented, or optimization-focused
- softening failure spirals before bankruptcy
- surfacing realistic challenges for advanced players
- nudging toward sustainable play without fully removing consequences
- tuning tips, events, and warning thresholds to match player skill

Recommended early simulation layers:

- Fish hunger
- Maturity/growth timers
- Breeding eligibility
- Tank suitability score
- Passive earnings/value generation
- Basic compatibility rules
- Bounded offline catch-up
- Simple species-authored aggression and schooling behavior
- Visible algae and cleanliness state
- Cleanup-role effects on waste or algae pressure
- Authored decor placement rules such as heavy, rooted, floating, or mounted

Defer deeper realism unless it strengthens gameplay:

- Disease systems
- Detailed water chemistry
- Predator-prey behavior
- Complex maintenance failure cascades
- Full emergent ecosystem simulation

## Social/public features

Public aquariums should be opt-in at the player or tank level.

Candidate first version:

- Public/private tank setting
- Public aquarium page
- Public owner profile summary
- Featured tank feed
- Likes
- Follows
- Comments
- Search by owner, tags, species, and popularity

Public/shared tanks should also consider moderation implications for custom
background uploads before those uploads are broadly enabled.

## Live operations opportunities

Potential future content cadence:

- Seasonal decorations
- light seasonal showcases

## Proposed first playable milestone

The smallest meaningful playable version should likely include:

1. Desktop web delivery
2. One guest-accessible fixed side-view sandbox tank with a curated asset set
3. GLB-based fish model loading with metadata-driven configuration
4. A small set of freshwater fish species
5. Built-in background selection and substrate selection
6. Free-rotation edit mode with snap views for top, side, and orbit inspection
7. Buy/place fish and decorations in at least one mode
8. Fish idle movement with authored species behavior differences
9. Visible cleanliness or algae state
10. Basic breeding and offspring generation for career mode
11. Public sharing for a single opt-in tank

## Risks to manage

- 3D rendering scope becoming too heavy for browser delivery
- Breeding depth becoming too complex too early
- Idle simulation needing server support for offline progression
- Social/public viewing increasing backend complexity significantly
- Monetization design undermining the relaxing tone
- Adaptive difficulty becoming opaque or manipulative if not explained carefully

## Product principles for future agents

- Favor a calming, high-readability UI
- Make systems legible before making them deep
- Keep content data-driven where possible
- Separate simulation rules from presentation
- Treat fish assets and metadata as a formal pipeline, not ad hoc files
- Treat free-rotation edit mode and snap views as editing tools in service of the side-view aquarium presentation
- Design per-mode experiences intentionally instead of forcing one ruleset across
  all players
