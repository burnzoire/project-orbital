# Scenario: Surface Expedition

## Narrative
The survey drone went down nine days ago. It was mapping the subsurface geology of the Komarov Basin when its telemetry cut out mid-transmission — the last data burst showed it nose-down in a ravine sixty-two kilometers east of the outpost, its sample core intact and its recorder full. Nine days of high-resolution seismic and mineral composition data, the kind that takes months to recollect. The kind that determines whether this moon justifies a permanent mining installation or gets written off as a dead rock. Nobody is sending another drone. The launch window for the supply ship closes in eleven days. You need that data.

So you load the rover. Four people, eight days of consumables, a route plotted through terrain that satellite imaging can only partially resolve. The first two days go well enough. The ground is hard-packed regolith, visibility is tolerable, the rover handles the low gravity with its usual sluggish compliance. Then the dust comes. Not a storm exactly — more like the moon exhaling. Electrostatic regolith lifted by thermal cycling billows across the flats in sheets so fine it looks like fog, except it coats every surface, clogs every filter, and carries enough charge to scramble unshielded electronics. Your forward sensors go intermittent. The nav system starts disagreeing with the terrain. You slow down and push through.

On day three, the rover drops its left front wheel into a subsurface void — a lava tube ceiling that looked solid on the surface but was hollow underneath. The axle snaps. The suspension frame is bent. The rover is not moving again without hours of fabrication work, and you don't have a fabrication bench. You have hand tools, patch materials, a limited power supply, and a team that's been breathing canned air for three days. The drone crash site is still thirty-one kilometers east. Behind you is the outpost, thirty-one kilometers west. You are equidistant from safety and objective, standing on a moon that wants you dead, and the math on your consumables just got very uncomfortable.

You can try to repair the rover with what you have — a long shot, but mobile shelter is worth a lot out here. You can leave the rover and continue on foot, carrying what you can, knowing that an EVA traverse at this distance will push your suits to their absolute limits. You can split the team — two forward, two back — halving your margin for error but covering both options. Or you can abort, turn around, walk home, and explain why the data is still sitting in a ravine. Every option has a cost. The dust doesn't care which one you choose.

## Setting
- **Location type**: moon surface / hostile terrain
- **Scale**: personal / small team
- **Tone**: survival, exploration

## Player Agency
- **Assess the rover damage**: Inspect the axle and suspension to determine if a field repair is even feasible — this costs time but informs every subsequent decision
- **Attempt rover repair**: Commit hours and materials to jury-rigging the axle using hand tools and structural patch stock — success is uncertain and depends on crew skill and remaining power for tools
- **Continue on foot**: Abandon the rover and load essential supplies into suit packs for a multi-day foot traverse across thirty-one kilometers of uncharted terrain in low gravity
- **Split the team**: Send two crew forward to the drone while two return to the outpost for help — each pair carries half the margin and neither can rescue the other if something goes wrong
- **Abort the mission**: Turn the entire team around and walk back to the outpost — the safe option, but the data is lost and the mining survey with it
- **Manage consumables**: Ration oxygen, water, battery, and suit filters across the team — every hour of work or travel burns resources, and the dust accelerates filter degradation
- **Choose route segments**: Pick paths based on terrain scans — ridgelines offer firmer ground but higher radiation exposure, valleys are sheltered but risk more subsurface voids
- **Manage crew condition and morale**: Monitor fatigue, stress, and injury across the team — push too hard and someone makes a mistake; go too easy and the consumables run out

## Resolution Paths
- **Best**: Rover repaired or bypassed creatively, team reaches the drone, recovers the data core, and returns to the outpost with consumables to spare — the geological data secures the mining installation and the team earns a reputation for surface competence
- **Good**: Team reaches the drone on foot after abandoning the rover — data recovered, but the return trip is a razor-thin consumable margin, one or more crew arrive back dehydrated, exhausted, and filter-depleted
- **Mixed**: Team splits — the forward pair recovers the data but the return pair encounters trouble (injury, dust event, navigation error), requiring a rescue sortie from the outpost that strains colony resources
- **Bad**: Attempted repair fails and wastes hours of consumables — team is forced to abort with less margin than they would have had if they'd turned around immediately, limping back to the outpost with nothing to show for it
- **Worst**: Team pushes forward on foot into worsening conditions, consumables run critical, a crew member collapses — emergency beacon activated, full search-and-rescue response required, data unrecovered, personnel casualties possible

## Required Simulation Systems

### Surface Environment
- **Purpose**: Simulates the moon's hostile surface conditions — electrostatic dust, thermal cycling, radiation belts, subsurface geological hazards, and low gravity — as an active antagonist shaping every decision
- **Key State**: Regolith dust density (electrostatic charge level, filter clogging rate, sensor degradation), surface temperature (extreme diurnal cycling from frozen to scorching), radiation flux (varies by elevation and terrain shielding), terrain stability (subsurface void probability per grid cell, load-bearing ratings), gravity level (affects movement speed, carry capacity, fatigue curve), visibility (dust opacity, horizon distance), seismic micro-tremor frequency
- **Player-facing**: Dust density indicator filling suit filter gauges, temperature warnings on HUD during thermal transitions, radiation dosimeter with zone-based alerts when traversing ridgelines, terrain stability overlay on nav map (color-coded confidence from solid to suspect to unknown), visibility range shrinking during dust events, ground-penetrating scan results when available

### EVA & Spacewalk
- **Purpose**: Simulates extended surface EVA — suit integrity, consumable budgets, physical endurance, and the compounding toll of multi-day operations in a sealed suit far from shelter
- **Key State**: Suit oxygen reserve (per crew member), CO2 scrubber filter saturation (degrades faster in dust), battery charge (powers HUD, comms, heating, tools), water supply (drinking reservoir in suit), thermal balance (radiative cooling vs. solar heating vs. exertion heat), suit seal integrity (dust abrasion on joints and seals), boot traction rating (varies with terrain), glove dexterity (degrades with cold and fatigue), helmet visor condition (dust scoring reduces visibility), fatigue accumulation (multi-day EVA is qualitatively different from a short excursion)
- **Player-facing**: Per-crew consumable dashboard showing oxygen, filter life, battery, and water as declining bars, suit integrity warnings when seals degrade, visor clarity indicator, movement speed modifier displayed when fatigued or on difficult terrain, breathing audio and heartbeat intensifying with exertion, filter clog warnings when dust density is high

### Equipment & Repair
- **Purpose**: Simulates the rover's mechanical state, available repair tools and materials, and the feasibility of field repairs under adverse conditions
- **Key State**: Rover damage assessment (axle broken, suspension bent, wheel lost in void), available tools (hand wrenches, power driver with limited battery, structural adhesive, patch plates, spare cable), repair feasibility score (function of damage severity, available materials, worker skill, environmental conditions), power tool battery drain, repair time estimate, structural integrity of repair (field fix vs. proper shop repair — a patched axle may hold for ten kilometers or fail after two)
- **Player-facing**: Rover damage schematic highlighting broken components, repair options menu with estimated time, material cost, and success probability, tool battery gauge, "repair quality" indicator showing how robust the fix is likely to be, warnings when attempting repairs beyond available skill or materials

### Navigation & Fuel
- **Purpose**: Simulates route planning across partially mapped terrain, distance tracking, and the energy cost of travel — on foot or by rover
- **Key State**: Distance to objective, distance to outpost, mapped vs. unmapped terrain segments, route options (ridgeline vs. valley vs. direct), elevation profile, estimated travel time per segment (adjusted for gravity, terrain, fatigue, dust), rover fuel/charge remaining (if mobile), waypoint system, GPS-equivalent accuracy (degraded by dust interference), ground-truth vs. satellite-map disagreement
- **Player-facing**: Terrain map with route overlays showing distance, estimated time, and hazard ratings per segment, progress tracker, "point of no return" calculations based on current consumable rates, route comparison tool showing tradeoffs (faster but more exposed vs. slower but sheltered), nav accuracy confidence indicator

### Player Health
- **Purpose**: Tracks the player character's physical and cognitive condition over a multi-day surface expedition with cumulative stress
- **Key State**: Oxygen saturation, hydration level, caloric deficit (no real meals in a suit, only paste tubes), core temperature, fatigue (cumulative over days, not hours), radiation dose (accumulated), muscle strain (low gravity changes the injury profile), cognitive impairment from sleep deprivation and stress, morale
- **Player-facing**: Health panel with trending indicators (getting worse vs. stable vs. recovering), fatigue debuffs affecting movement speed and decision-making, dehydration warnings, radiation dose bar filling toward exposure limits, sleep deprivation effects on HUD clarity (slight blur, delayed responses), stress affecting dialogue options

### Medical & Injury
- **Purpose**: Simulates injuries sustained during the expedition — falls into voids, suit breaches from sharp regolith, overexertion injuries, and the severe constraints of treating wounds inside a sealed suit in the field
- **Key State**: Injury type per crew member (sprain, laceration from regolith, blunt trauma from rover incident, hyperthermia, hypothermia, radiation sickness), injury severity, bleed rate (if applicable), treatment options (suit-compatible first aid only — no surgery, no IV, limited splinting), pain level (affects performance), infection risk (dust contamination of wounds), medical supply inventory (bandages, analgesics, anti-radiation meds, stimulants)
- **Player-facing**: Crew health panel with injury markers, treatment interface limited to field-viable options, pain indicators affecting crew performance ratings, medical supply inventory with usage projections, warnings when injuries worsen without treatment

### Communications
- **Purpose**: Simulates radio contact with the outpost and between team members — degraded by distance, terrain occlusion, dust interference, and power limitations
- **Key State**: Signal strength to outpost (drops with distance and terrain), inter-team radio range (critical if team splits), dust interference level, line-of-sight to relay (if any), antenna power draw, message latency, emergency beacon status and battery, last confirmed contact timestamp
- **Player-facing**: Signal strength bars, periodic static and dropout during dust events, comm range circles on the map showing where contact will be lost, relay options (climb a ridge to get line-of-sight at the cost of radiation exposure and time), emergency beacon activation option with estimated response time

### NPC Identity & Personality
- **Purpose**: Gives each expedition crew member distinct skills, tolerances, and personalities that affect their usefulness, resilience, and behavior under sustained pressure
- **Key State**: Name, specialization (geologist, mechanical engineer, medic, survey technician), physical fitness rating, dust tolerance, stress threshold, risk appetite (cautious vs. bold), trust in player leadership, opinion on current plan (voiced in dialogue), fatigue tolerance, interpersonal dynamics (who steadies whom, who cracks first under pressure, who argues)
- **Player-facing**: Crew roster with skill tags and condition indicators, dialogue reflecting each crew member's opinion of the plan (the engineer wants to fix the rover, the geologist wants to push forward, the medic wants to abort), visible behavioral changes as stress accumulates (shorter replies, hesitation, irritability), trust indicators shifting based on outcomes of player decisions

### Task & Workforce Management
- **Purpose**: Simulates the allocation of a tiny team across competing priorities — repair work, travel, scouting, medical care, rest — where every assignment has a direct opportunity cost
- **Key State**: Active task list (rover repair, forward traverse, return traverse, route scouting, medical treatment, rest cycle, equipment maintenance), crew assignment per task, task duration estimates, skill match quality, simultaneous task limit (four people, many needs), rest requirement (multi-day expedition demands sleep rotations)
- **Player-facing**: Task board showing active and pending work, crew assignment slots, time estimates that shift based on who is assigned, warnings when critical tasks are unattended, rest schedule showing who needs sleep and when, opportunity cost projections (if you repair for six hours, you travel zero kilometers and burn six hours of consumables)

### Sensors & Scanning
- **Purpose**: Simulates the ability to survey terrain ahead, detect subsurface hazards, locate the drone crash site, and assess environmental conditions at range
- **Key State**: Ground-penetrating radar status (handheld unit, limited battery), terrain scan resolution (degrades with dust), drone crash site beacon signal (faint, intermittent), subsurface void detection range, radiation mapping capability, dust density measurement, sensor battery drain rate
- **Player-facing**: Terrain scan overlay on nav map showing void risk zones, drone beacon direction and signal strength indicator, radiation heat map for route planning, sensor battery gauge, scan quality warnings when dust is heavy, "blind spots" clearly marked on the map where no scan data exists

### Time Pressure
- **Purpose**: Simulates the converging deadlines — consumable depletion, supply ship launch window, worsening surface conditions, and crew endurance limits — that force the player to act rather than deliberate indefinitely
- **Key State**: Hours of oxygen remaining per crew member, hours of filter life remaining, hours of battery remaining, days until supply ship window closes (data must be transmitted before then), estimated hours to reach drone site, estimated hours to return to outpost, dust storm probability forecast (worsening over next 48 hours), crew endurance ceiling before mandatory rest
- **Player-facing**: Multi-timer dashboard with consumable countdowns per crew member, supply ship deadline countdown, weather forecast overlay showing dust probability rising, "feasibility window" calculation showing whether the current plan can physically be completed before consumables expire, point-of-no-return markers on the map based on current burn rates

## System Dependencies

### Hard Dependencies
- `EVA & Spacewalk` --depends on--> `Surface Environment`: suit consumable burn rates, filter degradation, thermal load, and seal wear are all driven by surface conditions — dust density, temperature, and radiation directly determine how fast suits deteriorate
- `Navigation & Fuel` --depends on--> `Surface Environment`: route viability depends on terrain stability, visibility, and radiation exposure — the environment defines what paths are survivable
- `Navigation & Fuel` --depends on--> `Sensors & Scanning`: route planning requires terrain scan data — without functioning sensors, the team is navigating blind into potential void fields
- `Equipment & Repair` --depends on--> `EVA & Spacewalk`: all repair work happens in suits on the surface — glove dexterity, tool power, and environmental exposure during repair are governed by EVA conditions
- `Communications` --depends on--> `Surface Environment`: dust interference and terrain occlusion directly degrade signal quality — the environment controls whether you can talk to the outpost

### Soft Dependencies
- `Player Health` ~~depends on~~> `EVA & Spacewalk`: multi-day suit confinement accumulates fatigue, dehydration, and stress far beyond short EVA norms
- `Player Health` ~~depends on~~> `Surface Environment`: radiation exposure and thermal stress from the environment compound the toll on the player's body
- `Medical & Injury` ~~depends on~~> `EVA & Spacewalk`: treatment options are severely constrained inside a sealed suit — field medicine in a pressure suit is barely medicine at all
- `Medical & Injury` ~~depends on~~> `Surface Environment`: dust contamination of wounds increases infection risk; thermal extremes worsen hypothermia and hyperthermia injuries
- `NPC Identity & Personality` ~~depends on~~> `Player Health`: crew morale and trust erode when they see the leader deteriorating — a visibly exhausted commander inspires less confidence
- `Task & Workforce Management` ~~depends on~~> `NPC Identity & Personality`: crew skill, fatigue, and willingness determine what tasks can be assigned and how effectively they're performed
- `Sensors & Scanning` ~~depends on~~> `EVA & Spacewalk`: sensor equipment draws from suit power; operating the ground-penetrating radar requires stopping, deploying, and scanning — all of which cost time and battery
- `Time Pressure` ~~depends on~~> `EVA & Spacewalk`: consumable depletion rates set the master clock — every timer on the board is ultimately counting down suit resources
- `Equipment & Repair` ~~depends on~~> `NPC Identity & Personality`: repair quality depends on the assigned crew member's mechanical skill — the geologist with a wrench is not the same as the engineer with a wrench

### Feedback Loops
- `Surface Environment` <-> `EVA & Spacewalk`: Worsening dust conditions accelerate filter clogging and seal wear, which forces slower travel to conserve consumables, which extends exposure time to the worsening conditions. The environment degrades the suits; degraded suits force longer exposure to the environment.
- `EVA & Spacewalk` <-> `Player Health` <-> `Task & Workforce Management`: Suit confinement accumulates fatigue; fatigue slows movement and work; slower progress means more hours in suits means more fatigue. Crew members forced to work while exhausted make mistakes, which create new problems (injuries, equipment damage) that consume more time and resources.
- `Navigation & Fuel` <-> `Sensors & Scanning` <-> `Time Pressure`: Scanning terrain costs battery and time. Skipping scans saves both but risks walking into a subsurface void. Falling into a void costs far more time and resources than the scan would have — or it doesn't, and the scan was wasted. The player must gamble between thoroughness and speed with no way to know which was the right call until it's too late.
- `Communications` <-> `NPC Identity & Personality` <-> `Time Pressure`: Losing contact with the outpost increases crew anxiety. Anxious crew members argue more about the plan and work less efficiently. Lost efficiency extends the mission. A longer mission means more time out of comm range. If the team splits, communication between pairs degrades with distance, and each group makes decisions the other can't influence.
- `Equipment & Repair` <-> `Time Pressure` <-> `Navigation & Fuel`: Hours spent repairing the rover are hours not spent traveling, and consumables burn regardless. But a working rover covers ground faster and carries more supplies, potentially buying back more time than the repair cost. The gamble is whether the repair succeeds and whether the patched axle holds — a failed repair wastes the time twice over.

## Emergent Possibilities
- The player decides to repair the rover and assigns the engineer to the axle. Six hours later, the fix is holding but marginal — the engineer rates it at maybe twenty kilometers before it fails again. Twenty kilometers gets you to the drone but not back. The player now faces a second decision layered on top of the first: drive to the drone knowing the rover will die there and you'll walk back, or accept the repair was a sunk cost and abort. The consumables burned during the repair have narrowed every remaining option.

- The player splits the team — two forward, two back. On day four, the forward pair crests a ridge and gets a clear line-of-sight comm window to the outpost, only to learn that the return pair triggered a subsurface collapse two kilometers from the rover and one of them has a broken ankle. The outpost is scrambling a rescue but it's twelve hours out. The forward pair has the medical supplies. They're closer to the injured crew than the outpost is. Do they turn back to help, abandoning the drone site eight kilometers ahead, or push forward trusting the outpost rescue to arrive in time?

- A dust event rolls in heavier than forecast, dropping visibility to near zero and saturating suit filters at triple the normal rate. The team shelters behind a rock outcrop, burning consumables while stationary. When the dust clears four hours later, the nav system has drifted — the terrain ahead doesn't match the satellite map. The ground-penetrating radar reveals the "clear path" on the map is actually a field of shallow lava tube ceilings. The team must reroute through a narrow canyon that adds eleven kilometers and passes through a radiation belt, or attempt to pick through the void field using manual scanning at a crawl. Neither option was in the original plan. Both will push consumables past the comfortable margin.

## Inspiration
- *The Martian* (Andy Weir) — the arithmetic of survival on a hostile world, where every resource is finite and every decision has a calorie cost
- *The Expanse* (James S.A. Corey) — surface expeditions on alien moons with real suit limitations, dust hazards, and the loneliness of being far from shelter
- *Death Stranding* (game) — the grueling physicality of traversing hostile terrain on foot, where the landscape itself is the antagonist and every step is a risk calculation
- *Moon* (film) — the oppressive isolation and quiet hostility of a lunar surface that is indifferent to human survival
- *Prospect* (film) — a small team on an alien moon surface with finite resources, decaying equipment, and a salvage objective that may not be worth the cost of reaching it
