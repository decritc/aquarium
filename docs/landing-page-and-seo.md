# Landing Page and SEO Strategy

This document defines the quality bar for the marketing site and public landing
experience of the virtual aquarium game.

The landing page is not a secondary detail. It is a core product surface that
must communicate quality, trust, and visual polish immediately.

## Product standard

The landing page should feel like a **premium modern game/product launch page**,
not like placeholder startup marketing or AI-generated filler.

Quality expectations:

- polished, intentional composition
- custom or in-engine visual assets
- sharp copy with a clear point of view
- smooth motion and transitions
- strong typography and layout hierarchy
- zero reliance on generic "AI slop" visuals or vague filler sections

The page should feel closer to a best-in-class premium product launch than to a
quick template site.

## Goals

- Make the game feel credible and high quality immediately
- Convert first-time visitors into sandbox users, observers, or account signups
- Rank well for relevant search queries
- Showcase the game's visual identity without tanking performance
- Create a strong foundation for social sharing, screenshots, trailers, and dev updates

## Brand impression

The first impression should communicate:

- this is a real polished browser game
- it has beautiful aquariums and animated fish
- it supports multiple play styles
- it is relaxing, modern, and high quality

The page should not feel:

- cheap
- auto-generated
- overloaded with jargon
- visually noisy
- dependent on low-value keyword stuffing

## Audience entry points

The landing page should speak to at least four audience motivations:

1. **Relaxing aquarium/screensaver players**
2. **Decorators and sandbox creators**
3. **Breeding/economy players**
4. **Observers/social browsers**

Different sections can emphasize different motivations, but the page should still
feel like one coherent premium product.

## Recommended page structure

## 1. Hero section

The hero must do most of the credibility work.

Recommended contents:

- strong title and value proposition
- short supporting copy
- primary CTA such as `Start Free Sandbox`
- secondary CTA such as `Watch Public Aquariums`
- premium visual treatment using in-engine renders, captured gameplay, or approved art

Recommended first-implementation format:

- a lightweight cinematic motion loop as the primary hero treatment
- not a static-only hero if motion can be delivered well
- not a heavy interactive 3D hero that risks harming first-load performance

Recommended visual style:

- real tank scene or polished composite built from real game assets
- visible fish movement and layered tank depth
- subtle motion, not distracting chaos
- intentional framing that highlights the side-view aquarium presentation
- mostly side-on framing with only a very slight cinematic tilt/parallax bias if it
  improves polish without misrepresenting the actual in-game presentation
- for the first implementation, prefer a **calm premium planted-beauty mood** over a
  dramatic or noisy spectacle-first composition
- frame the scene so the **full aquarium composition reads clearly first**, while the
  betta still remains the obvious focal fish within that composition

Avoid:

- generic stock art
- filler gradients with no product evidence
- fabricated mockups not grounded in the actual design direction

## 2. Gameplay modes section

A clear section for:

- Sandbox
- Career
- Observer

Each card or block should communicate:

- what kind of player it is for
- what the experience feels like
- why it is distinct

## 3. Visual showcase section

This section should prove quality.

Recommended contents:

- high-quality stills from tank scenes
- short clips or lightweight motion loops
- fish close-ups
- tank variety examples
- backdrop/theme examples

Important rule:

All visuals should come from:

- captured gameplay,
- engine renders,
- approved concept art,
- or founder-provided assets.

Do not pad this section with low-trust generated filler.

## 4. Feature/pillar section

Good candidates:

- breed and design fish tanks
- build beautiful freshwater and saltwater displays
- browse public aquariums
- shape your experience from cozy to challenging
- play directly in the browser

## 5. Social proof / trust section

Possible contents later:

- featured tanks
- devlog timeline
- creator spotlights
- newsletter or wishlist signup
- press/creator mentions if they exist

## 6. FAQ / discoverability section

Useful for both users and SEO.

Candidate questions:

- What kind of game is this?
- Is it playable in the browser?
- Is there a sandbox mode?
- Can I visit other players' aquariums?
- Do I need an account?
- Is it free to start?

## 7. Footer / long-tail discovery section

Useful links later:

- gameplay overview
- sandbox mode page
- breeder mode page
- observer mode page
- privacy / terms
- devlog or news

## SEO strategy

SEO should be treated as intentional information architecture, not as keyword spam.

## Target content types

The site should eventually support indexable pages such as:

- homepage
- gameplay overview
- sandbox mode overview
- breeder mode overview
- observer/public aquariums overview
- fish species or content spotlights later
- updates / patch notes / devlog later

## On-page SEO requirements

Each important page should have:

- unique title tag
- unique meta description
- clear H1
- clean heading hierarchy
- descriptive body copy
- descriptive image alt text
- canonical URL
- Open Graph / social meta

## Structured data opportunities

Possible schema usage:

- `VideoGame`
- `FAQPage`
- `Organization`
- `BreadcrumbList`

Use structured data only when it is truthful and supports the actual page content.

## Technical SEO requirements

The marketing site should prioritize:

- server-rendered or statically generated public pages
- clean semantic HTML
- crawlable content without requiring heavy client-side hydration first
- sitemap generation
- robots.txt
- canonical management
- fast Core Web Vitals

The playable app can remain more application-heavy, but the public marketing and
SEO-critical pages should not depend on a JavaScript-only shell to communicate
the main value proposition.

## Content quality bar

Copy must be:

- specific
- confident
- human-written or heavily human-edited
- consistent with the actual game design

Do not allow:

- empty hype phrases
- generic AI-marketing clichés
- unsupported claims
- repetitive keyword stuffing

## Landing-page performance

A premium landing page must also load like a premium landing page.

Requirements:

- optimize hero media aggressively
- avoid massive autoplay background videos unless they are highly compressed and graceful
- use poster images and progressive enhancement
- lazy-load below-the-fold media
- serve compressed images in modern formats
- keep motion smooth without making the page heavy

The page should feel rich, not bloated.

## Asset policy for the landing page

Preferred assets:

- real screenshots
- real fish renders from in-game or asset pipeline scenes
- real UI captures once available
- polished founder-authored media

Avoid:

- placeholder generated scenes with no production value
- inconsistent visual styles
- assets that make the game look lower quality than it is intended to be

## Conversion strategy

Primary conversion goals:

- start guest sandbox
- create account
- browse public aquariums

Secondary conversion goals:

- join waitlist or newsletter if used later
- follow development updates
- return to previously viewed content

## Implementation guidance for future agents

- Treat the marketing site as a product surface, not an afterthought.
- Favor SSR or static generation for public landing and SEO pages.
- Require authentic visuals grounded in real assets or polished captures.
- Optimize landing-page media as carefully as gameplay assets.
- Write copy that proves the game has substance instead of hiding behind hype.
