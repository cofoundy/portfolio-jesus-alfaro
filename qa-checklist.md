# QA Checklist — Jesus Alfaro (Premium upgrade)

**URL:** https://jesus-alfaro.cofoundy.dev
**Date:** 2026-04-21
**Tier:** Premium S/.280 (upgrade Pro → Premium, +S/.160)
**QA Status:** ✅ PASS

## Automated Checks

- [x] `npm run build` passes (0 errors, 1 page, 848ms)
- [x] HTTP 200 on root URL
- [x] All 10 local assets return 200 (profile.jpg, cv.pdf, 7× yacht-*.webp, favicon.svg)
- [x] CSS loads (`_astro/index.*.css` → 200)
- [x] No broken image refs per `check-dist-assets.py`
- [x] `.nojekyll` present, gh-pages source code synced to main
- [x] `revealFallback` CSS animation confirmed live (defensive against JS-disabled / slow observers)

## Visual Verification (Screenshots)

All screenshots captured at /Users/melissaimannoriega/cofoundy/projects/pollada/clients/2026-02-19_jesus-alfaro/qa-screenshots/

### Desktop (1280px)
- [x] **Hero** — Editorial split: "Jesus Alfaro" Cormorant serif display, stats bar (OOW / 5+ / 4), large portrait right with teak gold frame + "Currently Aboard M/Y Princess Ashita" status chip with pulsing gold dot
- [x] **About (Professional Profile)** — Centered editorial quote in Cormorant serif 3xl, gold curly quotes, compass rose decorative
- [x] **Yachting Experience** — "Five Yachts. One Mission." title, 5 alternating entries with large photos (№ 01-05), № 01 has "Current Position" gold badge
- [x] **Section Divider** — Full-bleed NIGHT HOWL night yacht photo with "Every passage is precision." quote in large serif italic
- [x] **Offshore Background** — HF Offshore card with Chevron/Saipem/Pemex chips, 2-col bridge responsibilities
- [x] **Certifications** — 2-col (Licenses/Safety/Bridge/Medical left, Personal Details sidebar right with languages badges and visa list)
- [x] **Competencies** — Operational Skills + Professional Attributes 2-col, gold bullets
- [x] **References** — 2x2 cards (Pretell, Ciurlizza, Cleghorn, Lamprecht) with country flags and contact methods
- [x] **CTA** — Navy background, "Ready to Join Your Crew" serif, email + phone US CTA buttons (gold + outlined)
- [x] **Footer** — Navy with gold accents, 3-col (brand/nav/contact)

### Mobile (375px)
- [x] Hero stacks correctly: portrait first, then title/stats
- [x] Experience entries stack vertically, photos visible on all 5
- [x] Certifications collapses to 1-col properly
- [x] References stack to 1-col, all flags visible
- [x] CTA buttons full-width
- [x] No horizontal overflow

## Content Verification

- [x] Name: Jesus Alfaro
- [x] Title: OOW Unlimited · Deckhand / Junior Officer
- [x] Location: Fort Lauderdale, FL (updated from "relocating to Miami")
- [x] Phone US: +1 (754) 277-0935 (new)
- [x] Email: jesusalfaro116@gmail.com
- [x] LinkedIn link present
- [x] CV downloadable (`/cv.pdf` → 200)
- [x] 5 yachts in Yachting Experience (Princess Ashita, Incognito, All Class Detailing, Irvette/Mystere, Dropout)
- [x] 4 references with correct flags (🇲🇽 🇬🇧 🇳🇦 🇺🇸)
- [x] All certifications listed (OOW Unlimited, DP Unlimited, STCW, ECDIS, etc.)

## Design Quality (Premium tier validation)

- [x] **Unique palette**: Navy #0A1628 + teak gold #C9A96E + bone #F5F1EA (NOT generic "navy portfolio")
- [x] **Editorial typography**: Cormorant Garamond serif for all display + body Montserrat (magazine-grade)
- [x] **Large photography**: Portrait + 5 yacht photos as protagonists (not decorative stock)
- [x] **Alternating layout**: Matches Arthur Artigues reference (foto/text alternating by entry)
- [x] **Real client assets**: 100% Jesús' own photos (no Unsplash)
- [x] **Industry-specific language**: All-English, yachting terminology (deckhand, OOW, DPO, teak, COLREG, ECDIS)
- [x] **Luxury details**: teak gold hairline frames on photos, animated status chip, compass rose bg, full-bleed night yacht divider
- [x] **Premium test**: "If the name changed, would this be the same portfolio?" → NO — every photo, reference, and phrase is specific to Jesús

## Differences vs Previous Pro

| Element | Pro (old) | Premium (new) |
|---------|-----------|---------------|
| CV version | Feb 2026 | Apr 2026 (5 new yachts) |
| Title | "Deck Officer & DPO" | "OOW Unlimited · Deckhand / Junior Officer" |
| Location | "Relocating to Miami" | "Fort Lauderdale · Available Immediately" |
| Experience count | 1 (HF Offshore) | 5 yachts + HF Offshore |
| References | 0 | 4 Chief Mates / Captains with flags |
| Typography | Standard sans | Cormorant Garamond editorial serif |
| Layout | Timeline vertical | Editorial magazine alternating |
| Photos | 1 hero | 10+ full-bleed photos |
| Palette | Generic navy | Custom navy + teak gold |
| Feel | Technical portfolio | Luxury yachting magazine |

## Verdict

**✅ PASS — Ready for delivery**

The portfolio is live, performant, responsive, and delivers a clear premium upgrade vs the previous Pro version. Matches Arthur Artigues reference structure adapted to maritime context. Zero broken assets, zero placeholder content, all 5 yachts and 4 references properly represented.
