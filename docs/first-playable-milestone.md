# First Playable Milestone Specification

This document defines the exact scope of the first meaningful playable release for
the virtual aquarium project.

The goal is to produce a small but polished browser experience that proves the
core product fantasy:

- a beautiful living aquarium in the browser
- smooth fish motion in a side-view presentation
- satisfying tank editing and decoration
- a clear path from landing page to playable sandbox

This milestone is intentionally **not** the full game. It is the first release
that should feel real, premium, and testable by outside users.

## Milestone purpose

This milestone should answer:

1. Does the aquarium feel beautiful and alive in the browser?
2. Does the core tank-building interaction feel good?
3. Does the landing page convert visitors into players?
4. Does observer-style presentation feel strong enough to market?
5. Can the project hit a premium quality bar without overcommitting to full game scope?

## Release shape

The first playable milestone should contain two tightly connected surfaces:

1. **Public landing site**
2. **Guest-accessible sandbox aquarium**

Career mode, full accounts, and social-public aquarium features can remain lighter
or partially stubbed if needed, but the visitor must be able to:

- understand the product quickly
- click into a free sandbox experience
- build a tank
- watch fish move smoothly

## Included scope

## 1. Marketing / public site

Must include:

- premium landing page
- hero section with strong aquarium visual
- clear value proposition
- `Start Free Sandbox` primary CTA
- `Watch Public Aquariums` secondary CTA or placeholder route
- feature blocks for sandbox, career, observer
- visual showcase section
- SEO-ready page structure

May include placeholders for:

- account creation
- newsletter or devlog
- full social/discovery pages

## 2. Guest sandbox

Must include:

- one guest-accessible sandbox tank
- no required account to begin
- starter template selection with exactly three day-one options:
  - betta display
  - tropical community
  - planted showcase
- tank naming
- fish placement
- decor placement
- backdrop selection
- substrate selection
- edit mode with free rotation plus snap views
- side-view aquarium preview

## 3. Aquarium simulation/presentation

Must include:

- fixed side-view aquarium presentation
- 3D fish moving in layered depth
- smooth animation blending and visual interpolation
- visible fish differences by species behavior
- visible cleanliness/algae state
- basic compatibility warnings

## 4. Starter content subset

Minimum included fish:

- Betta
- Guppy
- Neon tetra
- Panda corydoras

Otocinclus can be included if implementation cost remains reasonable, but may be
deferred to the next milestone if needed.

Minimum included item/content categories:

- 2 substrate types
- 2-3 decor items
- 2 plant items
- 2 equipment items
- 2 built-in backdrops

## 5. Editing experience

Must include:

- item selection library
- ghost placement preview
- valid/invalid placement feedback
- undo/redo
- save/apply changes
- cancel/revert changes

Camera support in edit mode must include:

- free orbit
- top snap
- side snap
- return-to-presentation preview

## 6. Observer placeholder

This milestone does not need the full social observer system, but it should
include a **single featured aquarium experience** that acts as the first public
observer destination.

Required shape:

- one featured aquarium route or page
- read-only "public aquarium style" presentation
- observer-safe minimal HUD
- enough quality to support landing-page screenshots and CTA handoff

Deferred:

- full gallery or feed
- search and filters
- broad creator discovery

This is important because the product will be marketed partly through beautiful
tank viewing.

## Explicitly out of scope

The first playable milestone should **not** require:

- full account system
- multiplayer synchronization
- full economy balancing
- advanced breeding genetics
- saltwater content
- custom backdrop uploads
- full moderation system
- complex offline progression
- large fish catalogs
- terrain sculpting

These can be planned, but they should not block the milestone.

## User flow for this milestone

### Public visitor flow

1. Visit landing page
2. Understand the product in 5 seconds
3. Click `Start Free Sandbox`
4. Choose a starter template
5. Load into aquarium screen
6. Place fish and decor
7. Preview side-view tank
8. Continue building or return to landing/explore

### Guest sandbox flow

1. Choose one of three starter templates:
   - betta display
   - tropical community
   - planted showcase
2. Enter aquarium screen
3. Inspect tank in side view
4. Enter edit mode
5. Place substrate, decor, plants, fish, backdrop
6. Use orbit/snap views to inspect placement
7. Return to side-view preview
8. Observe fish motion and tank feel

## Required screens

This milestone should include at minimum:

1. Landing page
2. Mode entry or CTA handoff
3. Guest sandbox template picker
4. Aquarium screen
5. Tank editor state
6. Featured aquarium observer route

## Required player-facing stats

For the first playable, only a small set of player-facing signals should appear.

Required visible indicators:

- habitat match
- cleanliness
- fish comfort
- showcase appeal

Career-only management gauges can be deferred or hidden for now unless they are
needed for a prototype variant.

## Quality bar

This milestone must feel polished, not merely functional.

Requirements:

- fish movement must look smooth
- the aquarium should look good enough for marketing capture
- the landing page must feel premium
- the UI must feel cozy and readable
- observer-style viewing must remain visually clean

If tradeoffs are necessary, prefer:

1. fewer features
2. better motion
3. cleaner visual presentation
4. stronger landing page

over:

- more features with weak quality

## Acceptance criteria

The milestone is successful when:

### Product

- a new visitor can understand the offer quickly
- a visitor can start sandbox play without friction
- the sandbox feels like a real product, not a tech demo

### Visual

- fish appear alive, smooth, and pleasant to watch
- the tank looks attractive in screenshots and short clips
- the side-view aquarium is visually clear and layered

### UX

- edit mode is understandable
- large decor can be inspected from multiple angles
- returning to side-view preview is quick and satisfying

### Technical

- landing page loads quickly
- aquarium route becomes interactive in a reasonable time
- frame pacing remains stable on supported hardware

## Recommended internal build slices

To implement this milestone cleanly, future agents should likely break work into:

1. landing page shell
2. aquarium viewport shell
3. edit mode camera and placement
4. starter content ingestion
5. fish movement/presentation smoothing
6. light stat/warning layer

## What should be captured for review

When this milestone is ready, the team should review:

- landing page screenshots
- landing page loading metrics
- aquarium screen screenshots
- short side-view fish motion clips
- edit mode footage showing orbit/snap views
- a guest flow from landing page to sandbox

## Implementation guidance for future agents

- Treat this as the minimum premium slice, not a prototype dump.
- Do not expand scope by adding broad systems before the core aquarium feels good.
- Build for smoothness, clarity, and trust first.
- If a feature weakens polish or frame pacing, cut it from this milestone.
