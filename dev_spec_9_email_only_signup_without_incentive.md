# Email-only signup without incentive — dev spec
Site: allbirds.com · Priority 9 · Urgent · Effort: Medium (2-5 days)

## Problem
The single-field email capture on the homepage lacks a stated incentive or value exchange, which may reduce signup conversion.

## Evidence (from the live site)
> The homepage has a form with 1 input and submit button labeled 'Sign Up' under the heading 'Subscribe to our emails'. No incentive (e.g., discount, early access) is mentioned in the body sample.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Sign Up; notes: Email-only field with no explicit benefit or privacy reassurance.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Get 10% Off Your First Order; notes: Add a clear incentive (e.g., 'Sign up for 10% off') and a privacy note to increase opt-in rates.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a clear incentive (e.g., 'Sign up for 10% off') and a privacy note to increase opt-in rates.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_email_only_signup_without_incentive` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
