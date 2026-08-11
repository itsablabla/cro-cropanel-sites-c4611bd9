# No visible reviews on product page — dev spec
Site: allbirds.com · Priority 7 · Urgent · Effort: Medium (2-5 days)

## Problem
The product page lacks visible review ratings or review count near the price, so buyers may doubt the product's quality and hesitate to purchase.

## Evidence (from the live site)
> The page has an H2 'Reviews for Anytime Ankle Sock' but the body sample does not show any review stars, review count, or testimonial snippets near the product title or price.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: No review stars or count visible in the product title area; 'Get Notified' CTA suggests out-of-stock, but no social proof to reassure buyers.

## Required change
h1: Anytime Ankle Sock; cta: Get Notified; notes: Add a star rating and review count directly under the product title (e.g., '★★★★★ 1,234 reviews') to leverage social proof and reduce hesitation.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a star rating and review count directly under the product title (e.g., '★★★★★ 1,234 reviews') to leverage social proof and reduce hesitation.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_visible_reviews_on_product_page` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
