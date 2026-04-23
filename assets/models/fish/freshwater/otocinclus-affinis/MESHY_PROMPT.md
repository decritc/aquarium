## Meshy Prompt: Otocinclus affinis

### Asset intent
- Create a small, charming algae-grazer freshwater fish for tropical planted tanks.
- The style target is **cartoon realism**: believable fish anatomy with simplified,
  clean silhouettes, appealing proportions, bright readable coloration, and premium
  shading suitable for a polished browser game.

### Visual direction
- Small slender body, sucker-mouth algae eater profile.
- Recognizable Otocinclus silhouette with a compact body and horizontal stripe.
- Friendly, non-threatening appearance.
- Tropical planted-tank fit: natural earthy tones with crisp darker stripe and pale belly.

### Required look and feel
- Premium browser-game quality, not photorealism.
- Bright readable materials and clean form separation.
- Consistent with:
  - betta-splendens
  - guppy
  - neon-tetra
  - corydoras-panda
- Avoid muddy textures, over-detailed scales, noisy normals, or horror-real fish eyes.

### Color guidance
- Olive-brown upper body
- Clear dark lateral stripe
- Soft pale underside
- Slight warm gold or green tint acceptable

### Modeling requirements
- Low-to-mid poly optimized for browser delivery.
- Clean silhouette from side-view distance.
- Single fish model, centered and cleanly riggable.
- Fins should be readable but not fragile or ultra-thin.
- Keep topology friendly for animation.

### Animation requirements
- Required clips:
  1. `Swim_Cruise`
     - looping
     - gentle forward cruise with subtle body wave
  2. `Turn_Left`
     - short transition clip
     - smooth banking turn
  3. `Turn_Right`
     - short transition clip
     - smooth banking turn
- Strongly preferred:
  4. `Graze_Surface`
     - algae-grazing / suction behavior against surface or glass
  5. `Rest_Hover`
     - calm cling/hover state

### Rendering expectations
- Side-view gameplay must read immediately.
- The fish should still look good when slightly angled in a 3D tank.
- Materials should support soft specular highlights without looking wet-plastic.
- Keep the fish readable in planted tanks with darker backgrounds.

### Behavioral fit
- This fish will be used as an algae-grazer / cleanup-support species.
- Its shape should visually imply:
  - peaceful temperament
  - surface and hardscape interaction
  - utility/support role rather than showpiece aggression

### Technical delivery targets
- Deliver as runtime-friendly `model.glb`.
- Include rig and exported animation clips if possible.
- Keep material count low.
- Use texture sizes appropriate for web use.

### Avoid
- Hyperreal catfish textures
- Spiky fins
- Bulky body proportions
- Overly dark unreadable coloration
- Stylization that clashes with the rest of the starter fish set
