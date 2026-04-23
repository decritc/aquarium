# Marketing Site Specification

This document defines the first implementation spec for the public-facing landing
site and SEO-critical pages of the project.

It translates the high-level landing page strategy into a practical build target
for future implementation agents.

## Site goals

- Present the game as a premium, polished browser game
- Convert visitors into sandbox users first
- Support search discovery through indexable content
- Showcase visual quality without hurting page performance
- Establish trust through real product visuals and strong information architecture

## Core promise

### Primary promise

**Create a beautiful living aquarium in your browser**

### Supporting promise

Design cozy tanks, breed rare fish, and explore player-made aquariums in a
relaxing simulation built for the web.

## Primary conversion goal

### Primary CTA

`Start Free Sandbox`

### Secondary CTA

`Watch Public Aquariums`

For the first implementation, this CTA should open a **single featured aquarium
experience** rather than a full browse grid. That keeps the landing-page flow
premium and focused while the broader observer/discovery system is still being
built.

That featured aquarium should be a **handcrafted studio/demo tank**, not a live
player tank. This guarantees:

- premium art direction
- consistent quality for screenshots and trailers
- no dependency on account/public-tank systems
- a reliable observer destination from day one

## Site map for first implementation

The first implementation should support at least these public pages:

1. `/` - homepage / landing page
2. `/sandbox` - sandbox overview page
3. `/career` - breeder/career overview page
4. `/observe` - featured aquarium / observer mode overview page
5. `/faq` - FAQ/discoverability page

Optional early pages if capacity allows:

6. `/about`
7. `/updates`

## Homepage structure

## 1. Hero

Purpose:

- establish trust immediately
- communicate the promise in under 5 seconds
- drive the sandbox CTA

Required contents:

- H1 with the primary promise
- short benefit-led subheadline
- primary CTA: `Start Free Sandbox`
- secondary CTA: `Watch Public Aquariums`
- hero visual built as a lightweight cinematic motion loop from real assets or
  polished in-engine capture

Hero visual requirements:

- real tank scene or composited scene from real assets
- visible layered tank depth
- visible fish motion or motion implication
- premium art direction
- no placeholder visual treatment

Preferred mood for the first implementation:

- calm premium planted beauty
- elegant planted composition before dramatic spectacle
- soothing, high-trust, premium aquarium atmosphere
- visually rich but not chaotic

Preferred framing:

- show enough of the full tank to sell the aquarium fantasy
- keep the betta clearly readable as the focal point
- avoid compositions that become only a fish portrait or only an environment shot

Preferred hero-fish direction for the first implementation:

- lead with a **betta** as the primary visual hero
- use the fish as the focal point inside a calm planted composition
- avoid making the first hero rely on a busy school or multi-species chaos

Preferred first implementation format:

- a lightweight cinematic motion loop
- short, art-directed, and highly compressed
- able to fall back gracefully to a poster image
- not a heavy interactive 3D hero as the default landing treatment

## 2. Modes section

Show three mode cards:

- Sandbox
- Career
- Observer

Each card should include:

- what the mode feels like
- who it is for
- a short concrete benefit

## 3. Visual proof section

Purpose:

- prove the game looks premium
- reassure visitors this is a real polished product

Required contents:

- 3-6 strong screenshots or polished renders
- optional short motion loops or light video
- examples of different tank moods or archetypes

For the first implementation, at least one of the strongest showcase assets should
lean into the calm premium planted-beauty mood so the site establishes a relaxing,
high-quality identity immediately.

## 4. Feature pillars section

Recommended pillars:

- Build beautiful tanks
- Breed rare fish
- Relax and watch living aquariums
- Visit player-made showcases
- Play instantly in your browser

## 5. Trust / proof section

First implementation can use:

- one featured observable aquarium and its supporting showcase framing
- “coming soon” founder/devlog proof
- process or craft-oriented messaging

Do not fabricate:

- fake testimonials
- fake review badges
- fake player counts

## 6. FAQ section

Must include at least:

- What kind of game is this?
- Is it playable in the browser?
- Can I start for free?
- Is there a sandbox mode?
- Can I visit other players’ aquariums?
- Do I need an account?

## 7. Footer

Must include:

- gameplay links
- privacy / terms placeholders if needed
- contact or updates link when available

## Homepage copy requirements

The homepage should:

- explain what the game is clearly
- sound premium and human-written
- avoid cliché hype language
- use emotionally clear, scan-friendly copy

The homepage should not:

- feel like a template
- feel keyword stuffed
- make unsupported claims
- rely on vague buzzwords

## Visual standards

All above-the-fold and showcase visuals should come from:

- approved founder-provided media
- in-engine renders
- polished gameplay captures
- approved concept art

Avoid:

- random generated filler
- inconsistent art direction
- low-resolution composites
- visual styles that do not match the intended game

## Performance constraints

The landing page must feel premium **and** load quickly.

Requirements:

- fast first paint
- optimized hero media
- lazy-loaded below-the-fold images/video
- no blocking heavy 3D scene in the hero unless proven performant
- high Core Web Vitals priority

Recommended implementation:

- static generation or SSR
- responsive image loading
- poster-first media strategy
- progressive enhancement for motion content

## SEO requirements

Every public page in the first site should include:

- unique title
- unique meta description
- one clear H1
- structured heading hierarchy
- canonical URL
- Open Graph metadata

Site-level requirements:

- sitemap
- robots.txt
- clean semantic HTML
- crawlable content without heavy client-only dependency

## Structured data

Recommended first implementation:

- `VideoGame` on core landing pages if content is truthful
- `FAQPage` on FAQ page
- `BreadcrumbList` on secondary mode pages if useful

## Analytics expectations

Track at minimum:

- homepage CTA clicks
- sandbox CTA clicks
- observer CTA clicks
- scroll depth on homepage
- page load metrics

## First implementation acceptance criteria

The marketing site is successful for the first milestone if it includes:

- a polished homepage
- the primary CTA `Start Free Sandbox`
- the secondary CTA `Watch Public Aquariums` leading to a strong featured-aquarium destination
- distinct sections for the three play styles
- real or approved premium visuals
- fast, crawlable public pages
- clear information hierarchy

## Implementation guidance for future agents

- Treat the homepage like a premium product launch page, not a placeholder.
- Default the conversion path toward guest sandbox.
- Use real proof of product quality instead of filler.
- Optimize landing assets as carefully as gameplay assets.
- Build public pages with SEO and load speed in mind from the start.
