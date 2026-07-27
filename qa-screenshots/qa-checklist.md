# QA Report: Jesus Alfaro — Post-Update (M/Y Maria CV + Photos)

**Date:** 2026-07-27
**URL:** https://jesus-alfaro.cofoundy.dev
**Tier:** Premium S/.280 (client #78, TRACKER.md)
**Change scope:** New CV (2nd Officer, M/Y Maria 67m, Mediterranean — up from Chief Officer Relief, Fort Lauderdale) + 11 real M/Y Maria photos + references swap (out: Juan Lamprecht, in: Capt. John Rose) + 2 section dividers + CV download.
**Status:** ⚠️ **PASS WITH WARNINGS** (1 content regression found — see Issues)

> **Environment note:** Playwright's Chromium download is blocked in this sandbox (repeated `400 GatewayExceptionResponse` from the CDN across 4 install attempts: `npx playwright install chromium`, `chromium-headless-shell`, local binary, and `--force` with an alternate download host). No fresh desktop/mobile screenshots could be generated. The pre-existing `qa-screenshots/desktop-hero.png` etc. in this folder are **STALE** (captured before this session's photo/content update — still show "Deckhand / Junior Officer", "Fort Lauderdale", "M/Y Princess Ashita" — do not use as evidence of current state). QA below is based on: live HTTP checks against the deployed URL, full source review (`config.ts` + all `.astro` components), direct pixel inspection of the actual photo files via the Read tool, and text-diff of the new CV against `config.ts`.

## Technical Health
- [x] HTML → 200
- [x] CSS (`_astro/index.lWk4Kxly.css`) → 200
- [x] `profile.jpg` → 200 (used by Hero + `og:image`)
- [x] `favicon.svg` → 200
- [x] `cv.pdf` → 200, byte-identical to `assets/cv-nuevo.pdf` (deployed CV = new CV, confirmed via diff)
- [x] All 6 spot-checked yacht images → 200 (`yacht-maria-jetski.jpg`, `yacht-maria-lines.jpg`, `yacht-maria-tender.jpg`, `yacht-myq-bridge.webp`, `yacht-yacht2.webp`, `yacht-yacht4.webp`)
- [ ] `og.jpg` → 404, but not an issue: `<meta property="og:image">` points to `/profile.jpg` (200), not `/og.jpg`. No fix needed.
- [~] `guia.pdf` → 200 (n/a for Premium repeat client anyway)

## Content Update Verification (this session's scope)
- [x] Hero title: `2nd Officer · Chief Officer <3000 GT · DP Unlimited` ✓ (was "Deckhand/Junior Officer")
- [x] Hero tagline / meta description / masthead / status chip all say **Mediterranean-Based** — no leftover "Fort Lauderdale" as current location
- [x] `yachtingExperience` reduced 5→4 cards: M/Y Maria (current), M/Y Q, M/Y Inizio, M/Y Irvette — matches new CV exactly
- [x] Section header updated "Four Yachts. One Mission." (was "Five Yachts...") — no stale count
- [x] `stats[]` consistent: 3 licenses / 4 yachts / 6 references — all match array lengths
- [x] References: Capt. John Rose (M/Y Inizio, +1 540 246 9925) present; **Juan Lamprecht not found anywhere in `src/` or `public/`** — swap done correctly
- [x] Removed boats confirmed absent from `src/` and `public/`: "Incognito", "All Class Detailing", "Dropout" — zero grep hits
- [x] Sylvester Moise / M/Y Princess Ashita reference **still present** in config — verified this is **correct, not a bug**: the client's own new CV (`cv-nuevo.pdf` = deployed `cv.pdf`) still lists this exact reference verbatim, even though the Princess Ashita job entry itself was dropped from Yachting Experience. Data matches source.
- [x] "3rd Officer" / "Fort Lauderdale, FL" strings that remain in `config.ts` are legitimate **historical** context (past job locations, career-progression text in `offshoreBackground.roles`) — not presented as current status. No fix needed.
- [x] Two section dividers use the new real M/Y Maria photos (`yacht-maria-tender.jpg`, `yacht-maria-lines.jpg`) per `src/pages/index.astro`

## Photo ↔ Entry Consistency (visual inspection of actual files)
- [x] `yacht-maria-jetski.jpg` — Marbella coastline (La Concha mountain visible) on a Sea-Doo jetski → correct for M/Y Maria / Mediterranean / watertoys bullet
- [x] `yacht-maria-lines.jpg` — line/fender work on a superyacht hull → correct for mooring/deck-maintenance bullets
- [x] `yacht-maria-tender.jpg` — driving a RIB tender at sea → correct for tender-handling bullet
- [x] `yacht-myq-bridge.webp` (M/Y Q card) — officer polo with small embroidered "Q" logo, visible bridge/ECDIS behind → consistent, no foreign yacht branding
- [x] `yacht-yacht4.webp` (M/Y Irvette card) — cap literally embroidered **"Mystere"** → this is *correct*, not a mismatch: config explicitly labels the vessel "M/Y Irvette (previously M/Y Mystere)"
- [x] `yacht-yacht2.webp` (M/Y Inizio card) — generic filename but no conflicting yacht name/logo visible in frame; alt text "West Palm Beach" matches Inizio's stated location
- [x] No watermarks, no stock-photo artifacts, no visible branding contradicting its assigned card

## Data Validation
- [x] Deployed `cv.pdf` byte-identical to the new source CV (`assets/cv-nuevo.pdf`) — confirmed via `diff`
- [x] All yacht names, dates, roles, vessel sizes in `config.ts` yachtingExperience cross-checked line-by-line against the new CV text — match
- [x] Personal details, licenses, visas, ENG1 medical — unchanged, match CV
- [ ] **Pre-existing, out-of-scope inconsistency (not from this session):** `offshoreCredentials.vessels[0]` lists M/V Sapphire as "84m" while the new CV's background section lists "Sapphire - 92 m". Could not confirm correct value — `performances_offshore*.pdf` are scanned images with no text layer. Flagging as low-severity for a future correction, unrelated to today's change.

## Clean Deploy
- [x] No template artifacts, no "Lorem ipsum", no "undefined"/"null" in `config.ts`
- [x] No default/placeholder social links — LinkedIn, email, phone all real and specific to Jesus
- [x] `README.md`, repo naming, CNAME all correct

## Design Proposal Match (Premium gate)
- [x] Palette matches `design-proposal.md`: `primaryDark #0A1628`, `accent #C9A96E`, `surface #F5F1EA` ✓
- [x] Typography matches: Cormorant Garamond (display/serif) + Montserrat (body) ✓
- [x] Unique section retained (Offshore Performance Records with signed Master quotes) — no other portfolio has this ✓

## Visual QA — Desktop / Mobile
**Not directly re-verifiable this session** (Playwright browser install blocked in sandbox — see environment note above). No layout/CSS files were touched in this update (only `config.ts` content + new image files + 2 divider image references), and the April 2026 QA (`qa-checklist.md` at repo root) already passed full desktop/mobile responsive checks on the same component structure. Risk of new layout/mobile regressions from this change is low, but **not independently confirmed today**. Recommend a follow-up screenshot pass next time Playwright browsers are available (e.g., from `alvaro`/`melissa`'s machine or after sandbox network is unblocked) before telling the client "todo revisado visualmente."

## Issues Found

- **CRITICAL — Footer.astro has stale/orphaned positioning copy, contradicting the rest of the (updated) site.** `src/components/Footer.astro` lines 15-18 are hardcoded (not pulled from `config.ts`) and were never updated in this session:
  - `"OOW Unlimited · Deckhand / Junior Officer"` / `"Seeking long-term yachting position."` — client is now a **2nd Officer** seeking **Rotational Second Officer** opportunities (per Hero, CTA, and the new CV). This literally downgrades his title on his own site footer.
  - Bottom bar: `"Available Immediately · Open to Rotational & Temporary Positions"` — contradicts Hero/CTA's `"Available by Arrangement"` (config's `cta.description`). Both lines are leftovers from the original April "Deckhand, Fort Lauderdale, available immediately" version.
  - **Fix:** replace both hardcoded strings with config-driven values (e.g. reuse `siteConfig.title` / `siteConfig.cta.description`), or hand-update to `"2nd Officer · Chief Officer <3000 GT"` / `"Seeking Rotational Second Officer opportunities."` and `"Mediterranean-Based · Available by Arrangement"`.

- **WARNING (low, out of scope) — `offshoreCredentials` vessel size mismatch:** M/V Sapphire listed as 84m in `config.ts` vs 92m in the new CV's background section. Source PDFs for the performance records are scanned (no text layer) so the correct figure couldn't be independently confirmed. Pre-existing, unrelated to this session's edit — flag for a future pass.

- **WARNING — No fresh visual (screenshot) QA this session** due to sandbox network blocking Playwright's Chromium download. Content/data was validated at the source + HTTP level, but pixel-level rendering (overflow, exact stacking, spacing) was not re-verified after the photo/content swap.

## Evidence
- Live checks: `curl` HTTP status on HTML/CSS/CV/photos, `<title>`/meta tag extraction from deployed HTML
- `diff assets/cv-nuevo.pdf public/cv.pdf` (via pdftotext) → identical
- Direct image inspection (Read tool) of `yacht-maria-jetski.jpg`, `yacht-maria-lines.jpg`, `yacht-maria-tender.jpg`, `yacht-myq-bridge.webp`, `yacht-yacht2.webp`, `yacht-yacht4.webp`
- Full read of `src/config.ts` and all `src/components/*.astro`
- `qa-screenshots/*.png` in this folder are STALE (pre-update) — kept for historical reference only, not used as evidence for this report
