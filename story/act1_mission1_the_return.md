# ACT I — MISSION 1: "The Return"

**Revision 2 (2026-10-11).** Fixes: coherent photograph chain (print #1 in hand; docks text declined), Francis International Airport (not "BO Hann"), Roman's canon family (Mallorie, daughter), Kate past-tense guard, Niko knowledge bounds, causal logic (no premature conspiracy names).

## Mission Overview
- **Placement:** Act I, Mission 1 of 4. **Dramatic objective:** the inciting incident — Haru returns carrying print #1, declines the first lure, and re-bonds with Niko and Roman while the watchers log his arrival.
- **Why now:** the photograph forced the return (chronology C3); the watchers' presence tells Haru (and the player) that his arrival is already priced in.
- **Character conflict:** Haru's controlled demeanor against the visceral fact of being home; Niko's guarded relief and ten years of unspoken knowledge; Roman's warmth pulling the scene toward family while danger circles it.
- **Gameplay variety:** walking navigation, optional Roman taxi ride, phone scenes, safehouse arrival. No combat — a tone-setter.

## Opening cinematic

**[SCENE: FRANCIS INTERNATIONAL AIRPORT — INTERNATIONAL ARRIVALS — EVENING, LIGHT RAIN]**

HARU (33, composed, one suitcase, one worn leather document case) comes down the arrivals corridor. He is not sightseeing; he is scanning. His phone buzzes.

> **SMS — UNKNOWN:** THEY'RE WATCHING. MEET ME AT THE DOCKS. —A.

Haru reads it twice. His eyes move to a parked sedan past the taxi rank: engine off, wipers mid-cycle, a silhouette inside. Not hiding. *Logging.*

**[CAMERA: tracking shot through arrivals; hold on Haru's face as he pockets the phone without replying; slow push-in on the sedan as the wiper completes one arc — the silhouette does not move.]**

**[INSERT — HARU'S DOCUMENT CASE, opened on his knee earlier at the gate: the photograph. Grainy, ten years old, a warehouse night. A suited figure at the door. A typed strip beneath it: "IT WAS A CONTRACT. ASK NIKO BELLIC WHO STOOD AT THE DOCKS... " — final words cut by the fold. The player has seen it; no name is given.]**

*(Writer note: the typed strip is the player's only text on print #1. It plants C-01 without naming anyone.)*

**[ACTION: player gains control at the taxi rank. Objective: reach the safehouse in Bohan. Waypoint set.]**

## Dialogue

**HARU** (quiet, to himself): "Ten years. The rain's the same. Everything else is a different country."

**[Player may hail a cab. Roman's number is the only contact marked FAMILY.]**

**HARU** (phone to ear, watching the sedan's mirror in the terminal glass): "Niko. It's Haru."

**NIKO (V.O.)** — a silence first, long enough to be an answer. "…You're supposed to be in Rotterdam."

**HARU** "I was. Then I got a photograph in the mail. No note, no name — just the warehouse. The night. Niko, I need to know who stood at the door."

**NIKO (V.O.)** "Some doors, once opened, don't close nicely. I told your father that. I'll tell you."

**HARU** "You told him. So you were there. Meet me."

**NIKO (V.O.)** "…Roman's depot first. He'll have driven everyone crazy pacing. Then we talk. And Haru — come alone, leave the photograph locked up. Don't show it to anyone."

**HARU** "Why?"

**NIKO (V.O.)** "Because a photograph like that is a lit match. And Liberty City is dry."

**[CALL ENDS. SUBTLE BEAT: the sedan's headlights come on as Haru steps to the curb — then go off again. The player has seen it; Haru half-sees it.]**

## Gameplay flow
1. **Taxi or walk** to Bohan (waypoint). If the player takes a random cab, ambient radio and skyline establish the city; if they call Roman's number, see 2.
2. **Optional — Roman pickup:** ROMAN arrives personally in a depot cab, delighted, talkative. He mentions Mallorie picked up their daughter from her cousin's; he mentions — without alarm — a new "corporate account" booking depot cabs at odd hours ("more money than sense, this client — he pays in cashiers' checks!"). *(Seed C-15/M8. No suspicion.)*
3. **Mid-ride event:** the sedan from the airport passes once, same lane, three cars back. Roman doesn't notice. The radio weather reports rain through the week. *(The player may look — the car is scripted, not interactive; no wanted level.)*
4. **Arrival — Bohan safehouse (existing apartment interior):** the evening scene below.

## Safehouse scene (mission ending)

**[SCENE: SAFEHOUSE — BOHAN — NIGHT]**

Roman talks; Niko stands at the window with his back to the room, which is how Niko says things. On the table, a pot of Roman's coffee, which is a crime in itself.

**ROMAN** "—so the depot is *fine*, better than fine, we have a corporate account now, very fancy people, they pay on time which in this city is practically a marriage proposal—"

**NIKO** (not turning) "Roman."

**ROMAN** "Right. Serious faces. Serious faces."

**HARU** (sets the document case on the table, doesn't open it) "I came back because of what happened in 2009. Not to mourn. To find out who bought it."

**NIKO** (turning now) "'Bought.'"

**HARU** "Crews like that don't volunteer. Someone contracted the warehouse. I intend to find who signed."

A silence. Roman looks between them like a man at the wrong dinner table.

**NIKO** (carefully) "You say 'who.' Not 'why.' That's a dangerous word order, Haru."

**HARU** "It's the only one I trust. 'Why' can be lied to. 'Who' has to be *paid*."

**NIKO** (beat; almost a smile, gone at once) "You sound like him. Your father. He used to say the ledger never flatters."

**ROMAN** "Okay — good news: nobody is signing anything tonight, because my sister-in-law says I stress-eat when you two do this, and *I* say we eat anyway. Haru — you're home. Whatever this is… we do it with full stomachs, yes?"

**HARU** (to Niko, quietly) "I didn't answer a message tonight. Someone offered me a meeting I didn't take. When they offer again — I'd like you there."

**NIKO** (a long look; the guilt the player can't read yet) "…You'll have me."

**[MISSION COMPLETE: "The Return"]**

## Escalation & complication
- The photograph forces the return; the declined docks text means the sender must adapt (M4's "I'll bring the water to you").
- The watcher sedan is *logging*, not hunting — patient surveillance, the campaign's first read of the enemy's method.
- Niko's dialogue performs knowledge without confessing it ("You told him. So you were there") — bounded by his profile (witnessed ≠ concluded; he volunteers nothing).
- Roman's corporate account seed pays off in M8; his warmth is the scene's gravity, not comic relief.

## Failure / retry handling
- No fail states. If the player ignores waypoints for 10 minutes, Roman calls with directions (in-character, no punishment).

## Technical implementation notes
- **Locations:** Francis International Airport arrivals exterior (existing), Bohan street network, existing Bohan apartment interior as safehouse. All vanilla assets.
- **Sedan:** scripted ambient vehicle with parked + drive-past states; no AI pursuit.
- **Phone:** native text/call presentation; "UNKNOWN" sender label.
- **Photograph:** 2D texture overlay on the case insert; also visible full-screen during the insert shot.
- **Rain:** weather script state for the act; no physics impact.
- **Runtime:** all staging via loader-layer scripting (LuaModLoader candidate; see `docs/technical-architecture.md`). Cutscene camera paths use the runtime's cinematic primitives **once verified on 1.2.0.59 (UNVERIFIED — PoC, docs/poc-cinematic-plan.md)**.
- **No custom vehicles/weapons.**

## Continuity restrictions (hard)
- **Kate:** past tense only; she is referenced via Niko's careful silences, never named casually. No Deal-ending implications anywhere.
- **Roman:** alive; married to Mallorie; young daughter exists (named Kate, P-1.18); he is warm and observant, never a plot hostage in this mission.
- **Niko:** recognizes the warehouse from the photograph; does NOT mention any phone, any name, any "beneficiary." His warnings are proverbial, not factual.
- **Setting:** spring 2019; massacre was March 2009 (P-3.1). Haru was abroad ten years; the "Rotterdam" line matches his logistics cover.
- **No character uses the words "Beneficiary," "Accountant," or "ledger" in this mission.**

## Spoiler check (player-facing)
**Reveals:** Haru returned; the photograph exists and shows a suited figure; Niko was present in 2009; watchers are logging the return; a "—A." lure exists and was declined; Roman has a new corporate account.
**Does NOT reveal:** who "—A." is; the sender of the photograph; the Beneficiary; the Accountant; the ledger/trust; Jae-Ho's survival; Niko's burner; why the evidence resurfaces.

## Spoiler check (writer reference)
- Plants: C-01 (print #1), C-02 (docks text), C-03 (watcher sedan), C-15 seed (Roman's account).
- The typed strip's cut-off sentence is deliberate: the full line (M11's burner echo "ACCOUNT CLEARS FRIDAY. THEN THE BROOM.") must never be guessable from here.
- Niko's "he used to say the ledger never flatters" is the campaign's only ledger mention before M4 — a private memory, not information transfer. Audit note: allowed because Niko heard the phrase from Tae-joon (chronology A2); he is not revealing the ledger's existence.
