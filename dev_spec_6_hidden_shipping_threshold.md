# Hidden shipping threshold — dev spec
Site: allbirds.com · Priority 6 · Urgent · Effort: Medium (2-5 days)

## Problem
The product page does not display the $5 shipping cost or the $100 free-shipping threshold, so users may be surprised at checkout by an unexpected shipping fee, increasing cart abandonment.

## Evidence (from the live site)
> Product page inventory shows no shipping cost or threshold mentioned; only the homepage and collection page display 'Free ground shipping on orders over $100' and 'Shipping $5.00' in the cart drawer.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: Product page lacks any shipping cost or threshold information; users must discover it later in the cart or checkout.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart; notes: Add a line near the price or CTA: 'Free shipping on orders over $100. Otherwise $5 flat shipping.' This sets expectations early and reduces checkout surprise.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a line near the price or CTA: 'Free shipping on orders over $100. Otherwise $5 flat shipping.' This sets expectations early and reduces checkout surprise.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_hidden_shipping_threshold` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
