# PoC Storyboard — "The Ledger Page" (60–90 s cinematic)

Companion to `docs/poc-cinematic-plan.md`. All staging uses vanilla assets; every shot is authored with runtime camera primitives **after P1 verifies them**. Duration budget: 84 s.

## Shot list

| # | Dur | Shot | Camera | Staging | Audio/Subtitles |
|---|-----|------|--------|---------|-----------------|
| 1 | 10 s | Establishing: Broker docks at dusk, dead low tide. Haru walks the pier toward a distant bollard | Slow dolly-in at head height, 8 m behind subject | Weather: overcast→clear dusk fixed; no rain (perf) | Ambient: gulls, water, distant traffic. SUB (0:06): "HARU: He said the water would come to me." |
| 2 | 8 s | The thermos and two cups on a crate at the bollard — steam rising, nobody there | Static insert, shallow FOV | Prop pair placement; steam via existing particle (verify native at P1; fallback: omit steam) | SUB (0:14): "—A.: COME STAGED, IF IT HELPS YOU. I'LL BE THE ONE WHO ISN'T THERE." |
| 3 | 12 s | Reverse: Haru's POV along the empty pier; floodlight scaffold in silhouette | Handheld-sim (subtle shake), slow push | Lighting: existing pier lamps only | SUB (0:20): "VOICE: I mailed you the map, Mr. Haru. I don't need your gratitude. I need your knife." |
| 4 | 9 s | Close: Haru lifts the thermos — the torn ledger page beneath, one corner ripped away | Top-down insert, rack focus to page | Page texture (M4 asset) | SUB (0:32): "VOICE: A page is a hook. Hooks are honest about being hooks." |
| 5 | 14 s | Profile two-shot: Haru at the water's edge reading; the city skyline behind | Orbit arc, 30°, slow | Character idle anim loop (verify at P2) | SUB (0:42): "HARU: Name the party. / VOICE: Names are liabilities. I trade in pages." |
| 6 | 12 s | Wide: floodlights snap on across the yard; the watcher car noses through the far gate | High static wide | Scripted light + vehicle spawn (verify at P2) | SUB (0:58): "VOICE: My cue. The thermos is a gift. The exit is your problem." |
| 7 | 12 s | Haru pockets the page; walks into the container stacks, away from camera | Slow dolly-back as subject approaches lens then passes | Non-combat; no peds beyond subject | Ambient swell. SUB (1:12): "VOICE (fading): You'll come needing, the third. That's not a threat. It's a forecast." |
| 8 | 7 s | Black frame; the page texture full-screen; tear visible | Static | — | SUB (1:21): "ACT I — THE RETURN / END" → fade out |

## Continuity guards
- Voice lines are verbatim from `story/act1_mission4_the_docks.md` — no paraphrase.
- Page texture matches the M4/M15 document style.
- No characters besides Haru appear; the voice is never localized to a body (speaker trick per M4 tech notes, verified at P1).

## Performance rules (UHD 620 budget)
- Fixed time-of-day, no mid-cutscene weather change, zero traffic spawns in shot, subject + ≤2 ambient peds off-camera.
- If P2 FPS < 25 at 720p: drop shot 6's car spawn and reuse a light flash instead; log the substitution.

## Failure fallbacks
| Missing native | Fallback |
|---|---|
| Camera tracks | Fixed-camera shot list (8 statics) — storyboard still reads |
| Subtitle natives | Text via HUD helper if available; last resort: the recording carries burned-in subs added in editing (out-of-game) |
| Steam particle | Omit (noted in shot 2) |
| Vehicle spawn | Light-cue substitution (shot 6 note) |
