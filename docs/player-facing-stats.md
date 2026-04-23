# Player-Facing Stats and Hidden Simulation Model

This document defines which information should be shown directly to players in the
first implementation and which values should remain hidden or abstracted.

The goal is to keep the UI readable, cozy, and non-mechanical while still giving
career-mode players enough information to make meaningful decisions.

## Principles

1. **Show what helps a player decide**
2. **Hide what would turn the game into a dashboard**
3. **Abstract system complexity into friendly labels first**
4. **Keep observer mode far lighter than owner mode**

## Stat visibility by mode

### Sandbox mode

Sandbox should emphasize beauty and experimentation.

Show:

- Tank name
- Species present
- Theme/backdrop/substrate selections
- Light suggestion messages
- Optional compatibility hints

Hide or soften:

- detailed pH gauges
- hardcore maintenance metrics
- business or profitability metrics

### Career owner mode

Career should reveal more management information, but still in a player-friendly
way.

Show:

- habitat match
- cleanliness
- fish comfort
- breeding confidence
- simple owner gauges such as water temperature or pH
- warnings and suggested fixes

Hide by default:

- raw simulation internals
- per-frame movement data
- fully technical chemistry numbers beyond what supports decisions

### Observer mode

Observer mode should be presentation-first.

Show:

- tank name
- owner
- visible species list
- theme/style tags
- social actions

Hide:

- owner gauges
- diagnostics
- breeding info
- maintenance warnings
- profitability

## Recommended player-facing labels

The first version should favor descriptive categories over dense numeric displays.

### 1. Habitat match

Suggested labels:

- Mismatch
- Acceptable
- Ideal

### 2. Cleanliness

Suggested labels:

- Needs care
- Fair
- Clean
- Sparkling

### 3. Fish comfort

Suggested labels:

- Stressed
- Settled
- Thriving

### 4. Breeding confidence

Career mode only.

Suggested labels:

- Unfavorable
- Possible
- Strong

### 5. Tank look

Suggested labels:

- Plain
- Attractive
- Stunning

### 6. Maintenance load

Career mode only.

Suggested labels:

- Light
- Moderate
- Heavy

## Recommended owner gauges

These are allowed in career mode but should remain visually lightweight.

### Water temperature

- small inline gauge or chip
- color-coded safe range indicator

### pH

- simple bar/chip with ideal range highlight
- no laboratory-style UI

### Fish health

Recommended presentation:

- fish card summary
- icon/state wording
- optional tooltip for deeper explanation

Avoid:

- cluttering the main viewport with health bars above every fish by default

## Fish card information

### Basic fish card

Show:

- fish name or generated label
- species
- temperament
- comfort state
- breeding readiness if relevant

Optional:

- color/pattern traits
- lineage shortcut

### Advanced fish detail

Available on click or expanded panel:

- deeper lineage
- trait pools
- compatibility notes
- breeding cooldowns or status

## Tank-level versus fish-level information

Prefer tank-level information for:

- cleanliness
- habitat match
- overall compatibility
- maintenance load

Prefer fish-level information for:

- health state
- breeding readiness
- trait/lineage details
- specific conflict flags

## Observer-safe overlays

Observer mode should allow only very light overlays such as:

- species list drawer
- tank title
- owner attribution
- theme tags

No owner HUD should leak into public viewing by default.

## First playable recommendation

For the first implementation, expose only:

- tank title
- fish species present
- habitat match
- cleanliness
- fish comfort
- owner-only temperature and pH chips in career mode
- owner-only warnings panel

Everything else should remain secondary or hidden until needed.

## Implementation guidance for future agents

- Default to descriptive labels before raw numeric detail.
- Let advanced detail live behind clicks, drawers, or expanded cards.
- Keep the aquarium itself visible and emotionally central.
- Never let owner management HUD dominate observer presentation.
