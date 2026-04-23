# Tank Presentation and Environment

This document defines how aquariums should be presented visually and how tank
environment systems should behave in the first implementation phases.

## Camera and presentation direction

The game should use a mostly fixed **side-view presentation**:

- one primary camera angle looking through the side glass
- no free-look orbit camera required for the core experience
- 3D fish and 3D decor should still provide depth, layering, and believable motion
- the presentation should feel like a living animated diorama rather than a fully
  navigable 3D scene

This keeps the game visually rich while preserving a calmer, more readable UI.

## Placement mode and editing perspective

Because fish and decor use real front-to-back depth, the player needs a clearer
editing tool than the side-view alone can provide.

Recommended rule:

- **viewing mode** stays side-on and presentation-focused
- **placement mode** supports free rotation/orbit around the tank for inspection and
  placement
- **placement mode** should also provide quick snap views such as top, front, and side
  to help players judge spacing, height, and silhouette

This should not be treated as a contradiction. Editing is allowed to be more
tool-like than normal viewing. The side-view remains the primary player-facing
aquarium view, but editing should let players inspect the tank from whatever angle
is needed to place large objects, terrain, or layered decor confidently.

### Editing camera expectations

Editing camera should support:

- free orbit around the tank
- zoom in/out
- snap to top view for footprint planning
- snap to side view for silhouette and height checks
- quick return to the standard presentation view

Examples:

- placing a castle should allow the player to inspect footprint from above and final
  silhouette from the side
- placing terrain should allow the player to rotate around hills and valleys before
  confirming the layout
- placing tall plants or rear hardscape should allow front/back occlusion checks

## Visual style target

The tank should behave like a **2.5D aquarium stage**:

- fish swim in 3D space with depth variation
- decor occupies foreground, midground, and background depth layers
- the player views everything from a stable side angle
- parallax and lighting can sell depth without requiring camera movement

This means the renderer should support:

- layered depth placement
- soft shadows and water-light caustic effects
- readable silhouettes for fish and decor
- stable framing suitable for showcase sharing

## Tank layers

Each aquarium should be treated as layered content:

1. **Backdrop layer**
   - built-in backgrounds from the game
   - optional player-uploaded background images
   - color tinting and theme variants

2. **Rear decor layer**
   - rooted plants
   - rear rocks and driftwood
   - mounted equipment

3. **Midground gameplay layer**
   - major structures
   - shelters
   - centerpiece decor
   - the main fish swim volume

4. **Foreground layer**
   - front plants
   - pebbles
   - small decor accents
   - particles and interface highlights

5. **Ground cover/substrate layer**
   - sand, gravel, soil, coral substrate
   - detritus/algae/cleanliness overlays

## Physics-inspired decor placement

The first implementation does not need full rigid-body simulation, but object
placement should respect intuitive aquarium rules.

### Placement expectations

- heavy items fall and settle to the bottom of the tank
- rooted items anchor into substrate zones
- floating items stay near the surface
- wall/equipment items attach to allowed glass or equipment slots
- large structures should respect collision/overlap rules

### Practical implementation recommendation

Use authored placement behavior rather than full simulation:

- **heavy decor** snaps downward until supported by the floor or another item
- **floating decor** snaps upward toward the surface region
- **rooted plants** require substrate coverage
- **background panels** live in a separate non-colliding backdrop slot

This gives players expected behavior without expensive general-purpose physics.

The editor should make these behaviors visible through:

- item footprints
- front/back depth occupancy
- collision outlines
- snap previews
- side-preview confirmation
- free-rotation inspection before confirming placement

## Tank types and archetypes

Tank presentation should support multiple aquarium forms, especially in career mode.

Important early examples:

- **Betta display tank**
  - small single-fish showcase tank
  - built for one territorial fish
  - encourages shelter, resting areas, and decorative presentation

- **Community tank**
  - wider side-view tank for schooling and peaceful species mixes
  - emphasizes balance, schooling, and themed decor

- **Breeder setup**
  - more utilitarian presentation
  - simpler decor
  - efficient placement for breeding and maintenance

## Backgrounds and custom uploads

Backgrounds are an important creative tool and should be first-class content.

### Built-in background support

The game should ship with:

- neutral aquarium backdrops
- natural aquatic scenes
- planted-tank themed backgrounds
- rockwall and riverbed themes
- decorative showcase themes

### Player-uploaded backgrounds

Players should eventually be able to upload their own background images for tanks.

Requirements:

- uploads should be opt-in and per tank
- uploaded images should be cropped/scaled to tank aspect ratios
- moderation and content-policy controls will be required before broad rollout
- public/shared tanks using uploaded backgrounds may need extra review or safety checks

### Design recommendation

For early implementation:

1. ship curated built-in backgrounds first
2. support account-backed custom uploads later
3. treat custom uploads as a premium or account feature only if needed for cost/moderation reasons

## Ground cover and substrate

Ground cover should matter visually and mechanically.

Examples:

- gravel
- sand
- planted substrate
- coral rubble
- mud/blackwater substrate variants

Substrate can affect:

- plant placement eligibility
- habitat suitability
- tank cleanliness perception
- species comfort modifiers
- overall tank rating/theme coherence

## Algae, detritus, and cleanliness

Aquariums should change visually over time.

### First-pass environmental aging

The tank should be able to accumulate:

- algae on glass or hardscape
- detritus on substrate
- clutter or waste in under-maintained zones

This should be readable from the side-view presentation through:

- glass overlay buildup
- green/brown growth on surfaces
- substrate discoloration
- reduced visual polish score

### Gameplay role

Algae and dirt buildup should be part of tank management, not just decoration.

Possible consequences:

- lower tank rating or showcase appeal
- reduced fish comfort for some species
- more maintenance actions required
- slight reductions in breeding confidence or visitor appeal

### Important nuance

Some buildup can be natural or even beneficial in the right context. The game should
distinguish between:

- healthy natural growth in a mature planted tank
- neglected overgrowth that signals poor maintenance

## Cleanup species and ecological balance

Tank balance should include species that help manage algae, detritus, or leftovers.

Examples of cleanup roles:

- algae grazers
- bottom scavengers
- detritus pickers
- snail/shrimp cleanup crews

### Design goal

Players should be rewarded for building balanced aquariums, not only for adding
expensive fish.

This means:

- some species should contribute passive tank-cleanliness benefits
- some species should reduce visible algae or waste pressure
- cleanup species should have their own compatibility constraints and not function as
  magical universal fixes

Example:

- a peaceful bottom-dweller can help with leftover food and detritus
- an algae grazer can reduce algae buildup, but may still require appropriate tank size and diet

## Tank maintenance loop

The presentation and environment systems should support a readable maintenance loop:

1. feed fish
2. observe behavior and tank appearance
3. notice algae, detritus, crowding, or equipment mismatch
4. adjust fish mix, decor, equipment, or maintenance actions
5. restore tank health and visual appeal

This loop should feel visible in the tank itself, not only in hidden stats panels.

## Required content/data support

To support this design, future content contracts should continue to allow:

- tank archetype metadata
- backdrop definitions and upload settings
- item placement behaviors such as heavy, floating, mounted, or rooted
- species roles such as cleanup crew, algae grazer, territorial display fish, or schooling fish
- environment-ageing values such as algae susceptibility and cleanliness drift

## First playable recommendation

The earliest meaningful visual implementation should support:

- one fixed side-view tank scene
- depth-layered decor
- falling heavy decor placement
- built-in background selection
- substrate/ground cover selection
- visible algae cleanliness state
- at least one species that benefits from cleanup or balance play

That will make the aquarium feel like a designed living system rather than a static
fish viewer.
