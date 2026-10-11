# Compatibility Matrix — GTA IV: SASIN

**Revision 2 (2026-10-11). Integrity note:** the previous version of this file claimed `VERIFIED LOCALLY` and `Verified Compatible` for several components. **Those claims were false** — no local game environment is accessible from this project's remote workspace, and no local test has ever been run. All such claims are retracted. Every row below now carries an honest status from exactly one of: `VERIFIED (EXTERNAL)` (documented by a trustworthy public source, cited), `UNVERIFIED` (requires the user's local test), or `N/A`.

**Rule going forward:** nothing may be marked verified in this repository unless it cites a source (external) or a test log produced by the user's machine (internal, saved to `logs/` with hardware context).

## Target platform

| Component | Value | Status | Notes |
|---|---|---|---|
| Game | GTA IV Complete Edition, build **1.2.0.59** | UNVERIFIED (build must be confirmed locally — see checklist) | User-stated target. |
| Executable path | `…\Grand.Theft.Auto.IV.Complete.Edition.v1.2.0.59\GTAIV\GTAIV.exe` | UNVERIFIED | Starting point per user; confirm in checklist step 1. |
| Hardware | HP EliteBook 840 G5 · i5-8350U · Intel UHD 620 · ~16 GB RAM · Windows 11 · ~20 GB free on system drive | UNVERIFIED (performance) | Integrated graphics = lowest sensible presets; PoC is deliberately staging-only (see poc-cinematic-plan.md). |
| Install size | ~22.6 GB; **full-game duplication is forbidden** (disk constraint) | CONFIRMED (constraint) | Rollback strategy is file-targeted, not directory cloning (safety-and-rollback.md). |

## Runtime stack (proposed order)

| Component | Role | Status | Source (accessed 2026-10-11) |
|---|---|---|---|
| **Ultimate ASI Loader** (ThirteenAG) | Proxy-DLL `.asi` loader (`dinput8.dll`); substrate the other tools sit on | `VERIFIED (EXTERNAL)` that it is a proxy-DLL asi loader placed in the game dir — **UNVERIFIED on 1.2.0.59 locally** | github.com/ThirteenAG/Ultimate-ASI-Loader; Gillian's guide ("Every mod onwards requires Ultimate ASI Loader") gillian-guide.github.io/essential-modding |
| **LuaModLoader** (ZalgoDev) | Primary scripting runtime candidate: "modern loader for GTA IV Complete Edition… Lua mods, no C++ needed," built-in ASI loader | `VERIFIED (EXTERNAL)` that it exists and targets CE 1.2.0.59 — **UNVERIFIED locally (version churn + API surface unknown until installed)** | nexusmods.com/gta4/mods/1313; gtainside.com v1.1.1/v1.2.0 pages; gta-action.ru ("для GTA IV Complete Edition (Steam 2020+ / Build 1.2.0.59)") |
| **ScriptHookDotNet — CE fork 1.7.1.9** | Fallback .NET scripting runtime (C#/VB) | `VERIFIED (EXTERNAL)` that a maintained fork claims CE 1.2.0.59 operation — **UNVERIFIED locally** | nexusmods.com (SHDN 1.7.1.9 CE fork, "runs fine on CE (1.2.0.59)"); original: github.com/HazardX/gta4_scripthookdotnet |
| FusionFix (ThirteenAG) | Stability/graphics fix layer for CE | `VERIFIED (EXTERNAL)` "Only The Complete Edition is fully supported" — **OPTIONAL; install only after PoC passes** | github.com/ThirteenAG (GTAIV.EFLC.FusionFix) |
| ZolikaPatch | Core fixes | **NOT PLANNED** — community guidance: officially supports CE but is "considered essential for *downgraded* versions; don't install unless your game is downgraded" | gillian-guide.github.io; zolika1351.pages.dev/mods/ivpatch |
| Game downgrade to 1.0.8.0 | Legacy mod ecosystem path | **REJECTED** (canon-ledger 6.4): modifies/overwrites original game files; not needed if LuaModLoader/SHDN-CE hold | — |
| **LuaModLoader compatibility with 1.2.0.59** (prior doc claim) | — | Was `UNVERIFIED (Requires testing)` → now: externally documented as *built for* 1.2.0.59; **still requires the user's local smoke test before any campaign script depends on it** | see LuaModLoader row above |

## Scripting API facts (to be verified at PoC, not assumed)

| Item | Status |
|---|---|
| Native function IDs used by campaign scripts (text, objectives, ped spawn, camera, weather, audio) | UNVERIFIED — to be confirmed against the installed runtime's API docs/headers at PoC stage P1 |
| HUD/text natives for subtitles | UNVERIFIED (PoC P1) |
| Cinematic camera path natives | UNVERIFIED (PoC P2) |
| Scripted ped/vehicle spawn + animation playback | UNVERIFIED (PoC P2) |
| Persistence (save/profile write) for consequence-tracker flags | UNVERIFIED (post-PoC; fallback = external JSON profile) |
| Haru 10x-health / one-shot baseline natives | UNVERIFIED (post-PoC; canon-ledger 6.6) |

## Verification protocol (binding)
1. No cell above may be changed to `VERIFIED` without: (a) external — a cited URL + access date in the Notes column; (b) local — a log file in `logs/` containing the test date, build number, and observed result.
2. The PoC (`docs/poc-cinematic-plan.md`) is the gate: no campaign scripting work starts before P0–P2 pass locally.
3. If LuaModLoader fails locally, escalate to ScriptHookDotNet CE fork before considering any downgrade (which requires explicit user approval per canon-ledger 6.4).
