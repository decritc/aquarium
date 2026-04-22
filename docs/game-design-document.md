# Virtual Aquarium Game Design Document

## Document purpose

This document defines the product vision and first-pass design for a browser-based
virtual aquarium game. It is intended to guide future implementation agents so
they can build the game in phases with a shared understanding of the experience.

This is a living document. Unknowns and decisions that need user input should be
tracked in `docs/open-questions.md`.

## Vision

Create a relaxing but strategically rich aquarium simulation where players collect,
design, breed, and showcase animated 3D fish in beautiful tanks.

The game should support three complementary player fantasies:

1. **Aquarium artist** - design visually impressive tanks
2. **Fish breeder** - build a profitable operation through genetics and progression
3. **Observer/visitor** - explore and admire aquariums built by others

## Experience pillars

### 1. Living aquariums

Tanks should feel active and soothing even when the player is not making direct
inputs. Fish movement, schooling, idling, feeding, and tank ambience should make
the aquarium enjoyable to watch.

### 2. Meaningful progression

Career mode should reward long-term planning. Players start small, gradually earn
more money, unlock better fish and equipment, and improve their breeding program.

### 3. Creative expression

Players should be able to create tanks with different themes, decorations, layouts,
 and species mixes within tank rules and habitat compatibility constraints.

### 4. Social visibility

Public aquariums should be easy to browse. Observer mode should make it rewarding
to visit tanks created by other players and potentially follow favorite creators.

### 5. Low-pressure simulation

The game should feel idle-friendly and accessible. It should encourage planning and
experimentation more than punishing micromanagement.

## Core game modes

## 1. Breeder career mode

This is the main progression mode.

Player starts with:

- A small bankroll
- A starter tank
- A limited catalog of fish and decorations
- Basic water-quality and habitat tools

Player goals:

- Buy fish and equipment
- Create tanks that meet species needs
- Breed fish with desirable traits
- Sell fish for profit
- Expand into additional tanks
- Unlock new species, decorations, and systems

Core pressure:

- Limited starting funds
- Habitat constraints
- Breeding cooldowns and maturity time
- Gradual unlocking of premium fish and larger tank options

## 2. Sandbox mode

Sandbox is a creative mode with fewer or no economy constraints.

Likely features:

- Spawn fish directly
- Place decorations freely
- Change tank parameters quickly
- Build showcase aquariums
- Optionally share public tanks for observer mode

This mode is useful for players who want expression without progression pressure.

## 3. Observer mode

Observer mode allows visitors to view public aquariums from other accounts.

First-pass observer features:

- Browse public tanks
- View tank name, owner, theme, species list, and summary stats
- Watch fish behavior in real time or near-real time
- View featured/popular/recent aquariums

Later possibilities:

- Likes or favorites
- Following creators
- Ranked showcases
- Event tanks or contests

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

### Fish trait layers

To support breeding gameplay, fish should eventually have multiple trait layers:

1. **Species traits** - fixed biological/species rules
2. **Individual stats** - health, growth, fertility, temperament
3. **Visual traits** - color variants, patterns, fin shapes, markings
4. **Inherited genetics** - traits that influence offspring outcomes

### First-pass breeding goals

The breeding system should be deep enough to create player goals without becoming
opaque or spreadsheet-heavy.

Candidate outcomes from breeding:

- Better sale price
- Rare visual variants
- Improved hardiness
- Faster growth or fertility
- Collector-value lineage combinations

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

## Content progression

Suggested unlock vectors:

- New fish species
- Expanded tank sizes
- Higher-end decorations
- Advanced breeding tools
- Additional aquarium slots
- Social/public showcase features

## Simulation assumptions

Initial implementation should likely simplify realism in favor of clarity.

Recommended early simulation layers:

- Fish hunger
- Maturity/growth timers
- Breeding eligibility
- Tank suitability score
- Passive earnings/value generation
- Basic compatibility rules

Defer deeper realism unless it strengthens gameplay:

- Disease systems
- Detailed water chemistry
- Predator-prey behavior
- Complex maintenance failure cascades

## Social/public features

Public aquariums should be opt-in at the player or tank level.

Candidate first version:

- Public/private tank setting
- Public aquarium page
- Public owner profile summary
- Featured tank feed

## Live operations opportunities

Potential future content cadence:

- Limited-time species
- Seasonal decorations
- Breeding events
- Showcase challenges
- Daily or weekly goals

## Proposed first playable milestone

The smallest meaningful playable version should likely include:

1. Account creation/sign-in
2. One playable freshwater breeder tank
3. A small set of fish species
4. Buy/place fish and decorations
5. Fish idle movement
6. Basic breeding and offspring generation
7. Sell fish for soft currency
8. Public sharing for a single tank

## Risks to manage

- 3D rendering scope becoming too heavy for browser delivery
- Breeding depth becoming too complex too early
- Idle simulation needing server support for offline progression
- Social/public viewing increasing backend complexity significantly
- Monetization design undermining the relaxing tone

## Product principles for future agents

- Favor a calming, high-readability UI
- Make systems legible before making them deep
- Keep content data-driven where possible
- Separate simulation rules from presentation
- Treat fish assets and metadata as a formal pipeline, not ad hoc files
