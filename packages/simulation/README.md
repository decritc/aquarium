# packages/simulation

This package will eventually contain the core aquarium simulation logic.

Planned responsibilities:

- Tank environmental simulation
- Fish behavior state machines
- Growth, hunger, health, and breeding logic
- Time-step processing for active and idle play
- Deterministic calculations shared between client and server where useful

Design goals:

- Keep simulation rules data-driven where possible
- Separate rendering concerns from gameplay rules
- Make progression and monetization modifiers explicit rather than hardcoded
