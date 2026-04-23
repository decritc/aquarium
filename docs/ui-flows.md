# UI Flows

This document defines the first-pass UI/UX flows for the virtual aquarium game.
It is intended to bridge the gap between high-level game design and future app
implementation.

## UX goals

- Keep the experience calm and visually focused
- Make mode selection clear from the beginning
- Let players get to a meaningful aquarium quickly
- Surface warnings and complexity gradually instead of front-loading them
- Support both creative and systems-driven players without forcing one path

## Primary navigation structure

The application should be organized around a small number of top-level spaces:

1. **Home / Landing**
2. **Mode entry**
3. **My aquariums**
4. **Observer / Explore**
5. **Shop / upgrades**
6. **Profile / account**

The exact navigation chrome may differ between guest and account users.

## 1. Landing flow

### Guest landing goals

For a new guest user, the first screen should quickly communicate:

- this is a living aquarium game
- there are multiple ways to play
- they can begin without creating an account

Recommended primary actions:

- **Start sandbox**
- **Browse aquariums**
- **Sign in / create account**

Secondary content:

- featured aquariums
- a short statement of the three play styles
- a gentle note about account benefits

### Account landing goals

For signed-in users, the landing page should emphasize continuity:

- continue last aquarium
- check tank status
- see breeding/progression updates
- open explore/observer mode

Recommended primary actions:

- **Continue last tank**
- **My aquariums**
- **Explore**
- **Shop**

## 2. Mode entry flow

Mode choice should be explicit and beginner-friendly.

Recommended mode cards:

### Sandbox mode card

- message: design and experiment freely
- emphasize: creativity, decoration, fish placement
- show: one-tank guest limit if relevant

### Career mode card

- message: start small and build a breeding business
- emphasize: money, species unlocks, progression
- show: requires account or account prompt if needed

### Observer mode card

- message: watch and explore public aquariums
- emphasize: featured tanks, creators, ambient viewing

## 3. Sandbox flow

### Guest sandbox first-time flow

1. Choose sandbox
2. Choose starter template:
   - betta display
   - tropical community
   - planted showcase
3. Enter tank editor with default starter content
4. Preview tank in side-view
5. Place decor/fish
6. Receive optional upgrade prompts for saving, more content, or more tanks

### Sandbox in-session flow

Key panels or actions:

- tank name and template
- fish library
- item library
- backdrop picker
- substrate picker
- edit mode toggle
- side-view preview
- share/public toggle for eligible users

## 4. Career flow

### First-time career flow

1. Enter career mode
2. Receive a short setup summary:
   - starting credits
   - starter tank options
   - beginner species available
3. Choose a first direction:
   - betta display
   - community tank
   - guppy breeder
4. Enter aquarium management view
5. Use guided tips for first purchases and stocking

### Career in-session loop

The main career dashboard should allow players to:

- review tank status
- collect income
- inspect fish comfort/compatibility
- check breeding progress
- buy or sell fish
- buy equipment/decor
- switch between aquariums

## 5. Observer / Explore flow

Recommended explore entry points:

- featured tanks
- trending tanks
- recent tanks
- species-based browsing
- creator search

Each public tank page should include:

- tank title
- owner name
- tank image/live view
- visible species list
- style/theme tags
- likes/follows/comments actions when enabled

## 6. Aquarium screen structure

The aquarium screen should be composed from a few stable zones.

### A. Main tank viewport

- default side-view aquarium
- fish motion and visible cleanliness state
- backdrop visible behind content
- quick controls for pause, feed, inspect, and edit

### B. Context panel

Switchable by tab:

- **Overview**
- **Fish**
- **Items**
- **Environment**
- **Breeding**
- **Warnings**

### C. Action bar

Recommended actions:

- feed
- clean
- edit tank
- shop
- share / publish

## 7. Editing flow

Editing should be clearly separated from passive viewing.

Recommended editor entry options:

- **Edit layout**
- **Edit backdrop**
- **Edit fish placement**

### Editing flow

1. Enter edit mode
2. Switch to free-rotation editor camera
3. Select category:
   - decor
   - plants
   - equipment
   - substrate
   - backdrop
4. Place, move, rotate, or remove item
5. Snap to preset views:
   - top
   - front/side
   - left/right side
6. Return to side-view preview
7. Confirm or cancel changes

## 8. Warnings and guidance UX

Warnings should be readable and non-hostile.

Examples:

- "This betta may become aggressive with guppies."
- "This school is too small for neon tetras to feel secure."
- "Algae growth is rising. Add maintenance or cleanup support."
- "This heavy decor will block mid-level swim space."

Warnings should include:

- issue description
- severity
- likely cause
- simple recommended fix

## 9. Progressive disclosure

The UI should avoid dumping all simulation complexity on the player at once.

Recommended progression:

- early: simple labels and warnings
- mid: reveal more detail in care and compatibility panels
- advanced: expose deeper pedigree, breeding, and analytics tools

## 10. Guest-to-account conversion points

Natural moments for upgrade prompts:

- when trying to save a guest sandbox
- when trying to create a second tank
- when trying to upload a custom backdrop
- when trying to access broader asset libraries

These should feel helpful, not punitive.

## First implementation UX recommendation

The first meaningful UI prototype should include:

- landing page
- mode selection
- guest sandbox entry
- aquarium viewport
- edit mode
- fish/item library panels
- simple warning panel
- explore page placeholder

That would create an implementable end-to-end shell for future agents.
