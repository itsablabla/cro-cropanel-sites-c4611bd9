# Competing primary CTAs — dev spec
Site: allbirds.com · Priority 1 · Urgent · Effort: Medium (2-5 days)

## Problem
The hero presents two equally prominent CTAs (SHOP MEN and SHOP WOMEN) that split user focus and delay the path to a single product category, reducing click-through to a specific purchase path.

## Evidence (from the live site)
> Hero section contains both 'SHOP MEN' and 'SHOP WOMEN' CTAs, with no primary/secondary hierarchy; body sample shows 'SHOP MEN SHOP WOMEN' adjacent to the headline.
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN', 'SHOP WOMEN'

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Two equal CTAs force an immediate gender choice, which may cause hesitation or misselection, especially for gift shoppers or those browsing for themselves without a clear gender preference.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Shop All (primary) + secondary links to Men/Women; notes: Make 'Shop All' the primary CTA to let users explore the full range first, with secondary links to Men/Women for those who know their preference. This reduces decision friction and keeps the path open.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Make 'Shop All' the primary CTA to let users explore the full range first, with secondary links to Men/Women for those who know their preference. This reduces decision friction and keeps the path open.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_primary_ctas` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
