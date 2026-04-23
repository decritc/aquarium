# 3D Asset Production List

This document translates the current design and milestone specs into a concrete
art-production queue for 3D assets.

It is intended to help the founder begin generating or commissioning assets in a
useful order without wasting time on low-priority content.

## Principles

1. Prioritize assets that unblock the first playable milestone
2. Favor a small number of premium assets over a large number of weak ones
3. Generate assets that prove the tank-building fantasy, not just fill categories
4. Keep browser performance in mind while authoring every model

## Deliverable standard for each 3D asset

Where relevant, each asset should eventually provide:

- `MESHY_PROMPT.md` or equivalent generation brief
- runtime `model.glb`
- preview image or thumbnail
- metadata JSON that matches the repo schemas
- clean scale/origin conventions
- optimized materials and texture sizes appropriate for browser delivery

For fish specifically, preferred deliverables are:

- one runtime GLB
- one preview image
- animation clips where applicable
- one metadata file linked to the species definition

## Fish animation minimums

For the first playable milestone, fish assets should ideally support at least:

- cruise / swim idle
- left turn
- right turn

Strongly preferred for hero species or higher-priority fish:

- feed
- threat display
- rest / hover

Optional later:

- courtship
- attack
- variant-specific flourishes

## Priority 0: must-have first playable assets

These are the assets most important to unblock the first meaningful build.

## A. Fish

### 1. Betta splendens

- Priority: critical
- Role: single-fish showcase / hero fish
- Why first:
  - supports the betta display tank
  - ideal for landing-page and observer captures
  - tests territorial display behavior and surface-focused motion
- Recommended notes:
  - long-fin male presentation first
  - support calm cruise plus threat-display animation if possible

### 2. Guppy

- Priority: critical
- Role: breeder staple / lively community fish
- Why first:
  - supports career fantasy
  - adds color and movement to sandbox tanks
  - useful for population-growth loops later

### 3. Neon tetra

- Priority: critical
- Role: schooling visual fish
- Why first:
  - supports community-tank fantasy
  - helps prove smooth schooling-ish motion and group readability
  - great for side-view motion loops

### 4. Panda corydoras

- Priority: critical
- Role: bottom-dwelling cleanup support fish
- Why first:
  - makes the lower tank zone feel alive
  - supports ecosystem/floor gameplay
  - reinforces that fish roles are different, not just cosmetic

### 5. Otocinclus affinis

- Priority: near-term follow-up
- Role: algae grazer / cleanup support
- Why next:
  - useful for planted and ecosystem tanks
  - supports algae gameplay later
  - not strictly required if first-playable scope is tight

## B. Tank shells / environment containers

These are often forgotten, but they are visible on nearly every screen.

### 6. 5-gallon display tank shell

- Priority: critical
- Role: betta display tank
- Why first:
  - core starter archetype
  - useful for hero shots and cozy showcase compositions

### 7. 10-gallon rectangular starter tank shell

- Priority: critical
- Role: community / breeder starter tank
- Why first:
  - likely the most-used starter tank
  - needed for community and breeder templates

### 8. 15-gallon planted/community variant shell

- Priority: high
- Role: cleaner showcase/planted composition
- Why next:
  - supports more premium observer visuals
  - helps separate tank archetypes beyond only content changes

## C. Decor / hardscape

### 9. Floating log hide

- Priority: critical
- Role: key betta display item
- Why first:
  - central to betta tank identity
  - useful for surface-layer placement validation

### 10. Driftwood branch

- Priority: critical
- Role: signature planted/community centerpiece
- Why first:
  - supports depth composition
  - useful in multiple tank archetypes
  - strong for screenshots and motion loops

### 11. Smooth river rock cluster

- Priority: critical
- Role: safe starter hardscape
- Why first:
  - low-risk filler with real layout value
  - helps validate floor placement and occlusion

### 12. Small cave shelter

- Priority: high
- Role: lower-zone structure
- Why next:
  - supports shy fish / bottom-zone storytelling
  - adds silhouette variation

### 13. Tall hero decor piece

- Priority: high, but optional for first milestone
- Suggested forms:
  - castle,
  - ruin arch,
  - tall temple fragment,
  - stacked rock tower
- Why include:
  - validates multi-angle editor inspection
  - useful for marketing and demoing the orbit/snap-view editor
  - directly addresses the “judge from top and side” requirement

## D. Plants

### 14. Java fern clump

- Priority: critical
- Role: low-risk starter plant
- Why first:
  - supports planted and community templates
  - useful silhouette in side view

### 15. Anubias nana / Anubias on wood

- Priority: critical
- Role: broad-leaf cover plant
- Why first:
  - supports betta and showcase tanks
  - gives strong leaf silhouettes for layered scenes

### 16. Floating water sprite

- Priority: high
- Role: surface cover and fry-support plant
- Why next:
  - supports betta and guppy builds
  - useful for surface occupancy gameplay

## E. Equipment

These can be relatively simple models, but they are visible enough that they
still need polish.

### 17. Small sponge filter

- Priority: critical
- Role: gentle filtration
- Why first:
  - supports betta and beginner tanks
  - should read clearly without dominating the tank

### 18. Basic tropical heater

- Priority: critical
- Role: owner-facing environmental equipment
- Why first:
  - core starter equipment
  - visible in owner mode and editor mode

### 19. Internal power filter

- Priority: high
- Role: stronger community filtration
- Why next:
  - supports community/planted setups
  - useful visual differentiation for higher-flow tanks

## F. Substrate presentation assets

These may be authored more like materials/tiles than hero meshes, but they are
still part of the asset backlog.

### 20. Natural gravel

- Priority: critical
- Role: neutral starter substrate

### 21. Fine sand

- Priority: high
- Role: bottom-dweller/community substrate

### 22. Planted soil dark

- Priority: high
- Role: premium planted-tank substrate

## Priority 1: marketing and polish support assets

These are the next most useful assets once the core milestone queue is covered.

### Marketing mood direction

The first major marketing mood should be:

- **calm premium planted beauty**

That means featured showcase assets should favor:

- a **betta-led hero composition**
- a **soft blue gradient studio backdrop** as the first backdrop choice
- elegant planted compositions
- a **driftwood-led hardscape composition** first
- rock support as secondary structure rather than the main focal mass
- soft bright aquarium lighting
- clean healthy tank reads
- beautiful stillness with subtle life, not loud spectacle

Avoid making the first observer/hero tank feel:

- chaotic
- over-decorated
- theme-park cheesy
- battle-arena dramatic
- cluttered with too many competing focal points

### 23. Signature featured-aquarium hardscape set

Purpose:

- support the handcrafted studio/demo featured tank
- provide premium marketing capture material
- support a betta-led planted showcase composition first

Suggested pieces:

- one hero driftwood or root structure
- one tall statement decor piece
- one layered rock composition
- one premium planted cluster

Preferred composition rule for the first showcase:

- lead with driftwood as the main structural focal point
- use rock only as supporting balance and base weight
- preserve open negative space around the betta hero silhouette

### 24. Additional plant variations

Suggested:

- taller background stem plant
- foreground carpeting cluster
- red-accent plant for visual contrast

### 25. Additional showcase decor set

Suggested:

- premium arch
- themed ornament
- alternate cave/shelter

## Priority 2: later freshwater expansion

These are useful once the first playable and initial marketing surfaces exist.

### Fish candidates

- angelfish
- mollies
- platies
- shrimp/snail cleanup crew if desired later

### Decor/equipment candidates

- breeder box / fry support accessories
- alternate driftwood set
- alternate filter styles
- more shelter pieces

## Priority 3: saltwater expansion

Defer until freshwater and browser-performance goals are proven.

Likely early saltwater needs:

- clownfish
- simple reef-safe hardscape
- coral cluster set
- fish-only saltwater tank shell variant

## Recommended founder production order

If you want the shortest path to useful assets, generate in this order:

1. Betta
2. Guppy
3. Neon tetra
4. Panda corydoras
5. 5-gallon tank shell
6. 10-gallon tank shell
7. Floating log hide
8. Driftwood branch
9. Smooth river rock cluster
10. Java fern
11. Anubias
12. Small sponge filter
13. Basic tropical heater
14. Natural gravel
15. Fine sand
16. Planted soil dark
17. Signature featured-aquarium hero decor set
18. Internal power filter
19. Floating water sprite
20. Otocinclus

## Recommended art-delivery packages

To make generation work easier to manage, batch assets like this:

### Pack 1: Hero fish and showcase tank

- betta
- 5-gallon display tank
- floating log hide
- Anubias
- one premium backdrop-supporting scene composition reference

### Pack 2: Community starter pack

- neon tetra
- panda corydoras
- 10-gallon tank
- driftwood branch
- river rock cluster
- java fern

### Pack 3: Breeder starter pack

- guppy
- sponge filter
- heater
- floating water sprite
- gravel/sand materials

### Pack 4: Featured observer tank pack

- signature hero hardscape set
- premium planted cluster
- one tall statement decor piece

## Prompt workflow recommendation

For founder-driven generation work, each starter asset folder should contain:

1. `MESHY_PROMPT.md` - the generation brief
2. generated mesh output such as `model.glb`
3. preview render stills
4. metadata once the runtime-ready version is accepted

Use the shared style direction in `assets/models/MESHY_STYLE_GUIDE.md` to keep the
entire first asset wave visually consistent.

## Performance reminders for all generated assets

- avoid excessive material counts
- avoid unnecessarily dense meshes
- prefer clean silhouettes over micro-detail that disappears in the browser
- keep textures reasonable for web delivery
- design fish to look good at the side-view gameplay distance, not only in close-up renders

## Implementation guidance for future agents

- Do not request large asset waves before the milestone route that uses them exists.
- Prioritize assets that improve both gameplay and marketing quality.
- Treat the featured observer tank as a production asset set of its own.
- Keep at least one tall statement object in the backlog to validate the editor-camera workflow.
