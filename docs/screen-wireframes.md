# Screen Wireframes

This document provides low-fidelity screen structure guidance for the first
implementation. These are not visual comps. They are screen-planning documents so
future agents can scaffold pages and major UI zones without inventing the IA.

## Wireframe conventions

- `[header]` top navigation or hero framing
- `[panel]` grouped UI region
- `[viewport]` main aquarium or media area
- `[cta]` primary action
- `[meta]` supporting information

## 1. Public landing page

```text
[header]
  logo | explore | sign in

[hero]
  [headline] Create a beautiful living aquarium in your browser
  [subheadline] Design cozy tanks, breed rare fish, and explore player-made aquariums.
  [cta primary] Start Free Sandbox
  [cta secondary] Watch Public Aquariums
  [hero media] premium aquarium visual / loop / screenshot

[modes section]
  [card] Sandbox
  [card] Career
  [card] Observer

[showcase section]
  [media grid] curated tank images / loops

[features section]
  build | breed | showcase | browser play

[faq section]
  browser? sandbox? accounts? public tanks?

[footer]
  terms | privacy | updates | social
```

## 2. Mode selection screen

```text
[header]
  logo | back | account

[intro panel]
  [title] Choose how you want to play
  [meta] switch anytime later where allowed

[mode cards row]
  [card] Sandbox
    description
    [cta] Start sandbox

  [card] Career
    description
    [cta] Start career

  [card] Observer
    description
    [cta] Explore aquariums
```

## 3. Director selection screen

```text
[header]
  back | title | continue

[intro panel]
  [title] Choose your aquarium director
  [meta] this changes how much pressure and guidance the game applies

[director cards]
  [card] Cozy / Good Vibes
    low-pressure
    zen-friendly

  [card] Balanced
    standard pacing
    moderate challenge

  [card] Hardcore Breeder
    stronger pressure
    more demanding simulation

[footer action]
  [cta] Continue
```

## 4. Guest sandbox aquarium screen

```text
[top bar]
  logo | sandbox label | tank name | share | account prompt

[main content]
  [viewport]
    side-view aquarium
    minimal chrome

  [right rail tabs]
    overview
    fish
    items
    backdrop
    substrate

[bottom action row]
  [cta] Edit tank
  [cta] Fish library
  [cta] Decor library
  [cta] Presentation mode
```

## 5. Career aquarium screen

```text
[top bar]
  logo | career label | tank switcher | credits | shop

[main content]
  [viewport]
    side-view aquarium
    owner-only gauges in light chrome

  [owner HUD strip]
    habitat match
    cleanliness
    fish comfort
    breeding confidence

  [right rail tabs]
    overview
    fish
    breeding
    environment
    warnings
    items

[bottom action row]
  feed | clean | edit tank | shop | sell fish
```

## 6. Observer tank screen

```text
[top bar]
  logo | explore | search | profile

[main content]
  [viewport]
    side-view aquarium
    minimal unobtrusive chrome

  [light info card]
    tank title
    owner
    species summary
    theme tags

[bottom social strip]
  like | follow | comment | visit creator
```

Important rule:

- no owner gauges
- no pH/temperature HUD
- no fish-care diagnostics
- no business/economy chrome

## 7. Tank editor screen

```text
[top bar]
  back to tank | save | cancel | preview

[left panel]
  category list
  search
  favorites

[center editor viewport]
  free rotation camera
  snap view buttons
  placement ghost
  overlays

[right panel]
  selected item details
  placement hints
  impact summary

[bottom utility bar]
  undo | redo | side preview | top view | side view | orbit
```

## 8. Featured aquarium page

```text
[header]
  logo | explore | account

[hero strip]
  featured aquarium
  featured label

[main content]
  [viewport]
    side-view aquarium
    minimal observer chrome

[light info card]
  tank title
  owner
  species summary
  theme tags

[bottom social strip]
  like | follow | comment | visit creator

[footer link]
  explore more aquariums (later)
```

## 9. Marketing site content page template

For sandbox, career, or observer overview pages:

```text
[header]
  logo | play | explore | sign in

[hero]
  mode title
  1-line value prop
  [cta]
  hero media

[benefits section]
  three core reasons to care

[visual proof section]
  screenshots / loops

[faq]
  mode-specific questions
```

## Implementation guidance for future agents

- Keep the first build structurally simple and visually premium.
- Treat owner screens and observer screens as meaningfully different products.
- Use these wireframes as information architecture guides, not pixel-perfect
  design mandates.
- Prefer unobstructed tank viewing whenever a panel is not actively needed.
