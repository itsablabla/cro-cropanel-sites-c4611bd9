# Mega-menu choice overload — dev spec
Site: allbirds.com · Priority 5 · Urgent · Effort: Medium (2-5 days)

## Problem
The mega-menu presents 20+ nav items with repeated categories, causing choice overload and decision paralysis.

## Evidence (from the live site)
> nav_items list contains 20 items including duplicates like 'New Arrivals', 'Bestsellers', 'Men's Shoes', 'Women's Shoes' repeated across sections; body_sample shows extensive menu text repeated multiple times.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Mega-menu has 20+ items, many repeated, with no clear hierarchy or visual grouping.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Consolidate menu to 5-7 top-level categories, use flyout submenus, and remove duplicate entries.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Consolidate menu to 5-7 top-level categories, use flyout submenus, and remove duplicate entries.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_mega_menu_choice_overload` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
