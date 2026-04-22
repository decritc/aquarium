# Open Questions

This file now tracks the remaining decisions that still need refinement after the
first founder questionnaire was answered. Confirmed decisions are recorded in
`docs/founder-decisions.md`.

## Product and mode design

1. For guest sandbox users, how large should the free asset catalog be at launch?
2. Should guests be able to save and return to their sandbox aquarium, or is that
   an account-only feature?
3. In career mode, should players begin with one starter tank plus optional extra
   tank purchases, or should all tanks be purchased manually from the beginning?
4. Should observer interactions such as likes, follows, and comments be available
   immediately, or unlocked in phases after simple public browsing works well?

## Adaptive challenge and AI director

1. How visible should the AI director be to the player?
   - Hidden system only
   - Exposed through advisor-style messaging
   - Exposed through difficulty profiles
2. What knobs should the director be allowed to adjust?
   - Market prices
   - Maintenance costs
   - Random events
   - Contract opportunities
   - Breeding odds
   - Tutorial/intervention hints
3. Should the director ever allow fish death in order to preserve realism for
   expert players, or should it always bias toward softer failure states?

## Progression and monetization

1. What should the first paid upgrade path be for guest sandbox users:
   - Ad removal
   - Premium asset pack
   - More tank slots
   - Full account upgrade bundle
2. Should career-mode currency purchases be tightly capped to preserve pacing, or
   left mostly open-ended?
3. Should cosmetic monetization focus first on:
   - decorations,
   - lighting/background themes,
   - profile/showcase presentation,
   - or all of the above?

## Fish systems and content

1. What is the first freshwater starter roster?
2. When should saltwater unlock in career mode?
3. Which hybridization exceptions should exist beyond strict realism?
4. How much pedigree detail should be visible on the standard fish card before the
   player opens a deeper lineage view?

## Technical decisions

1. Should the server begin in TypeScript and only move performance-critical logic
   to Rust/WASM later, or should we plan for Rust services earlier?
2. Which frontend systems are most likely to benefit from WASM first:
   - fish movement/simulation,
   - genetics calculations,
   - pathing/flocking,
   - or asset processing?
3. For offline progression, what should be exact versus approximated:
   - earnings,
   - breeding timers,
   - fish health,
   - visitor activity?
