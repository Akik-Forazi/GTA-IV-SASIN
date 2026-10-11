# Consequence Tracker — GTA IV: SASIN

**Purpose:** make branching honest. Every player choice records (a) what changed, (b) what it costs, (c) where it pays off. Single-canon ending: branches alter paths, costs, and texture — not the destination (`campaign-outline.md`, policy section). Technical note: all flags below are boolean/small-int persistent variables — implementable with any runtime that supports save-state or an external JSON profile (see `docs/technical-architecture.md`).

## M3 route choice (exclusive lead + exclusive cost)

| Flag | If ROUTE A — "Lose the Watchers" | If ROUTE B — "Set the Trap" | If ROUTE C — "Mandu's Method" |
|------|-----------------------------------|------------------------------|-------------------------------|
| `route_m3` | `A` | `B` | `C` |
| Exclusive evidence gained | Watcher rotation map + plate registry (→ M7 approach A, M8 raid pre-marked) | Captured watcher's testimony + phrase-set heard live (→ Niko's burn is stronger; M7 leverage B) | Paymaster shell name (→ M6 records thread pre-warmed, M7 pretext C) |
| Exclusive cost | Network confirms Haru is hunting → M5–M7 surveillance harder (more patrols) | Capture accelerates network timeline → M8 raid comes earlier/harder | Mandu's cover burned with the network → Act III PLANTED-fact trap (M10) targets him specifically |
| Texture change | More tail-evasion gameplay in Act II | Heavier combat in M7–M8 | More con/dialogue minigames in Act II–III |
| Niko burn | Deferred to M11 (weaker) | Foreshadowed M3 (stronger rupture staging) | Standard |
| Clue-schedule link | C-03/C-15 route flavor | C-07 spoken live | C-08/C-13 thread opened early |

## M6 board outcome

| Flag | Deal won cleanly | Deal lost (bad terms accepted) |
|------|------------------|-------------------------------|
| `m6_board` | `won` | `lost` |
| Effect | Subsidiary protected; package evidence richer | One legacy entity with the paper goes to the bid front → M12 annex grab harder; M13 parley opens with Baek holding a card |
| Texture | Min-ji confidence beats | Min-ji guilt beat; Haru restraint required in M13 |

## M13 parley posture (recorded, not decision-locked)

| Flag | Defiant | Cautious | Hostile |
|------|---------|----------|---------|
| `m13_posture` | `defiant` | `cautious` | `hostile` |
| Effect on M16–M17 | Factions flip faster (haru_reputation +) | Package needs one more evidence run (M16 longer) | Congress security heightened (M17 infiltration harder); Mandu improvises more |
| Character cost | Haru's self-trust scar deepest (arc beat sharpest) | Min-ji carries more of M16 | Haru's flaw relapse visible — Niko names it in M16 |

## M14 front choice (two fronts player-led, third scripted-allied)

| Front led | Gain | Permanent cost if led here is *skipped* |
|-----------|------|------------------------------------------|
| Depot (Roman) | Depot intact → M16–M17 logistics cleaner | Depot damaged; Roman injured-but-standing; texture debt into Act V |
| Jae-Ho extraction | Jae-Ho free with testimony intact | Jae-Ho re-taken → M15 opens with him leverage-hostage; confession comes under duress |
| Mandu cover | Identity kit survives → M16 con available | Mandu burned → M16 runs on nerve alone; refusal scene lands harder (writer note: both versions written) |

**Design rule:** every M14 choice must leave something permanently lost (chronology Part D). The tracker's job is making that loss visible and referenced later.

## Running reputation/legend flags

| Flag | Set by | Effect |
|------|--------|--------|
| `sasin_restraint` | Non-lethal resolutions in M2/M3/M7 | Underworld rumor shifts in Act IV–V dialogue; M17 crowd texture |
| `sasin_bodycount` | Lethal resolutions | More fear, less cooperation from minor characters; Kostov approach harder |
| `niko_rupture_healed` | M16 accounting scene completed with C-18 present | Epilogue variant dialogue |
| `mandu_refusal` | Always set in M16 (canon beat) | Epilogue: brother's claim filed |
| `roman_pattern_found` | M8 (binding beat — cannot be skipped, only flavored) | M8 safehouse raid pre-marked if M3=A |

## Prohibited branches
- No branch may reveal the Beneficiary's name before M12 (clue-schedule gates).
- No branch may save Tae-joon, resurrect the dead, or avert the massacre (it is the campaign's fixed past).
- No branch may end the campaign other than The Reckoning (single-canon policy) — posture and cost only.

## Implementation checklist (per mission shipped)
- [ ] Flags declared in the mission's persistence profile
- [ ] Downstream missions read every flag they own
- [ ] Failure states write flags (fail-forward, never soft-lock)
- [ ] Tracker updated in the same commit as the mission script
