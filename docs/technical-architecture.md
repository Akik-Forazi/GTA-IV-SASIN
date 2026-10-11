# Technical Architecture — GTA IV: SASIN

**Revision 2 (2026-10-11).** Supersedes the prior draft. Changes: the C++/MinHook custom-ASI layer is **deferred** (do not build native binaries before a script-level proof of concept); the runtime strategy is now evidence-based (see compatibility-matrix.md for sources); every capability is labeled verified/unverified.

## Principles
1. **PoC before framework.** A 60–90 second cinematic must run locally before any mission-system code exists (user brief §7).
2. **Data over code.** Missions are data (objective lists, trigger volumes, dialogue tracks, staging notes) interpreted by a thin runtime layer — so revisions don't require rebuilds and writers can iterate.
3. **Vanilla assets only.** No custom meshes, weapons, vehicles, or audio; casting and staging use existing game content (user brief §6.8).
4. **The user's machine owns all truth.** Nothing is "playable" until the user runs it and a log exists (canon-ledger 6.2).

## Layer map

```
+--------------------------------------------------------------+
| story/*.md            writer/canon documents (this repo)      |
+--------------------------------------------------------------+
| missions/*.json|lua    mission DATA: objectives, triggers,     |
|                       dialogue, staging, consequence flags     |
+--------------------------------------------------------------+
| campaign runtime      thin interpreter: sequences objectives,  |
| (Lua, candidate)      fires cutscene camera tracks, routes     |
|                       persistence flags                        |
+--------------------------------------------------------------+
| host runtime          LuaModLoader (candidate #1) or          |
|                       ScriptHookDotNet CE fork (fallback #2)   |
|                       over Ultimate ASI Loader (dinput8.dll)  |
+--------------------------------------------------------------+
| game                  GTA IV Complete Edition 1.2.0.59        |
|                       (never modified; loader DLLs only)      |
+--------------------------------------------------------------+
```

## Runtime decision (proposed; requires local verification + user approval to install)

- **Candidate #1 — LuaModLoader** (Nexus #1313, built for CE 1.2.0.59): Lua mission scripts, built-in asi loading, no C++ toolchain required on the user's laptop. Matches the user's stated "Lua/JSON campaign definitions" preference and the laptop's constraints (no MSVC build cycle needed).
- **Candidate #2 — ScriptHookDotNet CE fork 1.7.1.9** over Ultimate ASI Loader: .NET scripts (C#). Heavier dependency chain (.NET framework/reds), but a mature API and large community knowledge base.
- **Selection procedure:** PoC stages P0–P2 are written twice only if needed — first attempt on #1; if the loader or its API fails on the target build, port the 90-line PoC to #2. No downgrade path is considered (canon-ledger 6.4).

## Mission data schema (draft; frozen after PoC)

```json
{
  "mission_id": "act1_m1_return",
  "act": 1, "index": 1,
  "start": { "type": "marker", "position": [x, y, z], "radius": 2.0 },
  "objectives": [
    { "id": "obj_taxi", "text_key": "M1_OBJ_TAXI", "type": "goto", "position": [x, y, z], "radius": 4.0, "optional": true }
  ],
  "cutscenes": [ { "id": "cs_arrival", "camera_track": "cinematics/tracks/m1_arrival.lua", "subtitle_track": "missions/subs/m1_arrival.csv", "audio": "ambient" } ],
  "flags_set": [], "flags_read": [],
  "failure": { "type": "none" }
}
```

- `flags_*` implement `story/consequence-tracker.md` (booleans/small ints; persistence mechanism verified post-PoC).
- Subtitles are CSV (`speaker,text,duration`) so dialogue revisions never touch code.
- Camera tracks are runtime-authored primitives (positions/look-at/fov over time) — **only after PoC P2 proves the camera natives on 1.2.0.59**.

## What was removed from the prior architecture, and why
- **C++ ASI + MinHook layer:** premature. It assumed loader + memory-hook compatibility that is unverified on 1.2.0.59, and it burdens the user's laptop with an MSVC toolchain for zero PoC value. Re-introduce only if both Lua and .NET candidates fail (unlikely; document first).
- **"Hot-reloading without recompiling":** retained as a goal of the data-driven layer, not as a claimed feature.

## Persistence & consequence flags
- Post-PoC: verify the runtime's supported persistence (ini/json/profile writes). Fallback: a JSON profile file inside the project folder, loaded at mission start — acceptable for a linear campaign with bounded flags (see consequence-tracker.md implementation checklist).

## Performance envelope (design targets, unverified until measured)
- i5-8350U / UHD 620: target 720p–900p, medium-low presets, vsync on. PoC uses fixed time-of-day, minimal peds/vehicles, no weather transitions mid-cutscene.
- Mission scripts must avoid per-frame polling where event callbacks exist in the chosen runtime (verify at P1).

## Explicit non-goals (until user directs otherwise)
- Multiplayer, trainers, graphics overhauls (ENB/Ivy), texture mods, file replacements inside the game directory.
- Any loader/patch installation **without the user's explicit approval** (canon-ledger 6.4).
