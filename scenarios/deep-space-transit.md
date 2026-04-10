# Scenario: Deep Space Transit

## Narrative
You are three days into a nineteen-day burn between Ceres Station and Pallas Depot, and the ship already smells wrong. Not dangerous wrong — not yet — but the recycler is putting out air with a stale, metallic edge that wasn't there at departure. You've got five crew aboard a hauler rated for eight, which means everyone is pulling double duty and nobody is sleeping enough. The navigation plot is locked in, fuel margins are tight, and there is nothing outside the viewports but black.

You didn't pick this crew. Half of them came with the contract, assigned by the freight company. The other half you scraped together at Ceres because the originals quit, got arrested, or simply didn't show. Your engineer is competent but drinks. Your pilot is green but eager. The logistics officer has opinions about everything and the authority to back up none of them. The cook — who is also your medic, because that's how thin you're stretched — hasn't said more than six words since boarding. You don't know these people, and you are sealed inside a metal tube with them for two and a half more weeks.

The food stores were loaded in a hurry and nobody verified the manifest against actual headcount. The water recycler is functional but old, and its filters are overdue for replacement. You have enough of everything if nothing goes wrong. But nothing going wrong for nineteen days, with this crew, in this ship, on this route — that would be a first.

## Setting
- **Location type**: vessel
- **Scale**: crew
- **Tone**: tension, endurance

## Player Agency
- Manage crew shift schedules and duty assignments to prevent burnout and conflict
- Ration food and water proactively or wait until shortages force the issue
- Decide how to handle interpersonal conflicts — mediate, take sides, ignore, or enforce authority
- Choose whether to maintain the planned route or adjust course for a longer but safer trajectory
- Allocate repair time between the air recycler, water filters, and other degrading systems
- Invest time in getting to know crew or maintain professional distance
- Decide how transparent to be with the crew about supply margins and system health

## Resolution Paths
- **Best**: Arrive at Pallas Depot on schedule with a functional ship, adequate reserves, and a crew that trusts each other enough to sign on again
- **Good**: Arrive late or with depleted reserves, but everyone is alive and the cargo is intact
- **Mixed**: Make it to port but lose a crew member (quit at arrival, medical emergency, or confinement breakdown) and the crew fractures into factions
- **Bad**: Systems degrade to the point of forced detour or distress call — Loss of cargo, contract penalties, and crew that will never fly together again
- **Worst**: Cascading failures — atmosphere, water, food, or crew cohesion collapses — resulting in death, mutiny, or abandoning ship

## Required Simulation Systems

### Navigation & Fuel
- **Purpose**: Simulates plotting courses, burn calculations, fuel consumption, and trajectory management over long distances
- **Key State**: Current trajectory, fuel remaining (delta-v budget), burn schedule, course deviation, ETA, nearest navigable destination, drift rate
- **Player-facing**: Navigation console with trajectory plot, fuel gauge and burn schedule, ETA readout, course correction prompts, deviation warnings

### Ship Crewing
- **Purpose**: Simulates crew positions, role requirements, shift scheduling, fatigue, and the effects of staffing on ship capability
- **Key State**: Required crew positions, current crew manifest, shift rotation schedule, hours worked per crew member, fatigue level per crew member, role coverage gaps, efficiency modifier
- **Player-facing**: Crew roster and shift calendar, fatigue warnings, role vacancy alerts, performance degradation indicators, overtime notifications

### Social Dynamics
- **Purpose**: Simulates interpersonal relationships, tensions, alliances, and group morale among crew in sustained close quarters
- **Key State**: Relationship scores (per NPC pair and player-NPC), tension level (individual and group), grievance log, alliance/faction formation, cabin fever index, privacy deficit, conflict history
- **Player-facing**: Crew arguments overheard or reported, body language cues, mess hall seating patterns, NPCs seeking the player out or avoiding them, morale events, request for mediation

### Food & Water Supply
- **Purpose**: Simulates consumable resource tracking, rationing, spoilage, and the physiological effects of nutrition and hydration on crew
- **Key State**: Food stores by type (calories, nutrition quality, variety), water reserves (liters), consumption rate per crew member, spoilage rate, water recycler throughput, filter condition, days of supply remaining at current consumption
- **Player-facing**: Pantry inventory, meal quality and variety indicators, water reserves display, rationing controls, spoilage alerts, crew complaints about food, hunger/thirst effects on NPC mood and performance

### Atmosphere Management
- **Purpose**: Simulates breathable air composition, recycling, scrubbing, and environmental quality in a sealed vessel over extended duration
- **Key State**: O2 level per compartment, CO2 level, humidity, trace contaminant buildup, recycler throughput, scrubber filter life, air quality index, leak rate, odor accumulation
- **Player-facing**: Air quality readouts, stale air complaints from crew, scrubber maintenance prompts, humidity condensation on surfaces, headaches and drowsiness from poor air, filter replacement warnings

### NPC Identity & Personality
- **Purpose**: Gives each crew member a persistent identity, personality, history, coping mechanisms, and behavioral patterns that emerge under sustained stress
- **Key State**: Name, background, skills (rated), personality traits (introvert/extrovert, confrontational/avoidant, optimistic/pessimistic), stress tolerance, coping mechanisms, vices, current morale, trust toward player, trust toward each crew member, personal goals, secrets
- **Player-facing**: Distinct dialogue and behavior per NPC, observable stress responses, private conversations, NPC-initiated requests or confrontations, personality clashes, moments of unexpected vulnerability or competence

### Time Pressure
- **Purpose**: Simulates the passage of time as a resource and constraint during a fixed-duration transit
- **Key State**: Current mission day, total transit duration, ETA, active deadlines (filter replacement, supply depletion dates, contract delivery window), schedule slippage, time remaining on critical consumables
- **Player-facing**: Mission day counter, supply countdown timers, contract deadline indicator, schedule deviation warnings, crew awareness of how many days remain

### Player Health
- **Purpose**: Tracks the player's physical and mental condition as affected by sleep, nutrition, air quality, and stress
- **Key State**: Fatigue, sleep debt, blood oxygenation, caloric intake, hydration, stress level, injury status
- **Player-facing**: Blurred vision from fatigue, reduced decision-making speed, irritability affecting dialogue options, physical debuffs from poor nutrition or air quality

### Equipment & Repair
- **Purpose**: Simulates the state of ship components and the ability to maintain, repair, or jury-rig them with limited supplies during transit
- **Key State**: Component health per system (recycler, filters, water processor, engines, nav computer), spare parts inventory, tool availability, repair skill of available crew, maintenance backlog
- **Player-facing**: Maintenance alerts, component degradation warnings, repair interface, spare parts inventory, crew skill ratings for repair tasks

### Sensors & Scanning
- **Purpose**: Simulates the ship's ability to detect external hazards, contacts, and navigational data during transit through open space
- **Key State**: Sensor range, resolution, power draw, detected contacts (debris, other vessels, navigational hazards), scan cycle time, interference level
- **Player-facing**: Sensor display with contact markers, hazard warnings, long-range scan results, interference static, "something on sensors" alerts that may be debris or may be nothing

## System Dependencies

### Hard Dependencies
- `Atmosphere Management` --depends on--> `Equipment & Repair`: recyclers and scrubbers are mechanical systems that degrade and require maintenance
- `Food & Water Supply` --depends on--> `Equipment & Repair`: water recycler and food storage systems require functioning hardware
- `Ship Crewing` --depends on--> `NPC Identity & Personality`: crew members are NPCs with skills, fatigue, and morale
- `Social Dynamics` --depends on--> `NPC Identity & Personality`: interpersonal simulation requires personality and relationship data
- `Navigation & Fuel` --depends on--> `Ship Crewing`: course corrections and burns require a qualified pilot on duty

### Soft Dependencies
- `Social Dynamics` ~~depends on~~> `Food & Water Supply`: meal quality and rationing directly affect crew morale and tension
- `Social Dynamics` ~~depends on~~> `Atmosphere Management`: poor air quality increases irritability and conflict
- `Social Dynamics` ~~depends on~~> `Ship Crewing`: overwork and unfair shift assignments breed resentment
- `Ship Crewing` ~~depends on~~> `Social Dynamics`: crew members in conflict perform worse together and may refuse shared shifts
- `NPC Identity & Personality` ~~depends on~~> `Food & Water Supply`: hunger and thirst affect NPC mood, stress tolerance, and decision-making
- `NPC Identity & Personality` ~~depends on~~> `Atmosphere Management`: headaches and poor sleep from bad air degrade NPC morale
- `Player Health` ~~depends on~~> `Food & Water Supply`: player nutrition and hydration affect physical and cognitive state
- `Player Health` ~~depends on~~> `Atmosphere Management`: air quality affects player alertness and health
- `Player Health` ~~depends on~~> `Ship Crewing`: player taking extra shifts increases fatigue and stress
- `Sensors & Scanning` ~~depends on~~> `Ship Crewing`: sensor monitoring requires a crew member on watch
- `Time Pressure` ~~depends on~~> `Navigation & Fuel`: course deviations extend transit time and compress remaining margins

### Feedback Loops
- `Social Dynamics` <-> `Ship Crewing`: Overworked crew become hostile; hostile crew perform worse, requiring others to pick up slack, increasing everyone's workload
- `Food & Water Supply` <-> `Social Dynamics` <-> `NPC Identity & Personality`: Rationing breeds resentment; resentful crew may hoard or steal food; discovered hoarding escalates tension further
- `Atmosphere Management` <-> `Equipment & Repair` <-> `Ship Crewing`: Degrading air systems need repair; repair requires pulling crew from other duties; understaffed shifts mean other systems get less attention; neglected systems degrade faster
- `Time Pressure` <-> `Food & Water Supply` <-> `Player Health`: Dwindling supplies force rationing; rationing degrades health and morale; degraded crew works slower; slower work extends timelines; extended timelines consume more supplies
- `Sensors & Scanning` <-> `Social Dynamics`: Unidentified contacts create anxiety; anxious crew make worse decisions; poor decisions may lead to unnecessary course changes that waste fuel and extend transit

## Emergent Possibilities
- The cook, who has barely spoken since departure, turns out to be the only crew member who notices the water recycler output tastes slightly off — an early warning sign of filter failure that the engineer missed because she was hungover. Whether the player takes the cook seriously or dismisses them determines whether a slow-building crisis is caught early or becomes an emergency at day fourteen.
- Two crew members who seemed professionally compatible at departure begin a quiet alliance against a third who they perceive as not pulling their weight. The player only discovers this when shift handoff logs start showing discrepancies, and by then the excluded crew member is considering sabotaging the recycler to force a distress call and early end to the transit.
- A faint contact appears on sensors at day eleven — probably debris, possibly another vessel on a parallel course. The crew splits on whether to investigate, ignore, or alter course. The disagreement reveals underlying tensions about who actually has authority on this ship, and the player's decision sets a precedent that echoes through every subsequent conflict.

## Inspiration
- *The Expanse* — long burns, tight ships, crew dynamics under pressure
- *Alien* (film) — blue-collar space workers trapped together, slow-building tension
- *Das Boot* (film) — claustrophobia, endurance, and interpersonal friction in a sealed vessel
- *FTL: Faster Than Light* (game) — crew management and system triage under time pressure
- *Prospect* (film) — resource scarcity and uneasy alliances in isolated conditions
