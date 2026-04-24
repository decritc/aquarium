## Asset

- Type: fish
- Species: Guppy
- Scientific name: Poecilia reticulata
- Folder: `assets/models/fish/freshwater/guppy/`
- Target runtime file: `model.glb`

## Goal

Create a stylized-realistic 3D guppy for a premium browser aquarium game. The fish
should feel lively, bright, and beautiful with a **cartoon realism** look:

- grounded fish anatomy
- elegant but slightly simplified body forms
- richer color separation than strict realism
- clean, readable silhouette from a side-view gameplay camera
- premium shading and material breakup without looking gritty or hyper-real

This fish will be used in:

- guest sandbox
- community tanks
- breeder/career tanks
- side-view aquarium gameplay

## Visual style direction

Match the shared visual language in `assets/models/MESHY_STYLE_GUIDE.md`.

Specific guppy traits:

- small tropical freshwater livebearer
- slim body
- relatively large decorative tail and dorsal fin
- lively, energetic, attractive coloration
- bright but tasteful palette
- readable patterning

Preferred look:

- a refined male-show guppy style first
- colorful tail with clear pattern contrast
- side-view silhouette must read instantly as “guppy”

Avoid:

- muddy coloration
- hyper-detailed scales that disappear in gameplay
- physically inaccurate giant fantasy fins
- dark horror-fish look
- washed-out gray materials

## Shape and silhouette requirements

- slim body with slight curve and buoyant posture
- elegant flowing tail that reads well from the side
- fins should feel decorative but not too thin to survive web rendering
- silhouette should still be readable at small on-screen sizes

The fish should look good:

- from the side-view gameplay camera
- in small group/community scenes
- as a thumbnail or species card render

## Materials and shading

Desired finish:

- clean stylized-realistic skin shading
- gentle color gradients
- slightly pearlescent or luminous tropical-fish feel
- tail material can have subtle translucency impression without requiring expensive runtime transparency

Keep materials browser-friendly:

- low material count
- avoid overcomplicated shaders
- avoid tiny noisy texture detail

## Animation requirements

The exported asset should support these named animation clips if Meshy can provide
them, or at least be authored toward them.

Required:

1. `Swim_Idle`
   - default cruising motion
   - continuous relaxed forward swimming
   - gentle tail wave
   - slight body flex

2. `Swim_Turn_Left`
   - short left-turn transition
   - body arcs smoothly
   - tail and fins respond naturally

3. `Swim_Turn_Right`
   - short right-turn transition
   - same quality as left turn

Preferred:

4. `Feed`
   - brief pecking or nibbling motion

5. `Courtship`
   - subtle display motion with extra fin emphasis

Animation notes:

- no jerky motion
- no robotic pivot turning
- preserve soft tropical-fish movement
- movement should blend well in a browser renderer

## Rendering / gameplay hints

This fish will usually be rendered:

- in the upper to mid water zone
- in peaceful community scenes
- with other small fish nearby
- in side-view motion loops and schools

Design the asset so it supports:

- clean silhouette at gameplay distance
- smooth perceived motion
- visible color variety for breeding or variant expansion later

## Output request

Please generate:

- one optimized stylized-realistic guppy model
- rigged and ready for animation export if possible
- exported as GLB-friendly asset
- suitable for bright, premium aquarium lighting

If multiple color directions are possible, prefer:

- turquoise / orange / yellow tail accents
- readable but elegant tropical coloration
- premium, cheerful, visually rich result
