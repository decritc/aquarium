# Feature Rollout Roadmap

This document defines when later-phase product features should move from "planned"
to "active implementation work."

The goal is to prevent premature scope growth while still ensuring that important
social, discovery, and public-sharing features begin at the right time.

## Principles

1. Build for quality first, then breadth
2. Use real user demand and content density to trigger expansion
3. Do not wait so long that existing public-facing features feel broken or incomplete
4. Treat rollout thresholds as product signals, not hard laws

## Phase framing

### Phase A: First implementation

Ship:

- premium landing page
- guest sandbox
- handcrafted featured observer aquarium
- observer-safe minimal HUD
- like/favorite interaction only

Do not require yet:

- full public-tank gallery
- follow system
- comments
- large social discovery surfaces

## Observer-mode rollout milestones

## Milestone O1: Featured observer launch

Trigger:

- first implementation / launch candidate

Goal:

- prove the observer fantasy through one premium handcrafted showcase tank

Included:

- one featured studio/demo aquarium
- read-only observer presentation
- like/favorite action
- no broad discovery surface yet

Why:

- fastest path to a premium observer destination
- strongest support for landing-page marketing
- avoids dependence on live user content too early

## Milestone O2: Basic public-tank discoverability

Trigger:

- approximately **10 or more** public/observable user tanks exist
- and/or the single-featured-tank observer entry starts to feel too limiting

Goal:

- let users browse more than one public tank in a lightweight way

Begin work when:

- public tank count is around 10+
- there is enough variation that discovery becomes meaningful

Recommended included features:

- lightweight public-tank browse page
- simple featured/recent list
- basic public-tank cards
- links from public tanks to owner/profile surface if available

Still optional at this stage:

- full search
- deep filters
- comments
- dense social graph features

## Milestone O3: Follow system

Trigger:

- meaningful repeat viewing behavior appears
- users are trying to re-find specific creators or tanks
- public observable tanks are numerous enough that identity matters

Signals to start work:

- users repeatedly revisit the same public tanks
- requests for "follow" or "save creator" become common
- there are enough public creators that manual discovery is no longer enough

Recommended included features:

- follow/unfollow creator
- creator profile page or lightweight creator surface
- simple "following" or "from creators you follow" list later if justified

## Milestone O4: Comments and deeper social interaction

Trigger:

- public viewing is active enough that social conversation adds value
- moderation capability is ready

Do **not** start serious implementation until both are true:

1. user demand is clear
2. moderation tooling/process is ready

Signals to start work:

- users want to react to specific tanks in more detail than likes/favorites
- featured/public tank sharing is active
- creator identity and audience loops are strong enough to justify conversation

Required prerequisites:

- moderation policy
- report/abuse flow
- blocked/hidden content handling
- public-background moderation approach if uploads exist

## Milestone O5: Rich discoverability

Trigger:

- observer mode has enough public content density that browsing is a core product loop

Signals:

- dozens of public tanks or more
- repeated search intent by species/theme/creator
- meaningful featured and recent churn

Recommended included features:

- search by creator
- search/filter by species
- theme/tag browsing
- featured/recent/popular tabs
- curated collections later

## Owner-public sharing rollout

## Rule S1: Public means observable

If a user marks a tank public, that tank should be treated as observable by other users.

## Rule S2: Shareability should arrive alongside real public viewing

Once the product supports real user-public tank observation at scale, those public
tanks should have straightforward ways to be accessed or shared.

This does not mean the first implementation must support full creator-driven public
sharing immediately, because the first observer route is a handcrafted studio/demo
tank. It does mean:

- once user-public viewing is enabled beyond that handcrafted showcase
- users should not be forced into a hidden or hard-to-access "public" state

Recommended early sharing forms:

- direct public tank URL
- creator/public tank page
- copy-link action

## Demand signals to monitor

Future teams should watch for:

- number of public observable tanks
- repeat observer visits
- return visits to the same creator/tank
- requests for follows/comments/search
- usage of like/favorite actions
- traffic from shared links once those exist

## Start-work guidance

### Build now

- featured observer tank
- like/favorite

### Start when public tanks reach ~10+

- lightweight discoverability/browse

### Start when creator identity matters

- follows

### Start only with moderation readiness and clear demand

- comments

## Implementation guidance for future agents

- Do not build the entire social stack before public content density exists.
- Do not wait too long to add browse/discovery once public tanks become numerous.
- Treat 10+ public observable tanks as the threshold for starting simple observer discovery.
- Treat follows/comments as demand-driven expansions, not automatic first-phase work.
