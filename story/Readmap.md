# Roadmap — GTA IV: SASIN

Updated 2026-10-11. Reflects the completed architecture pass and the gates ahead.

## PHASE 1: FOUNDATION ✅
- Stage 1 (canon audit) ✅ — `canon-ledger.md` restructured: CONFIRMED / PROPOSED / OPEN / REJECTED + Decision Queue.
- Stage 2 (underlying truth) ✅ — `writer_master_chronology.md`: full causal chain; all 15 prior OPEN items resolved or staged; continuity guards.

## PHASE 2: CHARACTER & MYSTERY ✅
- Stage 3 (characters) ✅ — `characters/`: 10 profiles with bounded knowledge, arcs, voices.
- Stage 4 (mystery construction) ✅ — `clue-schedule.md`: 23 clues, surface/true readings, knowledge gates, fair-play audit; consequence ledger in `consequence-tracker.md`.

## PHASE 3: CAMPAIGN STRUCTURE ✅ (writer-level) — GATE: user approval
- Stage 5 (outline) ✅ — `campaign-outline.md`: 17 missions / 5 acts, per-mission objectives/gameplay/clues/consequences/transitions, pacing audit, single-canon ending policy.
- Stage 6 (spoiler-safe design doc) — partially satisfied by player-facing sections of profiles + mission scripts; a consolidated spoiler-free design doc remains available on request (low priority while scripts carry the guards).
- Stage 7 (audit & approval) — **GATE: the user reviews the Decision Queue** (canon-ledger §8) and the four Act I scripts. Story is not locked until then.

## PHASE 4: IMPLEMENTATION
- **Track A — Narrative scripts (writer track):** Act II begins after Decision Queue feedback; one mission at a time (M5 "Blood and Paper" first), each with continuity/spoiler checks and a consequence-tracker update in the same commit. Acts III–V follow act-by-act.
- **Track B — Technical PoC (machine track, user-gated):** `docs/local-verification-checklist.md` step 0 → runtime approval → `docs/poc-cinematic-plan.md` P0–P3 → storyboard `cinematics/poc_storyboard.md` realized. No mission scripting before PoC passes.
- **Convergence:** after PoC, Act I missions are converted to runtime data files one at a time (schema in technical-architecture.md), each gated by a smoke test.

## Current position
- Phase 3 complete at writer level; Phase 4 both tracks **blocked on user input** (Decision Queue + PoC approval). Nothing in Track B may start without explicit approval to install (canon-ledger 6.4).
