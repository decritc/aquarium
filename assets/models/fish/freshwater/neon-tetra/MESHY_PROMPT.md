# Meshy prompt: Neon tetra

## Asset goal

Create a premium, stylized-realistic 3D **neon tetra** for a browser-based virtual
aquarium game.

The fish should feel:

- bright
- colorful
- elegant
- small and fast
- readable from a side-view camera

It should match the same **cartoon realism** family as the betta and guppy:

- simplified forms
- believable anatomy
- saturated but tasteful colors
- clean silhouette
- polished shading
- no gritty realism
- no exaggerated toy proportions

Read `/workspace/assets/models/MESHY_STYLE_GUIDE.md` first and match that style.

## Visual design

Model a **small tropical schooling tetra** with:

- slim torpedo body
- small translucent fins
- streamlined silhouette
- strong side profile readability

Color requirements:

- vivid electric blue lateral stripe
- bright red lower rear body section
- subtle silvery base body tone
- delicate transparent fins with slight tint

Keep the colors punchy and clean, but not neon-sign fake. The fish should look
beautiful in a premium stylized aquarium, not like a flat mobile-game icon.

## Geometry and material expectations

- clean game-ready mesh
- low to moderate mesh density suitable for browser rendering
- avoid tiny micro-detail that disappears in gameplay
- preserve the side silhouette of the stripe and body shape
- keep fins readable but not paper-thin and noisy
- use as few materials as practical

## Rigging and animation expectations

The fish should be rigged and suitable for these clips:

### Required

1. `Swim_Idle`
   - default cruising swim
   - small rhythmic body wave
   - smooth, continuous motion
   - loops cleanly

2. `Swim_Turn_Left`
   - short directional banking/turning motion
   - body bends naturally
   - not an aggressive dart

3. `Swim_Turn_Right`
   - mirrored right-turn version

### Preferred

4. `Schooling_Tighten`
   - slightly tighter, more alert swim style
   - usable when the school is stressed or clustering

5. `Feed_Peck`
   - short pecking or dart-to-food motion

## Motion style

This species is for community tanks and schooling visuals.

Animation should suggest:

- active but graceful motion
- tighter, more synchronized group behavior
- quick but not twitchy turns
- no visible stutter or snapping

## Rendering notes

The fish will mostly be viewed:

- from the side
- at small on-screen size
- in groups

So optimize for:

- stripe readability
- group silhouette clarity
- motion smoothness
- clean color separation

## Output expectations

Please generate:

- one rigged 3D runtime model
- one set of clean looping animation clips
- polished stylized shading
- a game-ready result appropriate for export to GLB

## Avoid

- realistic muddy scales
- overly reflective chrome-like materials
- giant anime eyes
- toy/chibi proportions
- noisy fin detail
- horror-real fish textures
- overbuilt geometry that will hurt browser performance
