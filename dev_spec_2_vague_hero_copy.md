# Vague hero copy — dev spec
Site: allbirds.com · Priority 2 · Urgent · Effort: Low (0.5-2 days)

## Problem
The hero headline 'Wildly Comfortable. Super Natural.' is abstract and doesn't directly address the visitor's intent to find comfortable, sustainable shoes, causing them to rely on secondary CTAs.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN', 'SHOP WOMEN'

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: The headline is a brand slogan, not a value proposition. It doesn't mention shoes, comfort, or sustainability explicitly, which are the primary reasons visitors come to Allbirds.

## Required change
h1: Comfortable Shoes, Naturally Made; cta: Shop Men's Shoes / Shop Women's Shoes; notes: Make the headline concrete and benefit-driven. The CTAs should specify 'Shoes' to match the visitor's intent and reduce ambiguity.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Make the headline concrete and benefit-driven. The CTAs should specify 'Shoes' to match the visitor's intent and reduce ambiguity.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_hero_copy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
