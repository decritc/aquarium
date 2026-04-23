# Open Questions

This file now tracks the remaining decisions that still need refinement after the
first founder questionnaire was answered. Confirmed decisions are recorded in
`docs/founder-decisions.md`.

## Product and mode design

1. For guest sandbox users, how large should the free asset catalog be at launch?
2. Resolved: guest sandbox should use temporary browser-local save behavior in the
   first implementation rather than full account-backed persistence.
3. Resolved: tanks marked public should be treated as observable by others.
4. Should observer interactions such as likes, follows, and comments be available
   immediately, or unlocked in phases after simple public browsing works well?
5. When should custom backdrop uploads unlock:
   - account creation,
   - premium purchase,
   - creator/showcase tier,
   - or a later post-launch phase?
6. Should public tanks with uploaded backdrops require extra moderation or opt-in
   review before they are shareable?

## Adaptive challenge and AI director

1. Which director profiles should exist in the first implementation beyond a
   general default?
   - laid-back / cozy
   - balanced
   - challenge-seeking
   - extreme / harsh
2. How visible should the active director be to the player?
   - chosen once at mode start
   - visible and changeable in settings
   - partially visible through advisor-style messaging only
3. What knobs should the director be allowed to adjust?
   - Market prices
   - Maintenance costs
   - Random events
   - Contract opportunities
   - Breeding odds
   - Tutorial/intervention hints
4. Should the director ever allow fish death in order to preserve realism for
   expert players, or should it always bias toward softer failure states?

## UI and presentation

1. How stylized should the interface be?
   - soft life-sim / cozy game inspired
   - aquarium-themed but still fairly minimal
   - highly decorative and playful
   - hybrid: playful shell with simplified panels
2. Resolved: the default career tank view should use **compact owner gauges plus
   warnings** rather than a dense management HUD.
3. In observer mode, how minimal should the visible HUD be?
   - almost none, just tank and social actions
   - light tank identity and species info
   - optional overlay toggles for viewers

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
6. Resolved: guest sandbox day one should expose three templates:
   - betta display,
   - tropical community,
   - planted showcase

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
