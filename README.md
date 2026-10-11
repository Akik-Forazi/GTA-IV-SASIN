# GTA IV: SASIN

A fan-made single-player story campaign continuing Grand Theft Auto IV (Revenge Ending continuity: Roman survives, Kate dies).

## Project Overview
- **Protagonist:** Kim Haru / Ahsan ("SASIN") — already wealthy and dangerous; the flaw under the control is confusing control with certainty.
- **Engine / Target:** GTA IV Complete Edition (build 1.2.0.59), mod-runtime TBD by PoC (LuaModLoader candidate; see `docs/`).
- **Architecture:** data-driven mission definitions interpreted by a thin runtime layer over an approved loader — **nothing is installed or modified without explicit user approval; vanilla game files are never touched.**

## Current state (2026-10-11)
- Story bible, writer-only chronology, character profiles, 17-mission campaign outline, clue schedule, and consequence tracker are complete at writer level (see `story/`).
- Act I fully scripted (4 missions) with continuity/spoiler checks.
- Technical docs reset to honest baselines: all compatibility claims are sourced or explicitly UNVERIFIED; a staged 60–90 s cinematic PoC plan awaits local execution.
- **Awaiting user decisions:** canon Decision Queue (`story/canon-ledger.md` §8) and PoC install approval (`docs/local-verification-checklist.md`).

## Repository Structure
- `story/` — canon ledger, writer-only chronology, characters, campaign outline, clue schedule, consequence tracker, status log, Act I scripts.
- `docs/` — technical architecture, compatibility matrix (sourced), PoC plan, verification checklist, safety & rollback runbook, file manifest.
- `cinematics/` — storyboards for cutscenes and the PoC.
- `scripts/` `tools/` `tests/` `assets/` — mission data, utilities, test procedures, reference materials (populated as phases land).
- `logs/` — local execution logs (git-ignored except README).

## Integrity rules
1. No claim of "verified" without a cited source or a user-run log.
2. No original game file is ever modified; loader additions are manifest-tracked and rollback-proven.
3. No credentials, tokens, or personal data anywhere in the repository.
4. Canon changes flow one way: user approval → canon ledger → chronology → scripts.
