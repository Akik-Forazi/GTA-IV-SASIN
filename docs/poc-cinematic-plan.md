# Proof-of-Concept Cinematic Plan — "The Ledger Page" (60–90 s)

**Purpose:** prove the fundamental approach on the target laptop before any mission framework exists (user brief §7). Success = a reproducible, rollback-safe 60–90 second staged cinematic, produced twice (once by procedure, once by the user) with logs.

**Status: plan only. Nothing here has been executed on any machine.** Every check must be run by the user; results go to `logs/`.

## PoC content (story-functional, not throwaway)
A staged rendition of the M4 pier beat: Haru walks the pier at dusk; a shot of the thermos and two cups; the voice line "I mailed you the map…" (subtitle only — no VO recording); the page under the thermos; a slow pull-back as the floodlights come on. Uses: one existing pier location, one ped (Haru model basis), fixed weather/time, ambient audio only.

## Stages (each gates the next)

### P0 — Loader loads (≈10 min)
1. User confirms build (checklist step 1) and installs the candidate runtime **after approving it** (canon-ledger 6.4).
2. Expected: game boots to menu with loader log present; no crash; vanilla behavior unchanged.
3. Log: loader version, boot time, any warnings. **Gate:** menu reachable, loader log exists.

### P1 — Text and natives (≈30 min)
- Runtime script draws a HUD subtitle line for 5 s, then a second line; prints a log line on each native call.
- Expected: on-screen text visible; log confirms the exact native names used.
- **Gate:** two subtitle cycles + zero native errors in log. *If natives fail → record names/returns, switch candidate runtime, repeat P0–P1.*

### P2 — The 60–90 s cinematic (≈2 h)
- Script sequence: weather/time set → camera track A (walk-in, 12 s) → subtitle block 1 → camera track B (thermos insert, 8 s) → subtitle block 2 → prop interaction beat (page reveal) → camera track C (pull-back + floodlights, 15 s) → fade.
- Expected: full playback; skippable via a key; clean return to control.
- **Gate:** plays end-to-end twice consecutively without crash or stuck state.

### P3 — Reproducibility (≈30 min)
- Second machine pass: delete loader files, verify vanilla, reinstall from the documented steps, replay. Both passes logged.
- **Gate:** identical results; rollback (below) proven.

## Rollback (binding, per safety-and-rollback.md)
- Before P0: record file inventory of game dir (names+sizes only) to `logs/baseline_inventory.txt`.
- Rollback = delete every file the procedure added (a numbered manifest `docs/poc-file-manifest.md` is created during install) + verify against baseline inventory. No vanilla file is ever overwritten by this project; if any step would, the step aborts.

## Measurement
- During P2: note FPS (runtime log or overlay), load time, and heat/noise (subjective note is fine). These numbers set the campaign's scene-budget rules in technical-architecture.md.

## Definition of done
- `logs/poc_p0.log`, `poc_p1.log`, `poc_p2.log`, `poc_p3.log` exist with hardware context.
- compatibility-matrix.md rows upgraded **with the log references**.
- A 20–30 s screen recording (optional, user's choice) stored outside the repo (git-ignored `cinematics/renders/`).
