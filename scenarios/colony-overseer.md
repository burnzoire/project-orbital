# Scenario: Colony Overseer

## Narrative
You weren't supposed to be in charge. The colony director took a shuttle to the orbital relay three days ago for a "routine coordination meeting" and hasn't come back — comms say weather delay, but the subtext is politics. The deputy director is in the medical bay with a kidney stone that won't pass. That leaves you: the operations coordinator, third in a chain of command that was never meant to reach this far down. Congratulations. You're the acting overseer of Shackleton's Promise, a forty-person terraforming colony on the dusty plains of Titan's largest co-orbital, and everything is broken at the same time.

The morning brief lands on your desk like a brick. Power output is down eighteen percent because the regolith dust has coated the solar array again — the panels need manual cleaning, but the only crew rated for surface EVA are currently reinforcing the western habitat seal, which has been losing pressure since Tuesday. The water extraction rig in Sector 7 is running hot and needs a technician before the pump seizes, but your best engineer is elbow-deep in the CO2 scrubber overhaul you can't afford to pause. The greenhouse crew is reporting a nutrient imbalance in the root beds that will kill the potato crop within forty-eight hours if nobody recalibrates the feed lines. And the morning shift just told you that two of your surface workers aren't speaking to each other after a fight in the mess hall last night — which means you can't send them out together, which means your already-thin EVA rotation just got thinner.

Every task on your board is urgent. None of them can wait. You don't have enough people to do all of them simultaneously, and every hour you delay one thing, something else gets worse. You can delegate, prioritize, improvise, or roll up your sleeves and do it yourself — but you can't do everything, and the decisions you make about what gets done first will cascade through every system in this colony for days. Welcome to command. Nobody said it would be fun.

## Setting
- **Location type**: surface colony
- **Scale**: local
- **Tone**: management, survival

## Player Agency
- **Prioritize tasks**: Rank competing urgent needs — power, atmosphere, water, food production, structural integrity — knowing that deprioritized tasks will degrade
- **Assign personnel**: Match available workers to tasks based on skill, certification, interpersonal compatibility, and fatigue — not everyone can do every job
- **Do it yourself**: Leave the oversight desk and personally handle a critical task — but lose the ability to coordinate and respond to new crises while in the field
- **Improvise solutions**: Reassign unqualified personnel with supervision, jury-rig temporary fixes, or accept degraded performance to spread coverage
- **Negotiate with crew**: Ask people to work overtime, swap shifts, or take on tasks outside their specialty — but at a cost to morale, trust, and fatigue
- **Accept tradeoffs**: Consciously let a lower-priority system degrade to save a higher-priority one — and own the consequences
- **Defer or batch tasks**: Identify tasks that can safely wait hours (not days) and batch work to reduce transition overhead
- **Restructure operations**: Rethink the shift schedule, cross-train crew, or implement new protocols that improve coverage long-term at the cost of short-term productivity

## Resolution Paths
- **Best**: Triage effectively, delegate well, maintain crew trust — all critical systems stabilized within 48 hours, colony running smoother than before, crew respects your leadership
- **Good**: Most critical issues resolved, one or two non-critical systems degraded but manageable — colony survives your tenure as overseer without permanent damage
- **Mixed**: Keep the colony alive but burn out the crew or sacrifice a non-essential system permanently — you held the line but people resent how you did it
- **Bad**: Misread priorities — one critical system fails (power, atmosphere, water) causing a cascade that takes days to recover from, with lasting consequences for colony viability
- **Worst**: Try to do everything at once, accomplish nothing well — multiple systems fail simultaneously, colony enters emergency mode, outside intervention required, your authority evaporates

## Required Simulation Systems

### Task & Workforce Management
- **Purpose**: Simulates the assignment, scheduling, and tracking of work tasks across a population with limited personnel, varying skills, and competing priorities. This is the core management system — the player's primary interface for running a colony, station, or ship as an overseer rather than a lone survivor.
- **Key State**: Task queue (prioritized list with urgency, required skills, estimated duration, required personnel count), worker pool (available personnel with current assignment, fatigue, skill certifications, interpersonal flags), task progress (per-task completion percentage, quality modifier based on worker skill match), task dependencies (some tasks must finish before others can start), opportunity cost tracker (what's degrading while resources are allocated elsewhere), shift schedule, overtime hours accumulated
- **Player-facing**: Task board interface showing all active and pending tasks with urgency indicators, drag-and-drop crew assignment, estimated completion times that update based on who's assigned, warning flags when unqualified personnel are assigned, degradation alerts for unattended tasks, shift schedule overview, overtime warnings, "what happens if I delay this" projections

### Power Grid
- **Purpose**: Simulates electrical power generation, storage, distribution, and consumption — with solar array performance degraded by environmental fouling
- **Key State**: Solar array output (percentage of capacity, degraded by dust accumulation), stored energy (kWh), generation rate vs. consumption rate, distribution bus status, per-subsystem power draw, load priority queue, dust accumulation rate on panels, time since last cleaning
- **Player-facing**: Power dashboard showing generation vs. consumption trending toward deficit, solar panel efficiency percentage dropping over time, brownout warnings, system shutdown queue if power drops below threshold, "hours until critical" countdown

### Equipment & Repair
- **Purpose**: Simulates the state of colony infrastructure — pumps, seals, scrubbers, feed lines, extractors — and the maintenance and repair actions needed to keep them running
- **Key State**: Component health per system, failure countdown timers, required skill level for each repair, required tools and parts, repair duration estimate, quality of repair (affected by worker skill match), maintenance backlog depth, cascading failure risk
- **Player-facing**: Maintenance board with red/yellow/green status indicators, repair work orders with skill requirements, estimated time to failure for degrading systems, parts inventory, quality warnings when assigning under-skilled workers

### Atmosphere Management
- **Purpose**: Simulates breathable air composition and the CO2 scrubber system that must be maintained to keep it viable
- **Key State**: O2 level, CO2 level, scrubber overhaul progress (partially disassembled — cannot be abandoned without consequences), air quality index, hours until CO2 reaches dangerous levels if scrubber stays offline
- **Player-facing**: Air quality readouts, CO2 trending graph, scrubber status showing "overhaul in progress — do not interrupt," countdown to dangerous CO2 levels

### Food & Water Supply
- **Purpose**: Simulates the colony's food production (greenhouses, hydroponics) and water extraction/recycling infrastructure
- **Key State**: Greenhouse crop health (potato root bed nutrient imbalance), water extraction rig temperature and pump health, water reserves, food reserves, crop failure countdown, nutrient feed line calibration status, daily water production vs. consumption
- **Player-facing**: Greenhouse status dashboard, crop health warnings with countdown to loss, water rig temperature alarm, pump seizure risk indicator, reserves display with days-of-supply

### Habitat Integrity
- **Purpose**: Simulates the structural condition of the colony's pressurized modules — seals, hulls, airlocks, and the slow-leak problem in the western section
- **Key State**: Seal status per section (western habitat losing pressure), pressure leak rate, repair progress on seal reinforcement, structural stress, compartment isolation options
- **Player-facing**: Pressure readings per section, leak rate display, seal repair progress bar, structural warning indicators, compartment isolation controls

### NPC Identity & Personality
- **Purpose**: Gives each colonist persistent skills, certifications, personalities, relationships, fatigue levels, and morale states that determine what tasks they can perform and how well
- **Key State**: Name, skill certifications (surface EVA rated, engineering, agricultural, medical, general labor), personality traits, current fatigue, morale, trust in player leadership, interpersonal relationships (who won't work with whom), stress tolerance, overtime willingness, grievances
- **Player-facing**: Personnel roster with skill badges, fatigue bars, morale indicators, relationship flags (conflict markers between specific pairs), dialogue reflecting opinion of player's decisions, visible behavioral changes under stress or overwork

### Social Dynamics
- **Purpose**: Simulates interpersonal relationships, group morale, and the effects of leadership decisions on crew cohesion — especially critical when asking people to work overtime, take on unfamiliar tasks, or accept unfair-seeming assignments
- **Key State**: Group morale, interpersonal tension map, active conflicts (the two surface workers not speaking), grievance queue, perceived fairness of task assignments, overtime resentment accumulation, leadership confidence rating, mess hall social temperature
- **Player-facing**: Morale indicator, tension alerts between specific crew members, overtime pushback in dialogue, crew members complaining about assignments to each other, leadership confidence rating visible in how readily people accept orders

### Time Pressure
- **Purpose**: Simulates the simultaneous ticking clocks of multiple degrading systems — each task's urgency changes dynamically as the player allocates resources
- **Key State**: Per-task urgency timers (hours until solar panel output causes brownout, hours until CO2 reaches hazard level, hours until potato crop dies, hours until water pump seizes, hours until western seal fails), dynamic urgency recalculation based on assignments and progress
- **Player-facing**: Multi-timer dashboard showing all countdown clocks simultaneously, urgency colors shifting from yellow to orange to red, timers pausing or slowing when crew is assigned, timers accelerating when conditions worsen

### Surface Environment
- **Purpose**: Simulates the conditions on the moon's surface that affect outdoor work — dust, radiation, temperature extremes, low gravity, and limited EVA windows
- **Key State**: Regolith dust accumulation rate, surface temperature, radiation level, daylight/darkness cycle, EVA suit consumable budgets, dust storm probability, surface traverse time between locations, gravity level (affects work speed and fatigue)
- **Player-facing**: Surface conditions panel, EVA window availability, dust accumulation forecast, radiation warnings, traverse time estimates between outdoor work sites, "conditions safe for EVA" status indicator

### Thermal Regulation
- **Purpose**: Simulates heat management within the colony — especially relevant as power drops and heating/cooling systems compete for diminishing energy
- **Key State**: Ambient temperature per module, heating power draw, cooling power draw, thermal balance trending, temperature tolerance thresholds for equipment and crops
- **Player-facing**: Temperature readings per section, thermal warnings when power deficit forces heating/cooling reductions, greenhouse temperature alerts (crops sensitive to cold)

### Player Health
- **Purpose**: Tracks the player's own physical state — relevant if the player leaves the desk to personally handle tasks, or if they're working extended shifts without rest
- **Key State**: Fatigue, stress, sleep debt, caloric intake, cognitive impairment from overwork
- **Player-facing**: Fatigue and stress indicators, cognitive debuffs (slower decision-making, missed details on the task board), physical capability limits if doing manual work, dialogue options becoming more irritable under stress

### Station Administration
- **Purpose**: Simulates the governance context — the player is acting overseer with limited authority, potentially subject to the returning director's judgment, and must maintain legitimacy with the crew
- **Key State**: Player authority level (acting, not permanent), chain of command status (director absent, deputy incapacitated), policy decisions made, crew confidence in leadership, accountability for outcomes when director returns, communication with orbital relay
- **Player-facing**: Authority indicators, crew deference level in dialogue, ability to make policy changes limited by acting status, accountability log of decisions for director's review, comms with director or orbital relay

## System Dependencies

### Hard Dependencies
- `Task & Workforce Management` --depends on--> `NPC Identity & Personality`: task assignments require knowledge of worker skills, certifications, fatigue, and interpersonal constraints
- `Atmosphere Management` --depends on--> `Power Grid`: scrubbers and recyclers require electrical power to operate
- `Atmosphere Management` --depends on--> `Equipment & Repair`: scrubber overhaul is an active repair task that must complete
- `Food & Water Supply` --depends on--> `Power Grid`: greenhouses need powered lighting and climate control; water rig needs powered pumps
- `Food & Water Supply` --depends on--> `Equipment & Repair`: nutrient feed lines and water pumps are mechanical systems requiring maintenance
- `Thermal Regulation` --depends on--> `Power Grid`: heating and cooling systems draw power
- `Habitat Integrity` --depends on--> `Equipment & Repair`: seal repair is a maintenance task requiring skilled labor
- `Power Grid` --depends on--> `Surface Environment`: solar panel output depends on dust accumulation and daylight cycle

### Soft Dependencies
- `Task & Workforce Management` ~~depends on~~> `Social Dynamics`: interpersonal conflicts constrain crew pairing options; morale affects task acceptance
- `Task & Workforce Management` ~~depends on~~> `Time Pressure`: task priority is driven by degradation timers
- `Social Dynamics` ~~depends on~~> `Task & Workforce Management`: perceived unfairness in task assignments degrades morale; overtime requests breed resentment
- `NPC Identity & Personality` ~~depends on~~> `Task & Workforce Management`: fatigue accumulates from assigned work; morale shifts based on assignment quality and fairness
- `Food & Water Supply` ~~depends on~~> `Thermal Regulation`: greenhouse crops are temperature-sensitive; power loss → thermal loss → crop stress
- `Player Health` ~~depends on~~> `Task & Workforce Management`: player doing field work personally accumulates fatigue and loses oversight time
- `Station Administration` ~~depends on~~> `Social Dynamics`: leadership legitimacy depends on crew confidence; poor decisions erode authority
- `Equipment & Repair` ~~depends on~~> `NPC Identity & Personality`: repair quality depends on the skill match of the assigned worker

### Feedback Loops
- `Power Grid` <-> `Everything`: Power deficit degrades all powered systems simultaneously. Atmosphere, food production, water extraction, thermal regulation, and habitat systems all compete for shrinking power. Fixing solar panels requires pulling workers from the systems that are degrading *because* of the power deficit — the cure competes with the symptoms for the same limited resource: people.
- `Task & Workforce Management` <-> `NPC Identity & Personality` <-> `Social Dynamics`: Assigning overtime or unfamiliar tasks increases fatigue and lowers morale. Low morale reduces work quality and speed. Lower quality and speed means tasks take longer. Longer tasks mean more overtime and more strain. Interpersonal conflicts further restrict assignment options, compressing an already thin workforce.
- `Time Pressure` <-> `Task & Workforce Management` <-> `Equipment & Repair`: Multiple systems degrade simultaneously on independent timers. Fixing one pauses its timer but the others keep ticking. Pulling a worker from a partially-complete repair to address a new emergency wastes the progress already invested and may leave the abandoned system in a worse state than before (the disassembled scrubber can't be abandoned safely).
- `Food & Water Supply` <-> `Thermal Regulation` <-> `Power Grid`: Greenhouse crops need stable temperature. Temperature needs power. Power is failing. Crop loss threatens food supply. Food scarcity threatens morale. Low morale threatens workforce effectiveness. Workforce effectiveness determines whether power gets fixed.
- `Player Health` <-> `Task & Workforce Management` <-> `Station Administration`: If the player does field work, they're more effective at that single task but lose the ability to respond to new crises, reassign workers, and make real-time priority decisions. The colony runs worse without active oversight. But if the player stays at the desk, there's one fewer pair of hands on tasks that desperately need bodies. This is the fundamental tension of the scenario.

## Emergent Possibilities
- The player pulls the EVA-rated crew off the seal repair to clean the solar panels. Power recovers, but the western habitat pressure continues dropping. That night, the colony's automatic safety system seals off the western module — trapping two colonists' personal quarters and the secondary tool store behind a pressure door. Now the seal repair is even more urgent, the colonists are furious about being locked out of their rooms, and the tools needed for the *next* repair are inaccessible. A reasonable prioritization decision cascaded into a compounding crisis.

- The player assigns the under-qualified agricultural technician to help with the water pump instead of the potato crop, reasoning that the pump is more critical. The tech makes a mistake that damages the pump further, extending the repair by twelve hours. Meanwhile, nobody recalibrated the nutrient feed lines and the potato crop dies. The colony loses both the crop and the pump time — a worse outcome than if the player had done nothing and let the pump seize naturally, which would have been repairable but slower. Sometimes the best delegation is no delegation.

- Two surface workers who aren't speaking after their mess hall fight are the only two people EVA-certified and available. The player can force them to work together on the solar panels (risking a blowup outside in suits), send only one (doubling the task duration and leaving one idle), or broker a reconciliation first (burning hours of leadership time that could be spent on other crises). The interpersonal conflict, which seemed like a minor HR issue, has become a hard operational constraint that directly affects power generation.

## Inspiration
- *Surviving Mars* (game) — colony management with worker assignment, infrastructure maintenance, and cascading system failures
- *RimWorld* (game) — task prioritization, colonist moods and relationships affecting work, everything going wrong simultaneously
- *The Martian* (Andy Weir) — making hard triage decisions with limited resources and no backup
- *Moonbase Alpha* / *Space: 1999* — the weight of command in an isolated lunar settlement
- *Offworld Trading Company* (game) — resource competition and optimization under pressure
- *Kim Stanley Robinson's Mars Trilogy* — the daily grind of making a hostile world livable, the politics of who does what work
