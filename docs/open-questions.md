# Open Questions

This file now tracks the remaining decisions that still need refinement after the
first founder questionnaire was answered. Confirmed decisions are recorded in
`docs/founder-decisions.md`.

## Product and mode design

1. For guest sandbox users, how large should the free asset catalog be at launch?
2. Should guests be able to save and return to their sandbox aquarium, or is that
   an account-only feature?
3. Should observer interactions such as likes, follows, and comments be available
   immediately, or unlocked in phases after simple public browsing works well?
4. When should custom backdrop uploads unlock:
   - account creation,
   - premium purchase,
   - creator/showcase tier,
   - or a later post-launch phase?
5. Should public tanks with uploaded backdrops require extra moderation or opt-in
   review before they are shareable?

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

1. When should saltwater unlock in career mode?
2. Which hybridization exceptions should exist beyond strict realism?
3. How much pedigree detail should be visible on the standard fish card before the
   player opens a deeper lineage view?
4. How strong should cleanup-species benefits be relative to direct player cleaning?
5. Should algae/detritus be mostly a visual-and-rating system at first, or should it
   also materially affect fish health and breeding from the beginning?
6. Which starter tank archetypes should be exposed in guest sandbox on day one:
   - betta display,
   - tropical community,
   - planted showcase,
   - guppy breeder,
   - or all of the above?

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
4. Should custom backdrop uploads be stored and transformed in the main backend
   first, or should they be deferred until a dedicated media pipeline exists?
