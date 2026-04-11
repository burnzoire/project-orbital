# Scenario: Boarding Action

## Narrative
The target is the *Hecate's Lantern*, a modified bulk freighter that went dark six hours ago after broadcasting a distress signal that turned out to be bait for a salvage crew. Now it's running under false transponder codes with sixteen crew — or captors, or hostages, or some mix you haven't figured out yet. Intelligence says the ship was hijacked by a separatist cell out of the Jovian Confederacy who want the classified survey data in its nav computer. What intelligence doesn't say is how well-armed they are, how many of the original crew are still alive, or whether the ship is rigged to blow if someone comes knocking.

You're in the CIC of the *Harrow*, a patrol corvette, and you've matched velocity with the *Hecate's Lantern* at four hundred meters. Close enough for your marines to cross. Too close for comfort if anything goes wrong over there. You have a twelve-person marine detachment — experienced, but not infinite. You need to divide them into fire teams, select a breach point, plan their route through the target ship's compartments, and get them in without getting them killed. Once they're across, you're their eyes, their ears, and their judgment. Helmet cams on your display wall. Biometric feeds on your console. Deck plans pulled from the ship's registry that may or may not match what's actually on the other side of that hull.

The breach itself will damage the target's structure — cutting through a hull is not a gentle process, and every compartment you force open is a compartment that might decompress. The separatists know you're here. They've had time to prepare. Barricades, maybe. Booby traps, probably. Hostages positioned as shields, possibly. Your marines will encounter situations that need your call: blow through a sealed hatch and risk killing everyone on the other side, or waste twenty minutes cutting around it while the enemy repositions. Pull a wounded operator back to the breach point or push forward with reduced numbers. Accept a surrender that might be genuine or might be a stall while someone arms a scuttling charge.

You will not fire a weapon. You will not kick in a door. You will sit in your chair, watch your screens, and make decisions that determine whether your people come home. That's command. That's the job.

## Setting
- **Location type**: deep space (ship-to-ship)
- **Scale**: tactical
- **Tone**: command, tension

## Player Agency
- **Plan the assault**: Choose breach points based on deck plans and sensor data — airlocks, cargo hatches, hull cuts — each with different structural damage, noise, and time tradeoffs
- **Organize fire teams**: Divide the marine detachment into teams with specific roles — breaching, clearing, overwatch, medical, reserve — based on individual skills and equipment
- **Assign objectives**: Route teams through the target ship compartment by compartment — choose the order of rooms to clear, corridors to secure, junctions to hold
- **Make real-time calls**: Respond to helmet-cam feeds and biometric alerts — authorize lethal force, order restraint, redirect teams, call for fallback when the plan breaks down
- **Manage hostage situations**: Decide how to handle discovered hostages — extract immediately (pulling a team off the advance), secure in place (leaving them vulnerable), or use them as intelligence sources
- **Handle surrenders**: Evaluate whether crew members giving up are genuine surrenders or traps — accept and restrain, isolate and bypass, or refuse and push through
- **Order withdrawal**: Pull teams back to the breach point if casualties mount, the ship shows signs of scuttling, or the situation becomes unwinnable — cutting losses is a decision too
- **Control the breach site**: Manage the structural damage your own entry causes — seal compartments behind the advance, manage atmosphere loss, prevent the breach from becoming a liability
- **Coordinate with your ship**: Direct the *Harrow*'s sensors and weapons to support the boarding — jamming enemy comms, scanning for movement through the hull, standing ready to cut the target's power or engines

## Resolution Paths
- **Best**: Marines secure the nav computer, neutralize all hostiles, rescue surviving crew — minimal casualties, target ship intact enough to tow, intelligence recovered
- **Good**: Objectives achieved but at cost — wounded marines, some hostages lost, significant structural damage to the target, but mission accomplished
- **Mixed**: Partial success — marines secure part of the ship but are forced to withdraw from contested sections, some intelligence recovered, some hostages saved, but the separatists destroy key data or escape in a lifeboat
- **Bad**: Assault stalls — marines pinned down or taking heavy casualties, forced to withdraw entirely, target ship damaged beyond salvage by the fighting, hostages killed in crossfire or executed
- **Worst**: Catastrophic failure — separatists trigger scuttling charges or a reactor overload, marines still aboard, the *Harrow* takes damage from the explosion or must choose between rescue and self-preservation

## Required Simulation Systems

### Task & Workforce Management
- **Purpose**: Simulates the planning, assignment, and real-time coordination of marine fire teams as a tactical workforce — the player's primary interface for commanding the boarding operation, assigning objectives, and reallocating personnel as the situation evolves
- **Key State**: Fire team roster (team composition, assigned role, current objective, position on deck plan), individual marine status (assigned task, skill specialization, fatigue, wounded/combat-effective), objective queue (breach, clear, hold, extract — prioritized and sequenced), task dependencies (compartment A must be cleared before team can advance to B), reserve pool (uncommitted marines available for redeployment), task progress per objective (percentage cleared, resistance encountered, time elapsed), opportunity cost tracker (what's unguarded or uncleared while teams are committed elsewhere)
- **Player-facing**: Tactical board showing fire team positions on deck plan overlay, drag-and-drop team reassignment, objective queue with sequencing, estimated completion times per compartment, warning flags when teams are overextended or under-strength, reserve pool status, "what's exposed if I move this team" projections

### Combat & Weapons
- **Purpose**: Simulates the firefights occurring aboard the target ship — weapons fire, suppression, grenades, breaching charges — as reported through helmet cams and biometric data rather than experienced directly
- **Key State**: Engagement status per fire team (contact/no contact, suppressed, pinned, advancing), hostile count estimates per compartment, ammunition expenditure per marine, weapon types in play (small arms, breaching charges, stun munitions, lethal vs. non-lethal), fire superiority assessment, friendly fire risk in tight compartments, Rules of Engagement mode (lethal/non-lethal/restricted)
- **Player-facing**: Helmet cam feeds showing firefights in progress, fire team engagement indicators on the tactical board, ammunition status per team, hostile contact markers on deck plan, Rules of Engagement toggle, suppression and pinned-down alerts, breaching charge deployment prompts requiring authorization

### Habitat Integrity
- **Purpose**: Simulates the structural state of the target vessel — hull breaches from forced entry, compartment pressure loss, blast damage from firefights and explosives, and the cascading structural consequences of fighting inside a pressurized ship
- **Key State**: Hull integrity per compartment, pressure status per section (pressurized, leaking, vacuum), breach points (player-created and combat-created), sealed hatch status, compartment isolation state, blast damage from breaching charges and grenades, decompression risk to adjacent sections, structural failure cascade potential, atmosphere composition (smoke, toxic fumes, oxygen depletion in sealed sections)
- **Player-facing**: Target ship cross-section showing pressure status per compartment (color-coded), breach point markers, atmospheric warnings, structural damage indicators, decompression alerts when breaching charges are used, sealed/unsealed hatch status, "breach here will decompress these adjacent compartments" preview

### Sensors & Scanning
- **Purpose**: Simulates the *Harrow*'s ability to scan the target ship from outside — detecting movement through the hull, mapping heat signatures, identifying power sources, and providing the player with intelligence the marines on the ground cannot see
- **Key State**: Hull-penetrating scan resolution, thermal signatures detected (personnel, active equipment, power sources), movement tracking through bulkheads, scan interference from ship structure and shielding, active scan detection risk (hostiles know you're scanning), lifeboat and escape pod status, reactor signature monitoring, electromagnetic emissions from the target
- **Player-facing**: Sensor overlay on deck plan showing detected heat signatures and movement, confidence levels on contact identification, reactor status monitor, escape pod launch alerts, "new movement detected in compartment" notifications, scan resolution degradation in shielded sections

### Communications
- **Purpose**: Simulates the comms links between the player in CIC and the marine teams aboard the target — as well as potential communication with the hostiles, hostages, and the target ship's own internal systems
- **Key State**: Channel status per fire team (clear, degraded, lost), comms interference from hull structure and jamming, hostile comms intercept capability, fire team voice traffic, target ship internal comms (monitored if tapped), hailing channel to hostiles (negotiation, demands, ultimatums), signal relay through the breach point, comms blackout zones within the target
- **Player-facing**: Comms panel with per-team channel status, voice feed indicators, signal strength per team position, hostile comms intercept log, hailing controls for negotiation, comms blackout zone overlay on deck plan, "lost contact with team" alerts

### Medical & Injury
- **Purpose**: Simulates injuries sustained by marines during the boarding action — gunshot wounds, shrapnel, blast injuries, decompression exposure — tracked through biometric feeds and helmet cam footage
- **Key State**: Per-marine injury status (type, severity, bleed rate, consciousness), biometric feed (heart rate, blood pressure, blood oxygen, pain indicators), combat effectiveness degradation from wounds, field treatment applied (tourniquet, pressure seal, stimulant), casualty evacuation status (walking wounded, litter, KIA), medical supplies per team, triage priority
- **Player-facing**: Biometric dashboard per marine (heart rate graph, blood oxygen, injury alerts), casualty list with severity and evacuation status, combat effectiveness percentage per wounded marine, medical supply inventory per team, triage prompts when multiple casualties occur simultaneously, "this marine is no longer combat effective" notifications

### Security & Threat
- **Purpose**: Simulates the threat environment aboard the target ship — hostile disposition, booby trap detection, ambush risk, surrender evaluation, and the ongoing assessment of whether the operation is succeeding or sliding toward disaster
- **Key State**: Threat level per compartment (cleared, contested, hostile-controlled, unknown), booby trap detection confidence, ambush probability based on layout and hostile movement, surrender authenticity assessment, scuttling risk (are they going to blow the ship), hostage status and location confidence, overall mission threat trajectory (improving, stable, deteriorating), force ratio (marines vs. estimated hostiles remaining)
- **Player-facing**: Threat overlay on deck plan (cleared zones in green, contested in yellow, hostile in red, unknown in grey), booby trap warnings, surrender evaluation prompts with confidence percentage, scuttling risk indicator, overall mission status gauge, force ratio display

### NPC Identity & Personality
- **Purpose**: Gives each marine a persistent identity with skills, personality, experience, and stress responses — the player is commanding people, not game pieces, and individual marines will react differently to orders, stress, casualties, and moral dilemmas
- **Key State**: Name, rank, specialization (breacher, marksman, medic, demolitions, electronics), combat experience, stress tolerance, current stress level, trust in command (affected by player decisions), personality flags (aggressive, cautious, protective of teammates), reaction to casualties, willingness to follow high-risk orders, morale
- **Player-facing**: Marine roster with specialization badges and experience indicators, stress level per marine, trust indicators reflecting how the team feels about your calls, personality-driven dialogue in helmet cam audio (cautious marines questioning risky orders, aggressive marines pushing to advance), morale shifts after casualties or successful clears

### EVA & Spacewalk
- **Purpose**: Simulates the crossing between ships and any exterior hull movement — the marines must transit open space to reach the breach point, and exterior maneuvering may be required to access alternative entry points or recover casualties
- **Key State**: Transit status (crossing, at breach point, exterior hull movement), suit integrity, thruster fuel for maneuvering, tether status, exposure to point-defense or hostile fire during crossing, time in vacuum, suit atmosphere reserves, crossing distance and time
- **Player-facing**: Crossing status display, suit integrity per marine during transit, transit time countdown, exposure risk warning during crossing, exterior hull camera feed, alternative breach point accessibility via hull walk

### Power Grid
- **Purpose**: Simulates the target ship's power systems — which the player may choose to disable remotely to gain tactical advantage, or which may fail due to combat damage, affecting lighting, life support, and security systems aboard the target
- **Key State**: Target ship reactor status, power distribution per section, emergency lighting status, life support power, security system power (door locks, internal sensors, automated defenses), player's ability to cut power remotely from the *Harrow*, power failure cascade effects, emergency power reserves on the target
- **Player-facing**: Target ship power grid schematic, section-by-section power status, "cut power to this section" command interface, warnings about life support loss if power is cut, security system status indicators, emergency lighting indicators on deck plan

### Equipment & Repair
- **Purpose**: Simulates the condition of marine equipment under combat stress — breaching tools, weapons, comms gear, medical kits, suit systems — and the target ship's internal systems that may need to be repaired or bypassed
- **Key State**: Breaching tool charges remaining, cutting tool fuel, weapon maintenance status, comms relay integrity, medical kit supplies, suit system health per marine, target ship door lock bypass progress, target ship system access (can marines hack internal sensors, override door locks, access ship logs)
- **Player-facing**: Equipment status per team, breaching charges remaining counter, tool condition warnings, door bypass progress bars, "equipment degraded" alerts, target ship system access prompts

### Player Health
- **Purpose**: Tracks the player's cognitive state under the sustained pressure of commanding a live boarding operation — stress, fatigue, decision quality, and the psychological weight of sending people into danger from the safety of a chair
- **Key State**: Stress level, cognitive clarity, decision fatigue, emotional state (guilt after casualties, relief after successes), focus capacity (ability to monitor multiple feeds simultaneously), adrenaline, command presence (how steady the player sounds on comms, affecting marine morale)
- **Player-facing**: Screen effects (tunnel vision when fixating on one feed, information overload blur when too many things happen at once), stress indicators, decision quality warnings when fatigue is high, the persistent awareness that you are safe and they are not

## System Dependencies

### Hard Dependencies
- `Task & Workforce Management` --depends on--> `NPC Identity & Personality`: fire team composition and objective assignments require knowledge of each marine's specialization, experience, stress tolerance, and interpersonal dynamics
- `Combat & Weapons` --depends on--> `Task & Workforce Management`: engagements occur based on which teams are assigned to which objectives and in what order — the assault plan determines who fights where
- `Combat & Weapons` --depends on--> `Habitat Integrity`: weapons fire and breaching charges damage the target ship's structure; a firefight in a pressurized compartment risks decompression for everyone in it
- `Habitat Integrity` --depends on--> `Combat & Weapons`: every breach point the player orders cut, every grenade thrown, every hull-penetrating round creates structural damage that must be tracked and managed
- `EVA & Spacewalk` --depends on--> `Sensors & Scanning`: crossing between ships requires sensor data on the gap — debris, hostile point-defense arcs, target hull geometry

### Soft Dependencies
- `Task & Workforce Management` ~~depends on~~> `Sensors & Scanning`: better sensor data on the target ship lets the player make smarter assignments — sending teams to compartments with confirmed hostiles vs. unknowns
- `Task & Workforce Management` ~~depends on~~> `Communications`: lost comms with a team means lost control — the player cannot reassign or redirect teams they cannot reach
- `Task & Workforce Management` ~~depends on~~> `Medical & Injury`: casualties reduce available personnel and may require reallocating teams to evacuation instead of assault
- `Security & Threat` ~~depends on~~> `Sensors & Scanning`: threat assessment relies on sensor data — heat signatures, movement patterns, reactor behavior all feed into scuttling risk and ambush probability
- `Security & Threat` ~~depends on~~> `Communications`: intercepted hostile comms reveal intent; lost comms with marines means blind spots in the threat picture
- `Combat & Weapons` ~~depends on~~> `Power Grid`: cutting the target ship's power kills their lights and security systems but also removes life support — tactical advantage at humanitarian cost
- `Medical & Injury` ~~depends on~~> `EVA & Spacewalk`: evacuating critically wounded marines means getting them back across the gap to the *Harrow*'s medical bay — a dangerous transit under fire
- `NPC Identity & Personality` ~~depends on~~> `Medical & Injury`: watching teammates get wounded or killed affects marine stress, morale, and willingness to follow orders
- `Communications` ~~depends on~~> `Habitat Integrity`: hull damage and decompressed compartments create comms dead zones as relay paths are disrupted
- `Player Health` ~~depends on~~> `Medical & Injury`: every casualty notification on the biometric feed is a psychological hit to the player sitting safely in CIC

### Feedback Loops
- `Task & Workforce Management` <-> `Combat & Weapons` <-> `Medical & Injury`: The assault plan determines where firefights happen. Firefights produce casualties. Casualties reduce available marines. Fewer marines means the player must compress the plan, assign fewer people to more objectives, or pull teams back — which changes where the next firefights happen. Every casualty makes the next engagement more dangerous because the same work must be done with fewer people.
- `Combat & Weapons` <-> `Habitat Integrity` <-> `Security & Threat`: Breaching charges and firefights damage the target ship's structure. Structural damage creates decompression risks that threaten marines and hostages alike. Decompression forces compartment isolation, which funnels movement into predictable routes that hostiles can ambush. The violence of entry creates the conditions that make the interior more dangerous.
- `Sensors & Scanning` <-> `Security & Threat` <-> `Task & Workforce Management`: Sensor data informs threat assessment. Threat assessment drives team assignments. Team positions change the sensor geometry (marines with helmet cams provide close-range data that ship sensors cannot). Cleared compartments improve the sensor picture while contested ones remain uncertain. The fog of war lifts only where the player commits forces.
- `Communications` <-> `Task & Workforce Management` <-> `NPC Identity & Personality`: Command requires communication. Lost comms with a team means that team operates on last orders, guided by individual marines' judgment and personality. Aggressive marines push forward; cautious ones hold position. The player's assault plan degrades into individual decisions they cannot override until comms are restored. Marine trust in command drops when they feel abandoned in a blackout zone.
- `Power Grid` <-> `Habitat Integrity` <-> `Combat & Weapons`: Cutting the target's power gives marines a tactical edge (darkness, no security locks, no internal sensors for the enemy) but kills life support in those sections. Compartments go cold and start losing atmosphere. Hostages in unpowered sections are now on a timer. Marines in unpowered sections rely entirely on suit systems. The tactical advantage of darkness comes with a structural and humanitarian cost that compounds over time.

## Emergent Possibilities
- The player orders a hull breach into what sensors indicated was an empty cargo bay. The breach decompresses the bay, but the blast damage cracks the bulkhead into the adjacent compartment — where six hostages were being held. The player watches on the sensor feed as heat signatures go still. The breach point was correct. The deck plans were wrong. The marines haven't even boarded yet and people are already dead because of a decision made from a chair two hundred meters away.

- A fire team reports a group of four crew members surrendering with hands up. The player accepts the surrender and orders two marines to restrain and secure them. While the marines are zip-tying wrists, a fifth person detonates a concealed explosive in the corridor behind them. The surrender was real — those four genuinely wanted to give up. But the separatists used the predictable pause to position a bomber. The player now has two wounded marines, four terrified surrendered crew, and a team that no longer trusts any surrender. Every future encounter becomes lethal-first because of one decision to show restraint.

- Comms with Alpha team cut out as they enter the engineering section — too much hull shielding, too many bulkheads between them and the relay at the breach point. For eight minutes the player has only biometric feeds: heart rates climbing, two spikes that suggest weapons fire, one heart rate dropping steadily. The player must decide whether to send the reserve team in after them — committing the last uncommitted marines into a section they cannot communicate with — or wait, watching the biometrics, hoping the heart rates stabilize, knowing that every second of waiting might be a second too late.

## Inspiration
- *Aliens* (James Cameron) — commanding a squad through helmet cams from a remote operations center, watching a tactical situation disintegrate in real time
- *Rainbow Six* (Tom Clancy) — the planning phase matters as much as execution, breach point selection, team composition, go-codes
- *FTL: Faster Than Light* — managing crew assignments across ship compartments, fighting fires (literal and figurative) in multiple rooms simultaneously
- *XCOM* (Firaxis) — squad management, individual soldiers with persistent identities you care about, the weight of losing someone to a bad call
- *Star Trek: The Next Generation* — commanding from the bridge, making decisions through screens and comms, never holding the phaser yourself
- *The Expanse* (James S.A. Corey) — boarding actions in pressurized ships, the lethality of hull breaches, the tension of CIC command
