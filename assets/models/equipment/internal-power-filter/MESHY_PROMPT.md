# Meshy Prompt - Internal Power Filter

## Asset ID

`internal-power-filter`

## Purpose

Stronger community/planted-tank filter that mounts to the back or side glass. This
is a visible piece of equipment in owner/editor views, so it needs to read clearly
without looking ugly or hyper-industrial.

## Visual style target

- Cartoon realism
- Clean and premium aquarium product styling
- Friendly silhouette, not harsh industrial machinery
- Believable materials and shading
- Designed to sit in a polished browser game scene

## Core generation prompt

Create a stylized-realistic **internal aquarium power filter** for a freshwater
tank. The model should be compact, clean, and modern, designed for a cozy premium
aquarium simulation. It should mount on the rear or side interior glass of the
tank. Use smooth molded plastic shapes, believable seams, intake/outflow features,
and subtle detail, but avoid excessive realism or tiny mechanical clutter.

The look should match a **cartoon realism** style: simplified silhouette, premium
materials, clean shading, and readable at gameplay distance. This should feel like
a thoughtfully designed aquarium accessory from a polished game world, not a harsh
industrial prop. Use dark neutral body materials with subtle contrast and a clean
finish.

The model should read clearly from the aquarium's **side-view presentation** and
also look good in the editor's orbit and side-inspection views. Keep the silhouette
distinct from the sponge filter so players can tell immediately that this is a
stronger, more modern filtration option.

## Rendering requirements

- Designed primarily for side-view readability
- Strong silhouette from side angle
- Should still read clearly from orbit/editor views
- Browser-friendly detail level
- Avoid thin fragile pieces that may break in generation

## Geometry and material notes

- One compact body
- Clear intake area
- Clear output lip/nozzle
- Mounting bracket or clip shape
- Smooth rounded-corner housing
- Keep mesh efficient and clean
- Avoid over-detailed grilles or tiny unreadable buttons

## Animation requirement

No skeletal animation required.

Optional separate loop references for engine-side effects only:

- subtle water outflow particle area
- subtle intake bubble cue area

Those do not need to be modeled as animation, but the shape should suggest where
those effects would originate.

## Meshy negative guidance

Avoid:

- photoreal industrial equipment
- extreme greeble detail
- military or sci-fi styling
- chunky toy proportions
- transparent hoses
- unnecessary cords if they make the silhouette messy
- dirty or damaged materials

## Metadata notes for later JSON

- Category: equipment
- Placement behavior: mounted
- Best for: community tank, planted tank
- Visual tags: clean, modern, mounted, low-clutter

