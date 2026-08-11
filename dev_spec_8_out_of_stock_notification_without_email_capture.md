# Out-of-stock notification without email capture — dev spec
Site: allbirds.com · Priority 8 · Urgent · Effort: Medium (2-5 days)

## Problem
The 'Get Notified' CTA on the product page may not capture an email, missing a lead generation opportunity for back-in-stock alerts.

## Evidence (from the live site)
> The product page for Anytime Ankle Sock has a CTA 'Get Notified' but the forms inventory shows only the newsletter signup form (1 input, 'Sign Up') and no visible email field for stock notifications.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: CTA present but no associated email capture form detected in the crawl.

## Required change
h1: Anytime Ankle Sock; cta: Get Notified; notes: Ensure the 'Get Notified' CTA opens an inline email capture form to collect leads for restock alerts.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Ensure the 'Get Notified' CTA opens an inline email capture form to collect leads for restock alerts.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_out_of_stock_notification_without_email_capture` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
