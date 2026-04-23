# Founder Decisions

This document captures the current design direction based on the founder's answers
to the initial product questionnaire. Future agents should treat these as the
default assumptions unless a later document supersedes them.

## Resolved decisions

### 1. Primary fantasy is mode-dependent

The game supports multiple player fantasies, and the dominant fantasy changes by
mode:

- **Sandbox mode** emphasizes relaxing aquarium creation
- **Observer mode** emphasizes social showcase and discovery
- **Career mode** emphasizes breeding strategy and tycoon progression

This means design, UX, progression, and monetization should all be mode-aware.

### 2. Tank ownership is mode-dependent

- **Guest sandbox without an account**: one aquarium with a curated asset set
- **Paid upgrade path for sandbox users**: more assets and more tanks
- **Career mode**: multiple aquariums are allowed, but the main constraint is
  limited capital rather than a hard one-tank cap

Players should be able to choose whether to invest in beautiful showcase tanks or
run a lean breeder-focused setup.

### 3. Observer mode should include social actions

The intended social feature set includes:

- viewing public aquariums
- likes/favorites
- follows
- comments
- curated/featured showcases

### 4. Difficulty should be adaptive

The game should use an **AI director** or adaptive challenge layer that tries to
keep the experience fun, challenging, and recoverable.

Design intent:

- casual players should not be driven into frustrating failure states
- experienced breeders should still feel meaningful realism and challenge
- the system should adapt to player skill and play style over time

### 5. Neglect consequences should follow the adaptive challenge model

Fish care penalties should be governed by the same adaptive philosophy as the
director system rather than a fixed global punishment rule.

Implication:

- the game should avoid making players go broke or lose everything too easily
- consequence severity may vary by context, tank condition, player behavior, or
  future difficulty settings

### 6. Core balance is also play-style dependent

The game should support multiple player archetypes:

- creative decorators and showcase players
- strategy-heavy breeders
- economy-minded optimizers
- social/community-oriented players

The default target is a balanced mix, but systems should not assume every player
has the same motivation.

### 7. Premium acceleration should stay light

Monetization should be conservative and sustainable:

- primary monetization should center on cosmetics, ad removal, and convenience
- optional purchases of in-game money are acceptable for career progression
- pricing should account for infrastructure and database/storage costs
- the business model should be able to scale sustainably if the game grows

### 8. Species realism target

Fish behavior and care requirements should be **semi-realistic**:

- grounded in real aquarium logic
- simplified enough to remain readable and fun

### 9. Breeding depth plan

Breeding should **start simple and expand later**.

Recommended rollout:

1. readable inheritance and trait pools
2. stronger authored rules and lineages
3. deeper simulation only after the basics are fun

### 10. Hybridization rules

Hybridization should generally stay realistic:

- allow many closely related species where appropriate
- stick close to realism by default
- include a few curated exceptions and discoverable easter egg fish

### 11. Pedigree visibility

Fish should have full lineages/pedigrees available for deep-dive players, but
pedigree should not dominate the default UI flow.

Design implication:

- surface simple lineage information in normal play
- provide an easy-to-find advanced pedigree view for collectors and breeders

### 12. Public visibility defaults

Aquariums should be **private by default**.

Players may explicitly choose to share tanks through the UI.

### 13. Public aquarium discovery

Public tanks should be discoverable through:

- owner search
- tags/themes
- fish species
- popularity/featured ranking

### 14. Live content direction

For now, plan for **seasonal decorations only** rather than a heavy live-ops
calendar.

### 15. Platform priority

The project should target **desktop web first**.

### 16. Technical architecture preference

The project should use a **TypeScript monorepo**, but the architecture should not
assume every performance-sensitive system remains in TypeScript forever.

Notes:

- frontend rendering may eventually use WASM for hotspots
- backend services may later move some workloads to faster runtimes if necessary

### 17. Offline progression

Offline progression should use a **hybrid model**:

- simplified catch-up while offline
- more detailed simulation only for the most important systems

### 18. Fish asset format

Fish models are expected to arrive primarily as **GLB** assets.

The current likely modeling workflow involves **Meshy AI** as an upstream asset
source.

### 19. UI tone should be playful and cozy

The interface should feel closer to a friendly life-sim UI than a technical
operations dashboard.

Design intent:

- rounded, readable, welcoming shapes
- playful but polished visual treatment
- calm color language that supports long passive viewing sessions
- avoid heavy enterprise-style control panels as the default presentation

The target mood is relaxing, comfortable, and "good vibes" forward rather than
high-stress management first.

### 20. Players should choose their AI director style

The adaptive challenge system should not be a single invisible difficulty layer.
Players should be able to choose a director/profile much like a storyteller
system in colony sims.

Implication:

- relaxed players can choose a laid-back, beauty-first, low-stress experience
- career-minded players can choose a balanced progression experience
- extreme players can choose a more demanding, challenge-heavy profile

### 21. Observer presentation must be low-obstruction

Observer mode should prioritize tank viewing over management surfaces.

Implication:

- owner-only gauges and tools should not appear in observer mode
- public viewers should not see career-management overlays such as pH gauges,
  water temperature tools, or private fish-care diagnostics
- observer mode should feel suitable for passive ambient watching or
  "screensaver-like" viewing

### 22. Career tools are owner-facing, not audience-facing

Career mode may expose management aids to the player, including:

- pH and temperature indicators
- observable fish health summaries
- compatibility warnings
- maintenance and breeding guidance

Those tools exist for the owner/operator of the tank and should be hidden or
significantly reduced when the same tank is viewed publicly.

## Key implementation implications

1. Build the product around distinct mode entry points rather than one unified
   progression path.
2. Keep fish and content data-driven so new species can be added by dropping in
   a model and metadata JSON.
3. Treat adaptive difficulty as a first-class system rather than a late tuning
   pass.
4. Treat director/profile selection as part of the player-facing UX rather than
   a hidden tuning detail.
5. Design social systems with moderation, privacy, and observer-safe
   presentation from the beginning.
6. Keep the premium model sustainable without making the experience feel paywalled.
