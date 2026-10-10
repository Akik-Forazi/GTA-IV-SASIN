# ACT I — MISSION 1: "The Return"

## Mission Overview
**Placement:** Act I, Mission 1 of 3  
**Dramatic Objective:** Haru returns to Liberty City via anonymous photograph; reconnects with Niko and Roman; establishes the monitoring threat that will drive the campaign.  
**Why It Matters Now:** This is the inciting incident — Haru's return kicks off the entire conspiracy. The photograph is the first clue; the monitoring tells Haru he's not alone in his pursuit.  
**Character Conflict:** Haru's controlled demeanor vs. the visceral emotion of returning home; Niko's reluctant re-entry guarded by protective guilt; Roman's innocent enthusiasm contrasting with undercurrent of danger.  
**Gameplay Variety:** Walking navigation, optional taxi ride with Roman, text message reception, safehouse arrival.

## Opening Cinematic (Narrative Description)

**[SCENE: INTERNATIONAL ARRIVALS — BO HANN, LIBERTY CITY — NIGHT]**

Rain falls on the tarmac. HARU (30s, composed, wearing a suit that feels slightly out of place in the rain) steps off the private jet, carrying only a briefcase and a duffel bag. He pauses, looking around — Liberty City after ten years away. His phone buzzes. A single anonymous text appears on screen:

> **THEY'RE WATCHING. MEET ME AT THE DOCKS. —A.**

Haru checks the message. His eyes shift left — a parked black sedan a few spaces down. A figure inside watches him. The window rolls down slightly. Not enough to see inside. Just enough to confirm someone's there.

**[CAMERA: Tracking shot follows Haru as he exits the terminal, passes through customs (minimal — he has no luggage), and steps into the rainy Liberty City night. The camera lingers on his face as he checks the message, then looks around — the observing car is still there. Someone is definitely watching him.]

**[ACTION: Player gains control of Haru. He can walk to a waiting taxi or call one. Roman's taxi company is visible at the curb.]

## Dialogue

**HARU (to himself, quiet):**  
"Liberty City. Home. After ten years... it feels like a different country."

**[SUBTITLE: HARU]**

**HARU (CONTINUED)**  
(dialing a number)  
"Niko? It's me. I'm... I'm back."

**NIKO (V.O.)**  
"Haru. You sound... different. Why are you calling?"

**HARU**  
"I got a photograph. Anonymous. Of the warehouse. Where it happened. I didn't know where else to go. I needed someone who was there. Someone who wouldn't lie to me."

**NIKO (V.O.)**  
"Warehouse. You mean the—"

**HARU**  
"The one your friend's bodyguard supposedly died in. Yes. Niko, I need to know what really happened. Who had a reason to kill my family?"

**NIKO (V.O.)**  
"...I haven't thought about that night in a long time. Why now?"

**HARU**  
"Because whoever had the photograph knew I was coming. Someone's been watching me for months. I could feel it at the airport. They're still here, Niko. In this city."

**[CAMERA: Quick cut as Haru ends the call, looks over his shoulder — the taxi at the curb has been waiting. The driver glances in the rearview mirror a moment too long.]

**NIKO (V.O.) (CONT'D)**  
"Roman's still here. He'd be glad to see you. But Kate... be careful what you wish for."

**HARU**  
"Roman knows what happened. He deserves to know I'm back. Please, Niko. Meet me. At the safehouse. Please."

**NIKO**  
"I'll be there. But Haru... some doors, once opened, don't close nicely."

**[MISSION OBJECTIVE ADDED: "Meet Niko at the safehouse in Bohan."]**

**[SCENE TRANSITION — RAINY STREETS OF BO HANN, NIGHT]**

## Gameplay Flow

1. **Player controls Haru** walking from arrivals to taxi stand  
2. **Optional:** Call Roman's taxi (FACTION TAXI) or walk through the streets  
3. **If Roman's taxi:** Roman greets Haru enthusiastically, talks about Niko, mentions Kate's memory with bittersweet tone. He's oblivious to the threat monitoring Haru.  
4. **If walking:** Haru navigates streets, may encounter normal pedestrian traffic for atmosphere  
5. **Player receives text message from Niko** — "Safehouse, Bohan. —N."  
6. **Haru proceeds to safehouse** (waypoint appears on minimap)

## Character Beats

- **Haru:** Economical with words, controlled demeanor; surprise at returning home; underlying anxiety about being watched (not yet articulated even to himself)  
- **Roman:** Warm, talkative; misses Niko; mentions Kate's memory with bittersweet tone; oblivious to the threat monitoring Haru — he just wants his brother back  
- **Niko:** Guarded, practical; reluctant but obligated; the concealed evidence hangs between him and Haru like an unspoken tension — he's protecting Haru, but Haru doesn't know why yet  
- **Mandu:** Not yet introduced — will enter in Mission 2

## Escalation & Complication

- **Haru arrives and immediately senses he's being watched** (camera lingers on the observing car; the driver's lingering glance)  
- **The anonymous photograph creates an immediate mystery** — who sent it and why? What do they want?  
- **Niko's hesitant reunion creates emotional friction** — Haru feels Niko withheld information he needed; Niko feels protective guilt about Kate's death and what he concealed  
- **Roman's innocent enthusiasm contrasts with the undercurrent of danger** — he's talking about how much he missed Niko, not understanding the storm coming  
- **Text from Niko provides a goal but also a warning** — "some doors don't close nicely" plants the seed that Niko knows something he's not saying

## Mission Ending

**[SCENE: SAFEHOUSE INTERIOR — BO HANN, NIGHT]**

HARU enters the modest safehouse. NIKO is already there, leaning against the window, looking out at the rainy city. ROMAN is there, talking animatedly about something trivial — maybe how much he missed Niko, maybe something about the taxi business.

**ROMAN**  
"Haru! My brother! You are back! We have so much to discuss! Kate would have wanted you to return, yes? To see how Roman is doing!"

**HARU (nodding briefly)**  
"Roman. Niko. I'm back. And I have questions. But first — we need to talk about why I really came back. The photograph... it wasn't random, was it? Someone sent it for a reason. Someone who's been watching me for months."

**NIKO**  
"Everyone has their reasons, Haru. Some are... harder to face than others."

**ROMAN**  
"Is everything okay? You look like you've seen a ghost. Or perhaps — is this about the business? The family empire? I tried to protect you both, you know. I—"

**[CAMERA: Quick cut to Haru's face — Roman's words hit close. Haru doesn't respond. Niko places a hand on Haru's arm — a silent warning.]**

**[MISSION STATUS: "The Return Complete"]**

**[OBJECTIVE MARKER: TALK TO NIKO AND ROMAN AT THE SAFEHOUSE]**

## Technical Implementation Notes

- **Safehouse:** Existing GTA IV safehouse interior (use multi-apt or safehouse property already in the game)  
- **Niko's presence:** Scripted companion NPC for this mission only  
- **Roman's presence:** Scripted companion; his taxi company business is canon-compliant (Roman's Taxi)  
- **Rain effect:** Optional atmospheric layer; does not affect gameplay but sets tone  
- **Phone model:** Existing GTA IV "cellphone" asset for text messages  
- **No custom vehicles or weapons required** — use existing GTA IV assets  
- **LuaModLoader compatibility:** Uses existing native functions for text, objectives, peds, and cutscene control  
- **Cutscene triggers:** Standard GTA IV mission triggers (player near marker, etc.)

## Continuity Restrictions

- **Roman survives** (Revenge ending) — he is present and alive in this mission  
- **Kate died** — referenced in Niko's dialogue, mourned but not physically present  
- **Niko's concealed evidence** is alluded to but not revealed yet ("some doors don't close nicely")  
- **Haru's visual basis:** Luis Lopez character model (per user decision), but Haru has his own dialogue and personality distinct from Luis  
- **Setting:** Post-GTA IV Liberty City, Bohan district safehouse  
- **No contradictions** with established GTA IV timeline  
- **Revenge ending continuity preserved:** Roman alive, Kate dead

## Spoiler Check (Player-Facing)

**Reveals in this mission:**  
- Haru arrived in Liberty City  
- He has a safehouse  
- He found an anonymous photograph  
- He contacted Niko  
- Roman is waiting at the safehouse  
- Someone is monitoring Haru's return

**Does NOT reveal:**  
- Who sent the photograph  
- Who is monitoring Haru  
- The intermediary's identity  
- The nature of Operation Black Ledger  
- The father's involvement  
- Beneficiary's identity  
- Why the evidence resurfaces now  
- Mandu's role (Mission 2+)  
- Niko's concealed fragment (hinted at, not described)

## Spoiler Check (Full Chronology — Writer Reference)

**This mission plants:**  
- Anonymous photograph (will be investigated throughout Act I)  
- Niko's reluctant re-entry and guarded demeanor  
- Roman's presence and innocent enthusiasm  
- Sense of being watched (payoff later)  
- Haru's motive for returning  

**Does NOT reveal:**  
- Who the intermediary was  
- What the network was (Operation Black Ledger)  
- Father's involvement or compromise  
- Beneficiary's identity  
- Why the evidence resurfaces now  
- Mandu's role or personal stakes  
- Niko's exact concealed fragment (only hinted)  
- How Haru and sister survived the massacre  

---