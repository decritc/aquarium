# Meshy Prompt - Panda Corydoras

## Asset ID

- `corydoras-panda`
- Species definition: `corydoras-panda`

## Prompt

Create a stylized-but-believable **Panda Corydoras** aquarium fish for a premium
browser aquarium game. The art direction is **cartoon realism**:

- grounded in real fish anatomy
- clean simplified forms
- bright readable colors
- premium materials and shading
- soft appealing silhouette
- designed to look excellent in a side-view aquarium with 3D depth

The fish should read instantly as a panda cory catfish:

- small armored catfish body
- rounded head
- downturned mouth and barbels
- panda-style black eye patch
- black markings on dorsal and tail region
- pale silver-cream body
- gentle bottom-dweller silhouette

Style requirements:

- no grotesque realism
- no hyper-detailed scales
- no muddy texture noise
- no horror-fish look
- no low-poly toy look
- keep it premium, soft, and clean

Rendering goals:

- side-view readability at gameplay distance
- looks attractive under soft aquarium lighting
- simple enough for web performance
- materials should support subtle shading and a healthy fish sheen

Pose the base mesh in a neutral swimming pose that supports animation rigging.

## Animation requirements

Generate/prepare the asset so it can support these animation clips:

1. `Swim_Cruise`
   - primary looping swim
   - gentle bottom-dweller cruising
   - subtle fin and tail motion

2. `Swim_Turn_Left`
   - short banking turn
   - should feel smooth and weighted

3. `Swim_Turn_Right`
   - mirrored smooth banking turn

Strongly preferred additional clips:

4. `Forage_Bottom`
   - slow substrate-search behavior
   - head-down pecking or nosing motion

5. `Rest_Hover`
   - quiet low-energy hover near the tank floor

Animation style:

- soft and natural
- calm, not frantic
- suitable for a peaceful bottom-dwelling cleanup fish

## Model constraints

- optimized for browser delivery
- modest geometry count
- clean topology for deformation
- minimal material count
- avoid tiny geometry details that disappear at gameplay distance

## Output requirements

Please produce:

- one runtime-ready `model.glb`
- one preview render/image
- rigged fish suitable for the listed animations
- textures/materials that preserve the panda markings clearly

## Notes for consistency

This asset must match the shared style guide in:

- `/workspace/assets/models/MESHY_STYLE_GUIDE.md`

It should feel like it belongs in the same world as:

- betta
- guppy
- neon tetra

All fish should share:

- premium cartoon-real shading
- consistent lighting response
- readable silhouette design
- a calm, polished browser-game look
