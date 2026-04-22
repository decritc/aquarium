# Open Questions

This file tracks product decisions to resolve before implementation becomes deep or
costly to change.

## Product direction

1. Is the primary fantasy closer to:
   - a relaxing aquarium creator,
   - a fish genetics and breeding sim,
   - a tycoon/economy game,
   - or a social showcase game?
2. Should players manage a single flagship aquarium first, or unlock multiple tanks
   early?
3. Should observer mode be passive only, or include likes, follows, comments, or
   curated featured tanks?

## Progression and economy

1. How punishing should incompatible fish care be in breeder mode?
2. Should fish die permanently from neglect, or should the game prefer softer
   consequences such as sickness, fertility loss, or lower value?
3. What is the desired balance between:
   - decoration and creativity,
   - fish breeding strategy,
   - and financial optimization?
4. How strong should the premium acceleration loop be relative to the idle baseline?

## Fish design depth

1. How realistic should species behavior and care requirements be?
2. Should breeding use:
   - simple trait rarity tables,
   - authored pattern inheritance rules,
   - or a more simulation-heavy genetics system?
3. Should hybridization across closely related fish be possible?
4. Will fish have named lineages and pedigrees visible to players?

## Social and content scope

1. Are aquariums public by default, private by default, or player-selectable?
2. Should public aquariums be searchable by tags, fish species, rating, or owner?
3. Will we eventually support seasonal events, daily shop rotations, or community
   competitions?

## Technical decisions

1. Do you want us to target desktop web first, or responsive mobile web from the
   beginning?
2. Are you open to a TypeScript monorepo with:
   - a React-based client,
   - a lightweight API/backend,
   - and shared simulation/content packages?
3. Should the simulation continue progressing while the player is offline, and if
   so, how exact should offline catch-up be?
4. Will fish models arrive in glTF/GLB format, or do you expect a different 3D
   format?
