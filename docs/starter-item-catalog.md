# Starter Item Catalog

This document defines the first recommended item catalog for freshwater sandbox and
career play. It is intended to pair with the starter roster and tank simulation
spec so implementation agents know what players can actually place in the first
meaningful build.

## Catalog design goals

- Support the first four freshwater tank archetypes
- Keep the catalog small enough to tune clearly
- Teach placement behavior through item types
- Ensure players can build a beautiful tank, a practical breeder tank, or a
  balanced ecosystem tank
- Make depth placement and side-view readability matter

## Placement-mode guidance

Because the live tank is viewed from the side but contains true depth, placement
mode should support a simplified **top-down layout view** for editing.

The item catalog should therefore provide enough data for:

- footprint on the tank floor
- depth occupancy
- whether the item belongs on the floor, the wall, the surface, or the backdrop
- whether it is heavy, rooted, mounted, floating, or free-placed

This means an implementation can:

- let the player position rocks and driftwood from above
- preserve front/back layering for side-view presentation
- prevent impossible overlaps
- keep fish swim lanes readable

## Category overview

### Substrate

1. **Natural gravel**
   - Use: all-purpose beginner substrate
   - Role: neutral starter choice

2. **Fine sand**
   - Use: community and bottom-dweller tanks
   - Role: improves comfort for corydoras-style fish

3. **Planted substrate**
   - Use: planted and ecosystem tanks
   - Role: supports rooted plants and visual maturity

### Equipment

4. **Basic tropical heater**
   - Use: maintains tropical range
   - Role: required for most starter freshwater species

5. **Small sponge filter**
   - Use: low-flow gentle filtration
   - Role: useful in betta display and fry-aware setups

6. **Internal power filter**
   - Use: stronger filtration for community or breeder tanks
   - Role: reduces waste pressure but may conflict with low-flow fish

### Plants and habitat support

7. **Anubias on wood**
   - Use: low-maintenance broad-leaf plant
   - Role: visual quality, cover, low beginner friction

8. **Java fern clump**
   - Use: low-risk planted tank support
   - Role: shelter and planted identity

9. **Floating water sprite**
   - Use: surface cover and fry protection
   - Role: helps betta and guppy setups

### Decor

10. **Floating log hide**
    - Use: surface shelter
    - Role: key betta display item

11. **Driftwood branch**
    - Use: centerpiece structure
    - Role: gives depth, cover, and planted-tank identity

12. **Smooth river stones**
    - Use: bottom structure and visual variety
    - Role: safe hardscape for beginner layouts

13. **Small cave shelter**
    - Use: territory marker / lower-zone structure
    - Role: supports bottom dwellers and shy fish

### Backdrops

14. **Blue gradient studio**
    - Use: neutral showcase backdrop

15. **Planted river scene**
    - Use: natural community presentation

16. **Dark blackwater scene**
    - Use: moody dramatic display tanks

17. **Clean breeder panel**
    - Use: practical low-distraction breeder setup

## Starter archetype mapping

### Betta display tank

Recommended starter kit:

- natural gravel or planted substrate
- basic tropical heater
- small sponge filter
- floating log hide
- Anubias or java fern
- blue gradient or dark blackwater backdrop

### Tropical community tank

Recommended starter kit:

- fine sand or natural gravel
- basic tropical heater
- internal power filter
- java fern
- smooth river stones
- driftwood branch
- planted river backdrop

### Guppy breeder tank

Recommended starter kit:

- natural gravel
- basic tropical heater
- small sponge filter or internal power filter
- floating water sprite
- breeder panel backdrop

### Cleanup-assisted planted tank

Recommended starter kit:

- planted substrate
- basic tropical heater
- internal power filter
- java fern
- Anubias
- driftwood branch
- smooth river stones
- planted river backdrop

## Placement behavior by item type

### Heavy items

Examples:

- smooth river stones
- driftwood branch
- cave shelter

Rules:

- placed from top-down mode onto floor coordinates
- settle to the bottom
- occupy physical footprint and depth
- can block swim paths if overused

### Rooted items

Examples:

- java fern
- Anubias

Rules:

- require valid substrate or attachment support
- occupy floor coordinates but rise vertically in side view
- may create cover or sightline breaks

### Floating items

Examples:

- floating log hide
- floating water sprite

Rules:

- placed in top-down mode with surface position
- rendered near the top water line in side view
- can compete for surface space used by bettas or other surface fish

### Mounted equipment

Examples:

- internal power filter
- heater

Rules:

- attach to valid rear/side equipment slots
- do not occupy floor space the same way as hardscape
- still affect side-view readability and rear-layer clutter

### Backdrops

Examples:

- planted river scene
- breeder panel

Rules:

- selected outside normal floor placement
- fill the rear backdrop layer
- affect theme and showcase presentation

## Tuning philosophy

- Beginner items should communicate their purpose visually.
- The first catalog should avoid dozens of near-duplicate decorations.
- Every starter item should either:
  - teach a tank-management concept,
  - improve visual identity,
  - or support a specific fish role.
- The top-down placement editor should make spacing and overlap easy to reason
  about, even though the tank is ultimately displayed from the side.

## Recommended first implementation subset

If implementation scope needs to stay very small, the minimum useful item set is:

1. natural gravel
2. basic tropical heater
3. small sponge filter
4. floating log hide
5. java fern
6. smooth river stones
7. planted river backdrop
8. blue gradient studio backdrop

That is enough to build:

- one betta display tank
- one simple community tank
- one visibly layered side-view aquarium
