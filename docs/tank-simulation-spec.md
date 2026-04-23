# Tank Simulation Specification

This document defines the first-pass simulation model for aquariums, including
visible tank state, maintenance, compatibility, and editing/placement behavior.

It is meant to be detailed enough that future agents can implement a playable
simulation loop without inventing core rules from scratch.

## Simulation goals

- Keep the aquarium readable from a fixed side-view camera
- Make fish, decor, substrate, and equipment all matter to outcomes
- Make cleanup species and maintenance support meaningful without replacing the player
- Support a calm simulation that still rewards planning and good stocking choices
- Ensure top-down placement mode can author a tank with meaningful depth and footprint

## Core design principle

The player **views** the tank from a stable side angle, but **edits** the tank in
placement mode with a top-down planning view when needed.

This gives the game both:

- the visual clarity of a side-view aquarium
- the authoring clarity of a layout tool that can reason about front/back depth

## Camera versus editing modes

### Viewing mode

- Fixed side-view camera
- Fish swim through front/mid/back depth lanes
- Decor occludes fish naturally when fish pass behind it
- Algae, substrate, and glass cleanliness remain readable from the side

### Placement mode

Placement mode should support:

- top-down tank layout view
- visible front-to-back depth grid or lanes
- item footprints and collision outlines
- snapping behaviors based on item type
- quick return to side-view preview

Recommended editor affordances:

- top-down grid overlay
- front/mid/back depth bands
- tank wall boundaries and equipment slots
- footprint highlights for blocked versus valid placement
- optional side preview panel so players can check composition while placing

## Tank coordinate model

Future implementations should treat tanks as authored 3D spaces even if the game
is mostly presented in 2.5D.

Recommended logical axes:

- **X**: left to right
- **Y**: bottom to top
- **Z**: front to back depth

Practical interpretation:

- side view primarily shows X/Y
- placement mode primarily manages X/Z footprint and Y anchors

### Placement anchors

Useful anchor types:

- substrate/floor
- background glass
- side glass
- free water volume
- surface
- equipment slot

## Simulation layers

The first implementation should simulate the following layers:

1. Fish population and behavior
2. Tank environment
3. Tank cleanliness and aging
4. Decor/equipment effects
5. Tank presentation and rating

## Core tank stats

These are the recommended first-pass tank-level metrics.

### 1. Temperature

- Driven by tank environment and heaters
- Compared against fish habitat ranges
- Stability matters more than tiny fluctuations

### 2. pH suitability

- First version can be lightly simulated
- May be mostly item/environment-driven rather than player micromanagement

### 3. Water flow suitability

- Important for species such as bettas that prefer lower flow
- Driven by filters and tank type

### 4. Cleanliness

Composite concept made of:

- algae growth
- detritus buildup
- glass dirt
- leftover food pressure

### 5. Comfort

Composite concept influenced by:

- species compatibility
- tank size/crowding
- hideouts and cover
- substrate and decor suitability
- environmental match

### 6. Breeding confidence

Represents how favorable a tank is for successful breeding.

Influenced by:

- species compatibility
- stress
- cleanliness
- environmental correctness
- availability of cover or appropriate hardscape

### 7. Showcase appeal

Useful for sandbox, observer, and social play.

Influenced by:

- theme coherence
- backdrop quality
- healthy-looking tank state
- fish motion/readability
- clutter versus polish

### 8. Maintenance load

Represents how much active upkeep the player needs to perform.

Influenced by:

- stocking density
- amount of food input
- weak equipment
- algae-prone surfaces
- low cleanup support

## Tank cleanliness model

The first implementation does not need advanced chemistry. Instead, it should
use a readable environmental drift model.

### Cleanliness sub-metrics

#### Algae pressure

Increases from:

- light exposure
- time passing
- nutrient load
- poor maintenance

Reduced by:

- player cleaning
- algae-grazing species
- certain plants or setup choices

#### Detritus load

Increases from:

- fish waste
- overfeeding
- higher stocking density

Reduced by:

- cleaning actions
- bottom-scavenging species
- filtration support

#### Glass dirt

Increases over time and visually affects:

- tank polish
- observer/showcase appeal

Reduced mainly by:

- player cleaning

### Design rule

Cleanup fish should slow down negative buildup, not erase it completely.

## Fish contribution model

Each species can contribute positively or negatively to the tank ecosystem.

### Positive contributions

- algae reduction
- detritus reduction
- leftover food reduction
- comfort boost for compatible community setups
- showcase appeal if used well

### Negative pressures

- aggression
- bioload
- crowding
- stress contagion in poor communities
- extra maintenance for messy or prolific species

## Behavior model

The first version should use authored behavior states rather than full emergent AI.

### Fish should be able to:

- idle/cruise
- school
- claim territory
- chase
- hide
- scatter
- rest near favored zones
- feed according to feeding style

### Behavior triggers can include:

- incompatible tankmates nearby
- low school size
- crowding
- insufficient shelter
- preferred zone competition
- breeding state

### Visible outcomes

Behavior should be reflected in:

- animations
- movement patterns
- stress/comfort modifiers
- tank warnings

## Compatibility scoring

Each tank should compute a rough compatibility result:

- **Excellent**
- **Good**
- **Situational**
- **Risky**
- **Poor**

Influencing factors:

- water type
- climate
- size and group size
- temperament mix
- predator/prey or aggression traits
- shared zone competition

This score should not be hidden. Players should receive readable warnings.

## Placement and collision model

### Item classes

Items should expose authored placement behavior:

- heavy
- rooted
- floating
- mounted
- free-place
- backdrop-only

### Placement expectations

- heavy items drop to floor anchors
- rooted items require substrate
- floating items remain near the surface
- mounted items snap to allowed surfaces or slots
- backdrop items never collide with gameplay decor

### Top-down placement requirements

Each placeable item should support enough metadata for editor mode to show:

- top-down footprint width/depth
- optional rotation
- depth occupancy
- collision blocking
- anchor requirements

This is why item data should be authored for both:

- side-view readability
- top-down editing logic

## Substrate and planting model

Substrate should be more than a cosmetic toggle.

### First-pass effects

- planted substrate improves plant eligibility
- gravel supports general freshwater community setups
- sand benefits bottom-dwellers in some tanks
- poor substrate/theme pairing reduces comfort or coherence

## Equipment model

### First-pass equipment roles

- **Heater**: supports temperature range and stability
- **Filter**: reduces maintenance load and improves clarity/flow
- **Lighting**: influences presentation and algae pressure

### First-pass rule

Equipment should be understandable and impactful, but not overly technical.

## Tank rating outputs

At least four outputs should be visible to the player:

1. **Habitat match**
2. **Cleanliness**
3. **Fish comfort**
4. **Showcase appeal**

Career mode may additionally show:

5. **Breeding confidence**
6. **Maintenance load**
7. **Profitability outlook**

## Time model

### Real-time drift

The aquarium should progress over time through:

- fish feeding cycles
- growth and breeding timers
- algae and dirt accumulation
- environmental drift

### Offline catch-up

Offline catch-up should be bounded and approximate for:

- cleanliness drift
- breeding timers
- fish comfort changes

It should avoid exact continuous simulation when offline.

## First playable numeric simplification

The first implementation can compress the full simulation into a few normalized
scales such as 0-100.

Suggested first-pass hidden/internal metrics:

- cleanliness
- algaePressure
- detritusLoad
- comfort
- breedingConfidence
- maintenanceLoad
- showcaseAppeal

Suggested player-facing views:

- Cleanliness: Poor / Fair / Good / Excellent
- Fish comfort: Stressed / Settled / Thriving
- Habitat match: Mismatch / Acceptable / Ideal
- Tank look: Plain / Attractive / Stunning

## Starter balance targets

### Betta display tank

- low fish count
- low flow
- moderate decor value
- low aggression if species kept solo
- high showcase potential

### Community tank

- higher fish count
- moderate maintenance load
- strong schooling visuals
- relies on compatibility and group sizing

### Guppy breeder tank

- lower polish at first
- higher breeding output
- rising maintenance load over time

### Cleanup-assisted planted tank

- moderate setup cost
- strong long-session maintenance payoff
- visible difference in algae/detritus management

## Implementation guidance for future agents

- Do not require orbit-camera editing to support depth placement.
- Support top-down placement mode as the canonical way to place depth-layered decor.
- Keep the side-view tank as the main identity of the game.
- Use authored rules and bounded drift before attempting full ecosystem simulation.
- Expose the consequences of poor compatibility visually and systemically.
