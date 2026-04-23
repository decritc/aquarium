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
- Favor a playful, cozy, life-sim-inspired interface over a harsh mechanical dashboard
- Keep observer mode visually clean so tanks can function as relaxing viewing experiences

## Visual language direction

The UI should feel more like a cozy life-sim interface than a sterile management
application.

Target qualities:

- soft shapes and rounded panels
- friendly iconography
- playful but readable typography choices
- warm, inviting color accents
- clear hierarchy without "control room" aesthetics
- a polished, Sims-like friendliness rather than industrial simulation UI

This means:

- panels should feel like lightweight cards, tabs, trays, or bubbles
- heavy spreadsheet-style layouts should be avoided in standard play
- warnings should feel supportive and gently instructive rather than alarming
- observer mode should be especially minimal and calm

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

The landing page is not a throwaway splash screen. It should function as:

- the first trust signal that this is a premium-quality web game
- the main SEO surface for discovery
- a polished conversion path into sandbox, observer mode, or account creation

The visual bar should be closer to a premium AI/product landing page than a rushed
indie placeholder:

- strong hero composition
- high-quality graphics and tank visuals
- clear typography hierarchy
- premium motion restraint
- no generic or obviously low-quality placeholder art

The goal is to feel professional and intentional, not like AI-generated slop or a
temporary mockup.

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

The landing page should also support:

- search-friendly descriptive page copy
- clear feature sections for sandbox, career, and observer play
- visible proof of visual quality through curated screenshots or live tank captures
- fast page load and high Core Web Vitals performance

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
- allow director-style selection before or during setup

### Observer mode card

- message: watch and explore public aquariums
- emphasize: featured tanks, creators, ambient viewing

## 2A. Director style selection

Players should be able to choose the tone of the AI director much like selecting a
storyteller or experience profile in a simulation game.

Recommended early presentation:

- as part of career setup
- editable later from settings or tank-management preferences
- described in player-friendly language rather than abstract difficulty jargon

Candidate presentation styles:

### Cozy / Good Vibes

- minimal pressure
- gentle reminders
- fewer disruptive setbacks
- ideal for zen players and showcase-oriented play

### Balanced

- moderate challenge
- standard pacing
- supportive but not passive

### Hardcore Breeder

- sharper economic pressure
- stronger realism consequences
- intended for players who want a more demanding simulation

The language should stay warm and inviting even for higher-pressure options.

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
6. Use temporary browser-local save during the session window
7. Receive optional upgrade prompts for stronger persistence, more content, or more tanks

### Sandbox in-session flow

Key panels or actions:

- tank name and template
- fish library
- item library
- backdrop picker
- substrate picker
- edit mode toggle
- side-view preview
- public/observable toggle for eligible users

Sandbox should feel especially low-pressure, with:

- minimal warning noise
- gentle suggestion language
- easy hiding/collapsing of editing panels
- a presentation mode that can leave the tank mostly unobstructed

Guest save behavior for the first implementation:

- allow temporary browser-local persistence for the active guest sandbox
- do not promise durable cross-device or account-level persistence
- use account upgrade prompts when the player wants stronger save guarantees

Public-setting rule:

- if a tank is marked public, that means it is observable by other users
- future share links or public entry points should reflect that observable state

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

Career mode may show owner-only management tools such as:

- pH indicator
- water temperature gauge
- cleanliness meter
- fish health indicators
- breeding readiness or compatibility warnings

Default career HUD recommendation:

- compact gauges plus warnings
- lightweight enough to preserve the aquarium as the visual focus
- expandable later for deeper management, but not dense by default

These tools are meant for the owner and should not appear in observer mode.

## 5. Observer / Explore flow

Recommended explore entry points:

- featured aquarium first
- broader tank discovery later
- trending/recent/species search as later expansion

Rollout rule:

- once there are roughly 10+ public/observable user tanks, observer mode should
  graduate from single-featured-only into a lightweight discoverability surface
  with browsing support

Each public tank page should include:

- tank title
- owner name
- tank image/live view
- visible species list
- style/theme tags
- likes/follows/comments actions when enabled

### Observer presentation rule

Observer mode should avoid cluttering the tank with owner-management UI.

Do show:

- tank title and creator
- species summary
- style/theme information
- social actions

Do not show by default:

- pH gauges
- owner health overlays
- breeding panels
- maintenance warnings
- economy metrics

Observer mode should feel capable of becoming a relaxing "aquarium screensaver"
experience.

### First implementation observer entry

For the first implementation, the landing-page CTA `Watch Public Aquariums`
should open a **single featured aquarium experience** rather than a full gallery.

Why:

- faster to polish to a premium standard
- easier to market visually
- lower discovery/backend complexity for the first release
- still proves the observer fantasy clearly

Source for the first implementation:

- use a handcrafted studio/demo tank
- do not depend on live player-published aquariums yet
- art-direct it to a premium visual standard suitable for screenshots and hero-adjacent marketing use

## 6. Aquarium screen structure

The aquarium screen should be composed from a few stable zones.

### A. Main tank viewport

- default side-view aquarium
- fish motion and visible cleanliness state
- backdrop visible behind content
- quick controls for pause, feed, inspect, and edit

The viewport should support different chrome levels by mode:

- **career owner view**: richer owner HUD and management tools
- **sandbox creator view**: lighter creative controls
- **observer view**: minimal overlays and social chrome only

### B. Context panel

Switchable by tab:

- **Overview**
- **Fish**
- **Items**
- **Environment**
- **Breeding**
- **Warnings**

Panels should feel collapsible and non-oppressive. Default state should prioritize
the aquarium itself, not bury it under dense management chrome.

### C. Action bar

Recommended actions:

- feed
- clean
- edit tank
- shop
- share / publish

In observer mode, the action bar should collapse down to a much lighter strip such as:

- like
- follow
- comment
- view creator

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

For lower-pressure director styles, warnings should feel more like guidance than
failure alerts.

## 9. Progressive disclosure

The UI should avoid dumping all simulation complexity on the player at once.

Recommended progression:

- early: simple labels and warnings
- mid: reveal more detail in care and compatibility panels
- advanced: expose deeper pedigree, breeding, and analytics tools

This is especially important because the game should support:

- zen players who mostly want a beautiful living tank
- strategic players who want deeper management detail

## 10. Guest-to-account conversion points

Natural moments for upgrade prompts:

- when trying to save a guest sandbox
- when trying to create a second tank
- when trying to upload a custom backdrop
- when trying to access broader asset libraries

For the first implementation, this should be framed carefully because guest users
do have temporary browser-local persistence. The upgrade prompt should emphasize:

- stronger persistence and account-backed saves
- multi-device continuity later
- more tanks and broader content access

These should feel helpful, not punitive.

## First implementation UX recommendation

The first meaningful UI prototype should include:

- landing page
- mode selection
- director-style selection
- guest sandbox entry
- aquarium viewport
- edit mode
- fish/item library panels
- simple warning panel
- explore page placeholder

It should also demonstrate:

- a cozy/cartoony UI tone
- owner-only management gauges in career mode
- a lighter unobtrusive observer presentation

That would create an implementable end-to-end shell for future agents.
