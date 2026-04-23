# Browser Performance and Rendering Strategy

This document defines the expected performance and rendering quality bar for the
virtual aquarium game in the browser.

The goal is not merely to "work in web." The goal is to feel like a premium web
game experience with smooth fish motion, fast loading, and high visual quality.

## Performance philosophy

Performance is a first-class product feature.

The game should feel:

- smooth
- responsive
- premium
- intentional

It should not feel like:

- a heavy tech demo
- a stuttering 3D experiment
- a low-budget browser prototype

The founder explicitly wants a high-quality browser experience comparable in
intent to polished web-based online games, not a compromised "it runs in a tab"
experience.

## Core rendering goals

### 1. Smooth fish motion

Fish must swim continuously and smoothly through the tank.

Avoid:

- visible teleporting between positions
- jerky steering
- low-frequency updates that make fish appear to skip
- abrupt animation-state changes without blending

Required qualities:

- frame-to-frame interpolation
- smooth turning arcs
- animation blending between cruise, turn, idle, chase, and schooling states
- stable update timing

### 2. Stable frame pacing

The experience should prioritize frame stability over excessive visual effects.

Important principle:

- a stable, smooth frame rate is better than a visually richer but inconsistent one

### 3. Fast startup and scene readiness

The landing page and the first playable aquarium should load quickly enough to
feel premium, not sluggish.

This means:

- careful code-splitting
- lightweight first route payloads
- deferred loading of non-critical 3D assets
- progressive scene hydration where appropriate

## Browser-first rendering constraints

This game runs in a web browser, so the renderer should be built around that
reality from the start.

The implementation must assume:

- variable GPU quality
- different browser engine behaviors
- fluctuating tab focus and throttling
- network latency and asset download cost
- public pages that may receive casual traffic on weaker devices

## Rendering quality guidelines

### Fish rendering

Fish should appear premium while remaining efficient.

Guidelines:

- prefer optimized GLB assets
- keep skeletons and material complexity under control
- support LOD or simplified mesh/material fallback if fish count grows
- minimize overdraw and expensive transparency where avoidable

### Scene effects

Visual effects should be chosen for impact-to-cost ratio.

Good candidates:

- subtle caustics
- light parallax
- restrained post-processing
- soft particle accents

Use sparingly:

- expensive screen-space effects
- layered transparency stacks
- heavy dynamic shadows on all objects
- per-object high-cost shaders without clear benefit

### Public/observer pages

Public aquarium viewing must be especially efficient.

Observer mode should:

- prioritize stable playback over heavy owner tools
- reduce management HUD cost
- support reduced-detail fallbacks when necessary
- avoid unnecessary simulation detail if read-only viewing is sufficient

## Movement and simulation quality

### Smooth pathing

Fish motion should use authored steering and interpolation rather than hopping
between waypoints.

Practical guidelines:

- sample targets at a sufficient frequency
- interpolate movement between simulation ticks
- decouple visual smoothing from coarse gameplay state updates
- allow curved motion and turn anticipation

### Simulation/render separation

The simulation should define intent.
The renderer should define smooth presentation.

Examples:

- simulation says a fish is cruising toward a zone
- renderer interpolates the path smoothly
- simulation says a fish is stressed and scattering
- renderer blends into faster movement and turn states

This separation is essential for browser smoothness.

## Technical optimization strategy

### 1. Measure first

Future implementation agents should profile real performance rather than guessing.

Track:

- frame time
- frame pacing variance
- initial route load time
- aquarium scene ready time
- JS main-thread cost
- GPU draw pressure
- memory use in long sessions

### 2. Optimize the expensive layers first

The likely early hotspots are:

- fish update loops
- animation blending
- draw calls
- transparent materials
- lighting/post-processing
- large public aquarium scenes

### 3. Scale gracefully

The renderer should support quality scaling instead of a single hard target.

Potential levers:

- fish count caps by mode
- lower effect quality
- shadow reduction
- animation update frequency tiers
- LOD or simplified materials
- reduced background animation on low-end devices

## Delivery and loading strategy

### Landing page

The landing page should be visually impressive but still fast.

Recommendations:

- SSR or statically generated shell for strong first paint and SEO
- hero media optimized aggressively
- prefer a lightweight cinematic motion loop for the first hero treatment rather than
  a static-only hero or a heavy interactive real-time 3D scene
- responsive image strategy
- avoid blocking the initial render on heavy interactive 3D content

### Game routes

Recommendations:

- lazy-load aquarium-heavy code paths
- stream or progressively load assets where possible
- cache content definitions aggressively
- reuse animation/material resources across similar fish where possible

## Asset budget discipline

Future agents should treat asset budgets as part of the product design.

Each fish or decorative item should be authored with awareness of:

- geometry budget
- texture budget
- material count
- skeleton/animation cost
- expected frequency of use

Do not assume "browser can handle it later."

## Quality targets by experience

### Landing / marketing pages

Priority order:

1. fast initial impression
2. premium visual quality
3. SEO/readability
4. restrained interactivity

### Sandbox / owner tank view

Priority order:

1. smooth fish motion
2. responsive editing interactions
3. stable frame pacing
4. attractive but controlled effects

### Observer mode

Priority order:

1. unobstructed viewing
2. stable performance across devices
3. smooth ambient motion
4. clean presentation and social discoverability

## Anti-slop standards

Future implementation agents should actively avoid:

- generic AI-generated landing-page copy
- low-effort placeholder visual treatments presented as final direction
- unnecessary motion gimmicks that hurt readability
- overbuilt but underperforming visual stacks
- "looks fancy in screenshots, feels bad in browser" outcomes

The quality bar should feel intentional, art-directed, and product-grade.

## Recommended early implementation priorities

If tradeoffs are necessary, prioritize:

1. smooth fish motion
2. stable frame pacing
3. fast landing page and route readiness
4. polished restrained visual effects
5. deeper rendering complexity later

## Implementation guidance for future agents

- Treat browser performance as a product requirement, not a later optimization pass.
- Separate simulation intent from visual interpolation.
- Build for graceful degradation, not one fixed hardware target.
- Favor premium restraint over overloaded effects.
- Measure with real profiling before moving hotspots to WASM or lower-level runtimes.
