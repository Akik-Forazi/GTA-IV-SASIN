# ACT I — MISSION 4: "The Man at the Docks"

**New mission (2026-10-11).** Resolves the dangling docks thread from the prior draft: the "—A." lure declined in M1 is answered on Haru's terms — and turns out to be on the sender's terms all along. First contact with the hidden author; the torn ledger page; the campaign's first beating of Haru's flaw (control ≠ certainty).

## Mission Overview
- **Placement:** Act I, Mission 4 of 4 (act closer). **Dramatic objective:** Haru accepts the second lure and stages it perfectly — exits sealed, overwatch set, ground controlled — and discovers the stage was dressed *for him*. He meets the voice, learns nothing he can prove, and leaves holding one physical object: a torn page.
- **Why now:** the caller promised the water would come; refusing twice would end the story, and accepting blindly would end the character. Haru accepts *on his own staging* — the flaw in its purest form.
- **Character conflict:** Haru's need to control against an opponent who prices control; Niko's professional distrust of any meeting he didn't arrange; Mandu's read of the stagecraft ("this pier is dressed").
- **Gameplay variety:** reverse-surveillance setup (player places overwatch and seals approaches), staged meet dialogue, third-party crash (network watchers), container-stack extraction.

## Opening cinematic

**[SCENE: BROKER DOCKS — INDUSTRIAL PIERS — DUSK — DEAD LOW TIDE]**

*(Bookend note: the same "water" the first text offered. The campaign returns to this geography in M17.)*

A second text, two days after the call:

> **SMS — UNKNOWN:** YOU DIDN'T COME TO THE WATER. TOMORROW, LOW TIDE, PIER 9 — COME STAGED, IF IT HELPS YOU. I'LL BE THE ONE WHO ISN'T THERE. —A.

**HARU** (reading it at the safehouse window; to Niko) "He's inviting my suspicion. That's either respect or bait."

**NIKO** "It's both. Nobody writes 'come staged' unless the stage is already dressed."

**MANDU** "Then we dress it *better*. I've had fights with better-dressed stages."

**[CUT: Haru, at the pier the next day, walking the ground an hour early — the player with him. Container stacks, one gate, two fences, open water on three sides.]**

**[ACTION: SETUP PHASE — player directs the staging: place NIKO and MANDU at two of three overwatch points; choose which of two yard gates to leave open. Staging is real: the crash in act three is *easier* from better points — but the meet itself plays identically. The game is honest; the antagonist is not the game.]**

## The meet

**[SCENE: PIER 9 — THE WATER'S EDGE]**

The pier is empty — except that at the far bollard, on a crate, sits a thermos and two cups, steam still rising. **No one.** From everywhere and nowhere, the flat synthetic voice — but on an outdoor speaker this time, played into the open air:

**VOICE (V.O.)** "You sealed the north gate. Good instinct — it's the one my watchers use. You gave it to them."

**HARU** (not moving; level) "Then say what you are."

**VOICE (V.O.)** "A bookkeeping voice. I mailed you the map, Mr. Haru — both prints, the grave, the words. I don't need your gratitude. I need your *knife*, aimed at the party your file concerns."

**HARU** "You don't get to be anonymous and specific. Name the party."

**VOICE (V.O.)** "Names are liabilities. I trade in *pages*." (a paper sound; a breath of wind) "There is a ledger that outlived your father. Fifteen years of entries. A page of it is under the thermos. The rest is in a place with better security than you, worse patience than me, and an owner who reads everything and signs nothing."

**HARU** (beat; the trap of it visible) "Why give me one page?"

**VOICE (V.O.)** "Because a page is a *hook*, and hooks are honest about being hooks. Because your sister keeps files and you keep promises, and between you, the ledger will surface. And because when it does — I'll still be alive, which is my entire business model." (the voice thins, almost human) "You didn't come to the water the first time. You came staged, the second. You'll come *need*ing, the third. That's not a threat. It's a forecast."

**[BEAT: floodlights — the yard's far gate — a watcher car (the north gate, the one Haru "gave" them) noses through. The meet was always going to be crashed. By whom: that was the only live variable, and Haru guessed wrong.]**

**VOICE (V.O.)** (unhurried, packing up in the sound) "My cue. The thermos is a gift. The *exit* is your problem — I booked mine first."

**[OBJECTIVE ADDED: retrieve the page; extract across the container stacks with Niko and Mandu. Watchers: four, armed.]**

## Extraction (gameplay)
- **Container-stack run:** cover-based movement, no forced kills (non-lethal path flagged `sasin_restraint`); Mandu's route shortcut opens only if he was placed at the east overwatch — staging consequences honored.
- **Haru takes a round through the shoulder of his coat** — a graze; second not-immortal beat of the act. He does not slow; the player will notice he doesn't dodge it either. *(Control: he was watching the wrong gate. Certainty would have watched the water.)*
- **Extraction complete → end scene.**

## Ending scene

**[SCENE: DEPOT BACK OFFICE — NIGHT]**

The torn page under the desk lamp: a Seorin-era payment entry, columns tight, a routing annotation in a second hand. At the foot, a signature block the attorneys will recognize (M5's beat). One corner is torn *away* — the page was torn from something larger, on purpose.

**MIN-JI (V.O., phone)** "Read me the annotation again… slower." (a long silence) "Haru. Someone bid on the Meridian subsidiary last night. Dormant nine years — and now, the same week you come home. I'm coming to the city. Don't do anything I'd have to fix."

**HARU** (to Niko, quietly, the graze dressed and the ear ringing) "He said I'd come needing. I hate that he scheduled me correctly."

**NIKO** "Get used to hating. It's the only part of this that's on time."

**[MISSION COMPLETE: "The Man at the Docks"]**
**[ACT I COMPLETE — ACT II: "FAMILY EMPIRE"]**

## Escalation & complication
- The campaign's antagonist *system* is now personified without being named: an author who trades in pages, forecasts behavior, and books his exits first.
- The torn page converts the mystery from "who killed them" to "what still exists to be found" — the ledger enters the player's vocabulary as an object, not a title.
- Min-ji's arrival is the act button: the Family Empire act begins as corporate warfare, not gun work.
- Haru's flaw takes its first public beating: he staged the ground and still gave away the gate. The lesson lands in dialogue without being lectured.

## Failure / retry handling
- Setup phase has no fail state (staging choices only). Extraction failure → respawn at stack head, watchers reset, page already in hand (page possession is scripted on meet completion, not on extraction).

## Technical implementation notes
- **Locations:** Broker docks piers (existing map area; verify pier 9 placement locally), container yard, depot back office.
- **Speaker voice:** positional ambient audio trick from a scripted point; voice filter as M3.
- **Thermos/page:** interactable prop pair; page = fullscreen document texture (matching M15's ledger style, torn edge).
- **Watchers:** four scripted AI, arrive/patrol/pursue states; non-lethal window flagged.
- **Setup UI:** overwatch placement via marker objects and objective text (no custom UI); staging consequences handled by trigger flags (east overwatch → shortcut active).
- **Runtime:** loader-layer scripting; UNVERIFIED on 1.2.0.59 pending PoC (docs/). The outdoor-speaker trick needs an audio-emitter native — flag for local verification; fallback: phone-call presentation.

## Continuity restrictions (hard)
- The voice NEVER names anyone. No "Beneficiary," no "Accountant," no "ledger owner."
- The torn page shows a *payment entry*, not a name that resolves anything; the signature block is recognized only in M5 by the attorneys.
- Niko recognizes the caller as the same voice from M3 — and nothing more. His knowledge reaches the *caller*, not the author's identity or any face from 2009; his distrust here is professional.
- Mandu operates on tags: INFERRED for the stage-dressing read; BLUFF permitted in the meet banter only.
- Kate: not referenced. Roman: present in setup logistics only (depot lockup for the night — his choice, protecting his people).
- Haru's graze: left shoulder, coat only — consistent with his M2 ear wound rules (he bleeds; he is not invincible).

## Spoiler check (player-facing)
**Reveals:** the "—A." sender exists in person (unseen); he mailed the prints and words; a ledger exists and outlived the father; one page is now in the group's hands; the sister is coming; the sender forecasts Haru's behavior.
**Does NOT reveal:** the sender's identity or face; the ledger's location; the party the file concerns; the Beneficiary/Accountant titles; the trust; why the page was torn or by whom; Jae-Ho's survival.

## Spoiler check (writer reference)
- Pays: C-02 (docks text answered), C-04 (both prints claimed), C-09 ("the water" line).
- Plants: C-10 (torn page — signature block pays M5; torn edge pays M15: the Accountant keeps the rest), the forecasting motif (pays M13: "He isn't offering you control. He's pricing your silence"), the north-gate lesson (pays M17: the room where he watches the water).
- The thermos-two-cups staging detail is the Accountant's professional courtesy — writer note: it is also a message to any watcher who later reviews the pier: *he came to talk*. Marsh documents his own meetings. That habit is M14's bait structure in miniature.
- Audit (clue-schedule rule 1): every claim the voice makes is checkable later — the prints (C-01/C-04), the grave words (C-05 context), the ledger's existence (C-10/M15). He confesses *authorship*, never *identity*, and never the conspiracy's shape.
