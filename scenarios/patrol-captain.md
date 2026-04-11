# Scenario: Patrol Captain

## Narrative
Three days into a twenty-one-day patrol sweep through the outer belt, and you're already behind. The corvette *Harlan's Reach* was supposed to deploy with a crew of twenty-two. You have sixteen, because the Navy decided your patrol sector was low priority and reassigned six of your people to a convoy escort that apparently mattered more. So now you're running three watches with crews meant for two, your damage control team is a gunner's mate and a cook who took a weekend course, and your sensor operator is pulling twelve-hour shifts because there's nobody qualified to relieve her.

The patrol route is a long, looping arc through a hundred-thousand-kilometer corridor of rock, dust, and marginal commerce. Mining barges, ore haulers, prospector skiffs, independent cargo runners — the belt is full of people trying to make a living in places where the law is a suggestion and help is hours away. Your job is to be the law. Respond to distress calls. Inspect cargo manifests for contraband. Deter the piracy that's been creeping up since the last patrol corvette in this sector broke down and never got replaced. Show the flag. Keep the peace. Do it with two-thirds of a crew and a fuel budget that assumes a straight-line route with no deviations.

This morning the problems arrived in a stack. A mining barge called *Duluth Prospect* is broadcasting a distress signal — loss of atmosphere in their crew module, casualties unknown, position four hours off your plotted route. A cargo hauler flagged by intelligence as a possible contraband runner is transiting your sector and will be out of intercept range within six hours — if you divert to the barge, the hauler is gone. Your medical officer has reported that someone has been systematically stealing from the pharmaceutical stores — stimulants, painkillers, and a controlled sedative — and wants you to investigate before the thief escalates. And your navigator just informed you that the fuel margins for the rest of the patrol are thinner than projected because of a miscalculated burn on day one. You can answer every call and inspect every ship, or you can complete the patrol route. You cannot do both.

You are not managing a colony or a cargo ship. You are managing a patrol — a moving jurisdiction with a schedule, a mandate, and a crew that is quietly fraying. Every diversion costs fuel you can't replace and hours your crew can't recover. Every call you don't answer is someone who needed help and didn't get it. Every inspection you skip is a cargo hold that might be full of stolen mining equipment or might be full of nothing. You have to decide what matters, and you have to live with what you chose to ignore.

## Setting
- **Location type**: vessel
- **Scale**: crew
- **Tone**: authority, endurance

## Player Agency
- **Triage distress calls**: Decide which calls to answer based on severity, proximity, fuel cost, and the opportunity cost of diverting from other duties — knowing that unanswered calls have consequences
- **Manage inspections**: Choose which vessels to inspect, how aggressively to pursue non-compliant ships, and whether to risk a confrontation with a suspect vessel when your crew is thin
- **Assign crew to watches and tasks**: Distribute an understaffed crew across bridge watches, damage control, boarding parties, medical, and engineering — every assignment leaves a gap somewhere else
- **Investigate internal problems**: Pursue the pharmaceutical theft through interviews, surveillance, and locker inspections — or deprioritize it and hope it doesn't escalate
- **Manage fuel and route**: Adjust the patrol route in real-time as diversions consume fuel, deciding which sectors to cut, which waypoints to skip, and whether to end the patrol early
- **Maintain crew welfare**: Balance the operational demands with the reality that your people are exhausted, overworked, and starting to make mistakes
- **Exercise legal authority**: Make judgment calls during inspections — what constitutes probable cause, when to detain a vessel, how to handle ambiguous cargo in a jurisdiction where the rules are fuzzy
- **Set priorities**: Explicitly rank your competing mandates — rescue, enforcement, deterrence, patrol completion — and accept that the lower-ranked ones will suffer

## Resolution Paths
- **Best**: Complete the patrol with all distress calls answered, key inspections completed, the thief identified and dealt with, and a crew that respects the hard calls you made — fuel margins tight but sufficient, patrol report clean
- **Good**: Most calls answered, most inspections completed, crew intact but tired, fuel required an early return by one or two days — the thief is identified but the resolution is imperfect
- **Mixed**: Answer the critical calls but skip sectors, miss the contraband hauler, crew cohesion fraying — the thief isn't caught and the stolen drugs cause an incident, patrol report has gaps that invite scrutiny
- **Bad**: A distress call goes unanswered and people die, or a botched inspection escalates into a confrontation that damages the ship or injures crew — fuel situation forces an emergency return, patrol is a failure
- **Worst**: Crew breaks down — exhaustion leads to a critical error on the bridge, the thief's actions cause a medical emergency, a confrontation with a suspect vessel goes wrong, and the corvette limps home with casualties, an incomplete patrol, and a captain facing a board of inquiry

## Required Simulation Systems

### Task & Workforce Management
- **Purpose**: Simulates the assignment and scheduling of all shipboard duties — bridge watches, engineering tasks, boarding party composition, investigations, damage control, and administrative work — across a crew that is too small for the demands placed on it. This is the central management system: the player's primary tool for deciding who does what, when, and at what cost to everything else.
- **Key State**: Task queue (watch rotations, boarding parties, damage control assignments, investigation tasks, maintenance work orders, administrative duties), each with urgency, required skills, required personnel count, and estimated duration. Worker pool (crew manifest with current assignment, fatigue, skill ratings, watch rotation position, morale, interpersonal flags). Task progress per active assignment. Coverage gaps (unfilled watch positions, unstaffed departments). Overtime accumulation per crew member. Task conflict matrix (tasks competing for the same qualified personnel). Opportunity cost tracker (what degrades while people are assigned elsewhere).
- **Player-facing**: Watch bill interface showing all three rotations with personnel assignments and gap warnings. Task board with active and pending duties, drag-and-drop crew assignment, completion estimates that shift based on who's assigned. Fatigue and overtime alerts per crew member. Coverage gap warnings when critical stations are unmanned. Boarding party composition builder with skill requirements. "Cost of this assignment" projections showing what gets neglected.

### Ship Crewing
- **Purpose**: Simulates the corvette's crew positions, role requirements, qualification tiers, and the cascading effects of understaffing on ship capability — the structural constraint that makes Task & Workforce Management difficult.
- **Key State**: Required crew positions (bridge watch officer, helm, sensors, engineering, damage control, medical, gunnery, boarding team lead, boarding team members), minimum safe manning levels per watch, current crew manifest against required billets, qualification ratings per crew member per position, cross-training status, watch rotation schedule (three watches), hours on duty per crew member, consecutive days without full rest, efficiency modifier per station based on operator fatigue and qualification, vacancy impact (what the ship cannot do when a position is unfilled).
- **Player-facing**: Crew roster with billet assignments and qualification indicators, watch rotation calendar, vacancy alerts showing which capabilities are degraded, cross-training progress, fatigue tracking per crew member with performance degradation warnings, "ship capability" summary showing what you can and cannot do with current manning.

### Navigation & Fuel
- **Purpose**: Simulates the patrol route, course plotting, fuel consumption, and the hard tradeoffs between diversions and route completion — fuel is the finite resource that constrains every other decision.
- **Key State**: Current position, plotted patrol route with waypoints, fuel remaining (delta-v budget), fuel consumption rate, projected fuel at each remaining waypoint, diversion cost calculator (fuel to reach a target and return to route), intercept geometry (time and fuel to reach a moving vessel), point of no return for current fuel state, nearest refueling point, patrol completion percentage, sectors covered vs. skipped.
- **Player-facing**: Navigation plot showing the patrol route, current position, and waypoints with fuel projections. Diversion calculator that shows the cost of any off-route action. Fuel gauge with "fuel at end of patrol" projection that updates in real-time. Intercept planner for suspect vessels. Route editor for cutting waypoints or sectors. Warning when fuel state forces hard choices.

### Sensors & Scanning
- **Purpose**: Simulates the corvette's sensor suite — detecting distress signals, identifying vessels, assessing threats, and scanning cargo at range. The information source that drives most decisions.
- **Key State**: Sensor range, resolution, power draw, detected contacts (vessels, debris, anomalies), contact classification (identified, unidentified, flagged), distress signal detection and triangulation, cargo scan capability (range and resolution limitations), electronic emissions analysis, sensor operator fatigue effects on detection quality, false positive rate under degraded conditions.
- **Player-facing**: Sensor display with contact tracks, distress signal alerts with position and signal quality, vessel identification readouts, cargo scan results (partial, uncertain, or clear), threat assessment indicators, detection quality warnings when operator is fatigued.

### Communications
- **Purpose**: Simulates ship-to-ship and ship-to-command communications — hailing vessels, responding to distress calls, reporting to patrol command, and managing the information flow that shapes decisions.
- **Key State**: Active comm channels, hail status per contacted vessel (responded, no response, refused), distress call log (signal strength, declared emergency type, time since first detection), patrol command contact schedule, report queue, signal delay to command, message backlog, crew communications (internal), signal intercepts.
- **Player-facing**: Comm panel with active channels, hail interface, distress call log with response status, patrol command reporting interface, message queue, signal delay indicator, recorded transmissions from contacted vessels.

### Security & Threat
- **Purpose**: Simulates threat assessment, defensive posture, boarding operations, and the use of force continuum — the tactical layer that activates when a vessel won't comply or a situation turns hostile.
- **Key State**: Threat level (per contact and overall), defensive posture (weapons status, shield readiness), boarding team readiness, use-of-force authorization level, rules of engagement, suspect vessel behavior (compliant, evasive, hostile), boarding risk assessment, crew combat readiness, internal security status (the theft investigation), detained persons (if any).
- **Player-facing**: Threat board showing assessed risk per contact, defensive posture controls, boarding operation planner with risk assessment, rules of engagement reference, use-of-force decision prompts during escalation, internal security investigation interface.

### Law & Jurisdiction
- **Purpose**: Simulates the legal framework governing the patrol — what authority the captain has to stop, inspect, detain, and use force, and the jurisdictional ambiguity of the outer belt where multiple authorities overlap and enforcement is inconsistent.
- **Key State**: Patrol mandate (authorized actions, sector boundaries, reporting requirements), jurisdictional zones (corporate claim areas, free zones, disputed territories), legal authority for inspection (probable cause requirements, flag state considerations), detention authority and limits, use of force authorization thresholds, contraband definitions (varies by jurisdiction), evidence chain for seized goods, legal risk of actions taken (wrongful detention liability, excessive force claims), outstanding warrants and alerts database, diplomatic considerations (corporate-flagged vessels with political protection).
- **Player-facing**: Jurisdiction overlay on navigation plot showing authority boundaries, legal advisor prompts during inspections ("you have / do not have authority to..."), evidence log for building inspection cases, detention protocol checklist, legal risk warnings when actions approach the edge of authority, post-action report generator for chain of command review.

### Cargo & Trade
- **Purpose**: Simulates the cargo inspection process — manifest verification, physical inspection, contraband identification, and the economic context that makes smuggling profitable and detection difficult.
- **Key State**: Inspected vessel cargo manifest (declared), scan results (detected), discrepancy flag (declared vs. detected), contraband database (prohibited items by jurisdiction), cargo value assessment, smuggling method sophistication (shielded containers, mislabeled goods, hidden compartments), false flag indicators, trade route patterns (what's normal vs. suspicious for this corridor), inspection thoroughness (quick scan vs. full physical inspection, time and crew cost of each), seized goods inventory.
- **Player-facing**: Cargo manifest comparison view (declared vs. scanned), discrepancy highlights, contraband match alerts, inspection depth selector (quick/standard/thorough with time estimates), smuggling pattern analysis, seized goods log, economic context for why certain goods are being moved through this corridor.

### Medical & Injury
- **Purpose**: Simulates crew medical status, the pharmaceutical theft crisis, and the medical officer's capacity to handle casualties from both the distress call response and any boarding operations.
- **Key State**: Crew health status per individual, pharmaceutical inventory (with tracked discrepancies — stimulants, painkillers, sedatives missing), medical officer workload, medical bay capacity, trauma response capability, drug interaction risks (if the thief is using stolen substances), casualty treatment priority, medical supplies remaining for the patrol, rescued casualty care requirements (if responding to the distress call).
- **Player-facing**: Crew health dashboard, pharmaceutical inventory with shortage alerts, medical officer status and availability, casualty treatment interface, drug theft investigation evidence board, medical supply projections for remainder of patrol.

### NPC Identity & Personality
- **Purpose**: Gives each crew member a persistent identity, service history, skills, personality, morale state, and behavioral patterns — especially under the compounding stress of understaffing, overwork, and the captain's difficult decisions.
- **Key State**: Name, rank, service record, skill ratings per billet, personality traits (by-the-book/flexible, confrontational/avoidant, ambitious/content), stress tolerance, current fatigue, morale, trust in captain, opinion of captain's decisions, relationships with other crew, personal stressors (the thief has a motive rooted in their background), coping mechanisms, breaking point threshold.
- **Player-facing**: Crew profiles with service history and skill ratings, observable stress responses and morale shifts, private conversations revealing opinions and concerns, NPC-initiated reports and requests, behavioral changes as fatigue and stress accumulate, trust indicators reflecting how the crew perceives the captain's leadership.

### Social Dynamics
- **Purpose**: Simulates crew cohesion, morale, and the interpersonal effects of sustained pressure — an understaffed crew on a long patrol develops friction, cliques, and grievances that affect operational performance.
- **Key State**: Group morale, unit cohesion index, interpersonal tension map, grievance queue (unfair watch assignments, denied leave requests, perceived favoritism), overtime resentment, confidence in captain's judgment, mess hall atmosphere, informal leadership (NCOs and senior crew who influence group mood), scapegoating dynamics, rumor propagation (especially around the theft investigation).
- **Player-facing**: Morale indicator, crew tension alerts, overheard complaints and conversations, NCO feedback on crew mood, mess hall scene descriptions reflecting group state, crew pushback on unpopular orders, cohesion warnings when the crew is fragmenting.

### Equipment & Repair
- **Purpose**: Simulates the corvette's mechanical and electronic systems — sensors, engines, weapons, life support, and the maintenance burden that competes with operational tasks for crew time.
- **Key State**: Component health per system, maintenance schedule, repair backlog, spare parts inventory, required skill for each repair, repair duration, deferred maintenance risk (what breaks if you keep delaying), tool availability, maintenance crew availability (usually stolen for other duties).
- **Player-facing**: Maintenance board with system health indicators, repair work orders with priority and crew requirements, deferred maintenance warnings, spare parts inventory, "time to failure" estimates for degrading systems.

### Player Health
- **Purpose**: Tracks the captain's physical and mental state — relevant because the captain is making continuous high-stakes decisions on insufficient sleep while managing a crew that needs visible, competent leadership.
- **Key State**: Fatigue, sleep debt, stress level, decision fatigue (accumulates with each hard call), caloric intake, cognitive impairment from overwork, command presence (how tired the captain looks affects crew confidence).
- **Player-facing**: Fatigue indicators, decision-making debuffs (slower processing, missed details in reports, narrowed dialogue options), crew noticing the captain's exhaustion in dialogue, physical limits on how many consecutive watches the captain can stand.

### Time Pressure
- **Purpose**: Simulates the competing clocks of patrol schedule, distress response windows, intercept windows, fuel depletion, crew endurance limits, and investigation deadlines — every hour spent on one thing is an hour lost for everything else.
- **Key State**: Patrol schedule (days remaining, waypoints remaining), distress response window (hours until too late), intercept window (hours until suspect vessel exits range), fuel timeline (hours until committed to return), crew endurance projections (days until fatigue causes critical errors), investigation urgency (rate of pharmaceutical theft), reporting deadlines to patrol command.
- **Player-facing**: Multi-clock dashboard showing all active time constraints simultaneously, window-closing warnings, fuel timeline overlay, patrol completion projection, "hours until decision is forced" indicators for each active situation.

### Power Grid
- **Purpose**: Simulates the corvette's power generation and distribution — relevant when the ship must choose between running sensors at full power, maintaining speed, keeping weapons hot, and basic life support during sustained operations.
- **Key State**: Reactor output, power distribution bus, per-system power draw (sensors, engines, weapons, life support, communications, lighting), load priority queue, power reserves, efficiency degradation under deferred maintenance.
- **Player-facing**: Power distribution dashboard, load warnings when multiple high-draw systems compete, priority controls for brownout situations, efficiency alerts tied to maintenance status.

## System Dependencies

### Hard Dependencies
- `Task & Workforce Management` --depends on--> `Ship Crewing`: task assignments are constrained by who is qualified, who is on watch, and how many people are available per rotation
- `Ship Crewing` --depends on--> `NPC Identity & Personality`: crew members are NPCs with skills, qualifications, fatigue, morale, and interpersonal constraints
- `Social Dynamics` --depends on--> `NPC Identity & Personality`: interpersonal simulation requires personality, trust, and relationship data
- `Navigation & Fuel` --depends on--> `Ship Crewing`: course corrections and burns require a qualified helm and watch officer on duty
- `Sensors & Scanning` --depends on--> `Power Grid`: sensor range and resolution depend on power allocation
- `Security & Threat` --depends on--> `Ship Crewing`: boarding parties and defensive operations require qualified, available personnel
- `Law & Jurisdiction` --depends on--> `Sensors & Scanning`: legal authority to inspect requires sensor evidence establishing probable cause
- `Cargo & Trade` --depends on--> `Sensors & Scanning`: cargo inspection begins with sensor scans that reveal manifest discrepancies

### Soft Dependencies
- `Task & Workforce Management` ~~depends on~~> `Social Dynamics`: crew tensions constrain who can be paired on watches and boarding parties; morale affects task acceptance and quality
- `Task & Workforce Management` ~~depends on~~> `Time Pressure`: task priority is driven by closing windows and competing deadlines
- `Ship Crewing` ~~depends on~~> `Social Dynamics`: crew members in conflict perform worse on shared watches; cohesion affects unit effectiveness during boarding operations
- `Ship Crewing` ~~depends on~~> `Task & Workforce Management`: overtime and unfair assignments accumulate through the task system and feed back into crewing quality
- `Social Dynamics` ~~depends on~~> `Task & Workforce Management`: perceived unfairness in watch assignments, boarding party selection, and overtime distribution degrades morale
- `Navigation & Fuel` ~~depends on~~> `Time Pressure`: diversion decisions are driven by intercept windows and distress response deadlines
- `Sensors & Scanning` ~~depends on~~> `Ship Crewing`: sensor quality degrades when the operator is fatigued or the position is filled by an underqualified substitute
- `Security & Threat` ~~depends on~~> `Social Dynamics`: crew cohesion affects boarding party effectiveness; low morale increases risk during confrontations
- `Law & Jurisdiction` ~~depends on~~> `Communications`: legal authority often depends on hailing a vessel and documenting its response before escalating
- `Cargo & Trade` ~~depends on~~> `Law & Jurisdiction`: what counts as contraband depends on which jurisdiction the inspection occurs in
- `Medical & Injury` ~~depends on~~> `Task & Workforce Management`: the medical officer's time is split between crew health, casualty care, and the theft investigation
- `Player Health` ~~depends on~~> `Ship Crewing`: the captain standing extra watches accumulates fatigue that degrades decision-making
- `NPC Identity & Personality` ~~depends on~~> `Task & Workforce Management`: fatigue and morale shift based on assignment load, overtime, and whether the captain's decisions feel competent and fair
- `Equipment & Repair` ~~depends on~~> `Task & Workforce Management`: maintenance competes with operational tasks for the same limited crew
- `Power Grid` ~~depends on~~> `Equipment & Repair`: deferred maintenance degrades reactor efficiency and distribution reliability

### Feedback Loops
- `Task & Workforce Management` <-> `Ship Crewing` <-> `Social Dynamics`: Understaffing forces overtime. Overtime increases fatigue. Fatigue degrades performance. Degraded performance means tasks take longer or fail. Failed tasks create new urgent work. New urgent work requires more overtime. Meanwhile, unfair assignments breed resentment, resentful crew resist orders or work slower, and the captain must either push harder (more resentment) or accept gaps in coverage (more risk). This is the core loop of the scenario — the staffing deficit that makes everything harder and gets worse the longer it runs.
- `Navigation & Fuel` <-> `Time Pressure` <-> `Task & Workforce Management`: Every diversion costs fuel and time. Less fuel means fewer future diversions. Fewer diversions mean skipped sectors and unanswered calls. Unanswered calls may escalate into worse situations that demand even costlier responses later. Meanwhile, diversions extend crew time on station, increasing fatigue, which degrades the quality of every subsequent operation.
- `Sensors & Scanning` <-> `Ship Crewing` <-> `Security & Threat`: A fatigued sensor operator misses contacts or generates false positives. Missed contacts mean threats go undetected. False positives waste fuel and crew energy on unnecessary intercepts. Both outcomes erode confidence in the sensor watch, leading other crew to second-guess alerts, which leads to slower response when a real threat materializes.
- `Medical & Injury` <-> `Social Dynamics` <-> `NPC Identity & Personality`: The pharmaceutical theft creates suspicion and paranoia among the crew. The investigation disrupts trust. If the thief is someone well-liked, catching them fractures the crew. If the thief is not caught, the stolen stimulants and sedatives create a crew member operating under chemical influence — a safety risk during boarding operations or engineering work. The medical officer, forced to play detective, has less time for actual medical duties, degrading crew health support.
- `Law & Jurisdiction` <-> `Cargo & Trade` <-> `Security & Threat`: Aggressive enforcement deters smuggling but risks confrontation with vessels that may be armed or uncooperative. Lenient enforcement maintains safety but lets contraband through and emboldens future smugglers. A botched inspection — wrong jurisdiction, insufficient evidence, excessive force — creates legal liability that constrains future enforcement actions and damages the captain's authority.
- `Player Health` <-> `Task & Workforce Management` <-> `Social Dynamics`: The captain skipping sleep to manage the crisis maintains oversight but visibly deteriorates. A tired captain makes worse decisions. Worse decisions erode crew trust. Eroded trust means the crew pushes back harder on orders, requiring more leadership energy from a captain who has less to give. Alternatively, the captain sleeps and delegates — but delegation to an understaffed, exhausted crew without active oversight risks errors the captain would have caught.

## Emergent Possibilities
- The player diverts to answer the *Duluth Prospect* distress call, burning four hours of transit and a significant fuel margin. On arrival, they find the barge's crew alive but the atmosphere breach was caused by a cutting charge — not an accident. Someone blew a hole in the crew module deliberately. The distress call is real, but the cause is a crime scene, and the player now has injured miners, a criminal investigation, and a suspect who might still be on the barge. Meanwhile, the contraband hauler has cleared the sector. The rescue just became an extended operation that was never in the patrol plan.

- The player orders a full inspection of the suspect cargo vessel. The hauler's captain is uncooperative but not hostile — she heaves to when threatened but makes it clear she considers this harassment. The cargo scan shows ambiguous results: containers that could be shielded contraband or could be legitimately sealed proprietary mining equipment. The player must decide whether to force a physical boarding — which requires pulling the boarding team from rest, risks a confrontation, and could be a jurisdictional overreach if they're in a corporate claim zone — or let the hauler go with a note in the log. Weeks later, the outcome of this decision shows up in a report: the hauler was either clean (and the captain filed a formal complaint) or dirty (and the contraband ended up arming a pirate crew in the next sector over).

- The pharmaceutical theft investigation narrows to two suspects — a veteran crew member with chronic pain who's been self-medicating because the medical officer rationed their prescription too aggressively, and a younger crew member who's been selling stimulants to keep their watch performance up because they're terrified of failing in front of the captain. Both are sympathetic. Both are breaking regulations. The player's choice — formal charges, quiet resolution, or looking the other way — sets a precedent that the entire crew internalizes about what kind of captain they're serving under.

- On day fourteen, with fuel margins razor-thin, a second distress call comes in from a prospector skiff — a single operator with a failing reactor, twelve hours off the return route. Answering the call means the patrol ends three days early with two sectors uncovered. Ignoring it means a person probably dies alone in the dark. The crew knows about the call. The player's decision, and how they explain it, determines whether the crew trusts the captain's judgment for the remaining week or quietly loses faith in the mission.

## Inspiration
- *The Expanse* — Rocinante crew dynamics, belter politics, naval authority in contested space
- *Master and Commander* (film) — a captain managing an undermanned warship, balancing mission with crew welfare, making calls with incomplete information
- *Battlestar Galactica* — crew fatigue, internal investigations, command decisions under sustained pressure
- *FTL: Faster Than Light* (game) — resource-constrained patrol with encounters that force hard tradeoffs
- *The Wire* (television) — institutional pressure, the gap between mandate and resources, doing the job with what you have
- *Papers, Please* (game) — inspection as gameplay, legal ambiguity, moral weight of bureaucratic decisions
