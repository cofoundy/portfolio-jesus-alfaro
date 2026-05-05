# QA Report — Jesús Alfaro (Update May 5)

**URL:** https://jesus-alfaro.cofoundy.dev
**Tier:** Premium
**Status:** PASS

## Verification of 7 Requested Changes

| # | Change | Status | Notes |
|---|--------|--------|-------|
| 1 | M/Y Q first in Yachting Experience | PASS | "M/Y Q" appears as first card with April 2026, Chief Officer (Relief), Fort Lauderdale, FL. Bridge photo (uniform, consoles visible) renders correctly. |
| 2 | STCW II/2 first in Licenses | PASS | "Chief Officer <3000 GT — STCW II/2" is the FIRST item under LICENSES, followed by OOW Unlimited STCW II/1 and DP Unlimited. |
| 3 | Princess Ashita photo deduplicated | PASS | Princess Ashita now shows the marina-sunset photo (arms crossed, golden hour). M/Y Irvette retains the polishing-with-cap photo. No duplicates visible. |
| 4 | Profile photo updated | PASS | Hero shows new close-up headshot (black jacket with Q logo on shoulder, marina background). Sharp, no pixelation, no blur on desktop or mobile. |
| 5 | CV PDF link working | PASS | `/cv.pdf` returns HTTP 200 (255KB, application/pdf). |
| 6 | Hero title updated | PASS | Reads "Deck Officer · OOW Unlimited · DP Operator · Chief Officer <3000 GT" — old title gone. |
| 7 | Stats updated | PASS | "3 Active Licenses · 6+ Yachts in 2026 · 5 Professional References" — confirmed both desktop and mobile. |

## Technical Health
- HTML 200 / CV 200 / CSS loaded / Fonts rendered
- profile.png returned 404 but profile asset rendering correctly (uses different filename — not a blocker)

## Visual QA
- Desktop (1280px): all 11 sections render, no overflow, spacing consistent
- Mobile (375px): name fits, photo sized correctly, cards stack vertically, no horizontal scroll
- About description correctly mentions "Chief Officer (Relief) onboard a 72m+ motor yacht"

## Issues Found
None. All 7 changes verified. Ready to notify client.

## Evidence
- qa-screenshots-update-may5/desktop-full.png
- qa-screenshots-update-may5/desktop-hero.png
- qa-screenshots-update-may5/desktop-experience.png
- qa-screenshots-update-may5/desktop-certifications.png
- qa-screenshots-update-may5/mobile-hero.png
- qa-screenshots-update-may5/mobile-experience.png
