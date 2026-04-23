# Tank Editor UX

This document defines the expected user experience for editing and decorating an
single aquarium.

It complements:

- `docs/tank-presentation-and-environment.md`
- `docs/tank-simulation-spec.md`
- `docs/ui-flows.md`

## Editor goals

- Make tank building feel tactile and satisfying
- Preserve the side-view aquarium identity during normal play
- Provide enough editing freedom to judge object scale and depth
- Keep advanced placement readable for casual players
- Support both quick decoration and deeper aquarium planning

## Core editor principle

The tank editor should support **free inspection**, but not force complex 3D
controls on every user.

That means:

- the player can freely orbit/rotate the tank in edit mode
- the editor should provide shortcut views for common tasks
- the player should always be able to snap back to the default side presentation

## Editor camera modes

### 1. Presentation preview

- Matches the normal side-view aquarium
- Used to confirm how the finished tank will look in regular play

### 2. Top-down layout view

- Best for spacing, footprint, swim lanes, and front/back placement
- Useful for rocks, driftwood, castles, and plant spacing

### 3. Side elevation view

- Best for checking item height
- Useful for castles, tall plants, stacked terrain, or shelters
- Important for understanding hills, valleys, and silhouette

### 4. Free orbit view

- Best for inspection and fine composition
- Lets the player rotate around the tank and examine depth layering
- Should remain constrained enough to avoid disorientation

## Recommended camera controls

### Mouse and keyboard

- Left drag: orbit in free view
- Right drag or modifier drag: pan
- Mouse wheel: zoom
- Hotkeys or toolbar buttons:
  - `1` side view
  - `2` top view
  - `3` front/side elevation variant
  - `4` free orbit

### Touch-friendly support later

- two-finger pan
- pinch zoom
- drag rotate in free view

## Editing workflow

### Standard placement loop

1. Choose category
2. Select item
3. Preview ghost placement
4. Position the item
5. Rotate or adjust if allowed
6. Confirm placement
7. Preview the tank from side view

### Suggested user loop for large scenery

For items like castles, arches, or major terrain:

1. place from top view for footprint
2. inspect from side view for height and silhouette
3. inspect from free orbit for volume and occlusion
4. confirm or reposition

### Suggested user loop for terrain and substrate shaping

If terrain shaping exists later:

1. use top-down view for footprint and distribution
2. use side/elevation view to inspect hills and valleys
3. use free orbit for final shape validation

## Editor layout

Recommended desktop layout:

### Left panel

- item categories
- search/filter
- favorites/recent items

### Center canvas

- active tank edit viewport
- camera mode toggle
- grid and collision overlays
- placement ghost and snapping feedback

### Right panel

- selected item properties
- placement hints
- compatibility/effect summary
- environment impact preview

### Bottom bar

- undo / redo
- side preview toggle
- hide UI for showcase preview
- save / cancel / publish buttons

## Placement feedback

Players should get clear feedback before placing an item.

### Valid placement feedback

- green outline
- visible snap target
- helper text like "Anchors to substrate"

### Invalid placement feedback

- red outline
- reason label such as:
  - "Needs substrate"
  - "Blocks equipment slot"
  - "Too tall for this tank"
  - "Overlaps existing decor"

### Helpful preview overlays

- item footprint
- blocked cells/regions
- front/mid/back depth occupancy
- swim-lane obstruction
- shelter or cover influence

## Player-friendly complexity management

Not every player wants a heavy building tool.

Recommended accessibility features:

- simple placement mode with automatic snapping
- advanced placement toggle for manual adjustment
- preset layout templates for beginners
- reset camera button
- "show final side preview" button

## Context-sensitive guidance

The editor should surface meaningful aquarium advice while placing.

Examples:

- "This betta tank has little surface cover."
- "This castle blocks most of the midwater swim lane."
- "These bottom rocks reduce open area for corydoras."
- "This backdrop fits the current planted theme."
- "This filter may create too much flow for a betta display tank."

## Terrain and large-object considerations

Your examples highlight why edit mode cannot be top-down only.

### Castles or tall decor

The player needs to see:

- floor footprint
- height
- front/back bulk
- final side-view silhouette

### Terrain and contours

If hills, mounds, or shaped substrate become editable, the player needs to see:

- surface outline from above
- height profile from the side
- final composition from the regular tank view

This is a strong argument for keeping:

- snap camera presets
- side/elevation preview
- free orbit inspection

## Beginner versus advanced editor modes

### Beginner mode

- category-based placement
- automatic snapping
- limited rotation where appropriate
- strong warnings and tips

### Advanced mode

- finer placement controls
- orbit camera
- depth management
- optional rotation increments
- richer overlays

## Save and preview states

Players should be able to:

- preview edits before saving
- revert unsaved changes
- compare side-view before/after
- publish or share after confirming final composition

## UX principle for future agents

The editor should feel like:

- a calm aquarium design studio,
- not a CAD tool,
- while still giving enough camera freedom to judge large objects, terrain height,
  and depth composition.
