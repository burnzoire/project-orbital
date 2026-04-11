# Scenario: Port Surveillance

## Narrative
You've been tracking the *Dawnkeeper* for three days across two transit corridors. Flagged by a corporate compliance bureau for suspected contraband runs, the vessel matches a pattern — irregular course corrections, transponder blackouts near relay stations, refueling at depots that don't appear in standard directories. Your contract is simple: confirm the cargo, identify the buyer, transmit the evidence. Clean intelligence work. No boarding, no confrontation.

The *Dawnkeeper* decelerates into Meridian Hub — a sprawling trade station at the junction of three shipping lanes, tens of thousands of residents, hundreds of docked ships at any given time. Your sensors track her into a berth on the eastern arm. You dock two berths down, close enough to watch the cargo locks, far enough not to draw attention. And then the job changes. Nothing comes off the ship. Instead, a woman in a maintenance jacket walks off the crew ramp, alone, carrying nothing but a personal bag. She moves like someone who knows she might be watched — not running, not hiding, just... careful.

The pursuit shifts from ship-scale to person-scale. You leave your cockpit and follow her into the station on foot. Through the main concourse with its press of bodies and vendor stalls. Down a transit elevator to the mid-ring market district where the crowd thickens and sightlines shorten. She checks her reflection in a shop window — or checks behind her. She doubles back through a food court. She takes a maintenance corridor that isn't on the public station map. You follow at distance, navigating by sound and signage meant for station engineers, until she emerges in the lower ring — a residential district of capsule hotels, unlicensed bars, and service workers who mind their own business.

She enters the Sable Rest, a hotel that rents rooms by the hour and doesn't scan IDs. You wait. Twenty minutes later, two more people arrive separately. You find a maintenance alcove with thin walls and a ventilation grille, and you listen. What you hear isn't a drug deal or a weapons transaction. It's a medical logistics discussion. Dosage quantities. Cold chain requirements. Pediatric formulations. The cargo in the *Dawnkeeper* is medical supplies — antibiotics, surgical kits, cancer treatment compounds — destined for Korren's Reach, a colony that's been under a corporate trade blockade for eight months. The blockade is legal. The colony is dying. And the people in that room are trying to save it.

Your contract says report. The law says this is smuggling. The blockade exists because Korren's Reach defaulted on development loans, and the corporation that holds the debt is starving them into compliance. Children are sick. The supply run is funded by a loose network of dock workers, medical professionals, and sympathetic merchants — people spending their own money and risking prison. The woman you followed is a nurse who used to work at the colony hospital before the blockade. She's not a criminal. But legally, she is. And so is everyone helping her. You have a recording. You have faces. You have a contract that pays well. What you don't have is a clean conscience in any direction.

## Setting
- **Location type**: station (interior, multi-scale)
- **Scale**: local
- **Tone**: espionage, moral, procedural

## Player Agency
- **Report as contracted**: Transmit the intelligence to the compliance bureau — fulfill the contract, get paid, and let the legal system handle the rest
- **Walk away**: Delete the evidence, abandon the contract, lose the pay, keep your hands clean of all of it
- **Join the supply run**: Offer your ship and skills to help deliver the medical cargo — break the law, void the contract, risk criminal charges
- **Blackmail the smugglers**: Leverage what you know for money, favors, or a cut of future operations
- **Renegotiate the contract**: Go back to the compliance bureau with partial information, attempt to steer the outcome or extract better terms
- **Investigate the blockade**: Dig into the legality and morality of the blockade itself — look for leverage to challenge it through legal or political channels
- **Warn and withdraw**: Tip off the smugglers that they've been tracked, then disappear — no profit, but no one goes to prison because of you
- **Play both sides**: Feed the bureau enough to keep the contract alive while helping the smugglers change their methods to avoid future detection

## Resolution Paths
- **Best**: Uncover evidence that the blockade violates humanitarian statutes, leverage it to force a legal exemption for medical supplies — smugglers protected, colony supplied, player reputation elevated with multiple factions
- **Good**: Help the supply run succeed without being detected — medical cargo reaches Korren's Reach, player forfeits the contract payment but gains deep trust with the humanitarian network
- **Mixed**: Report the smugglers but include enough context about the blockade that the bureau's response is delayed and softened — contract fulfilled, smugglers get a warning window, nobody fully trusts you
- **Bad**: Blackmail attempt goes wrong — smugglers have allies on the station who take the threat seriously and make the player's stay at Meridian Hub dangerous
- **Worst**: Full report leads to arrests, supply seizure, and public exposure of the network — the colony's medical crisis deepens, the player is paid but becomes known as the person who helped a corporation starve sick children

## Required Simulation Systems

### Sensors & Scanning
- **Purpose**: Simulates the ship-phase pursuit — detecting, tracking, and analyzing a target vessel across long distances before the scenario transitions to on-foot surveillance
- **Key State**: Sensor range, resolution, target lock status, transponder signatures, emission profiles, scan history, signal noise ratio, passive vs. active scan mode, detection risk (chance target knows they're being scanned)
- **Player-facing**: Sensor display with target bearing and range, transponder ID readouts, emission anomaly alerts, scan mode toggle (passive is stealthy but low-detail, active is precise but detectable), tracking log that records course changes and blackout windows

### NPC Identity & Personality
- **Purpose**: Gives every character a persistent inner life that drives their behavior during surveillance, confrontation, and moral negotiation — from the nurse's quiet determination to a hotel clerk's practiced disinterest
- **Key State**: Name, background, occupation, personality traits, motivation, secrets held, fear level, loyalty allegiances, trust toward player, trust toward other NPCs, awareness of being watched, behavioral tells (nervousness, countersurveillance habits), moral conviction strength
- **Player-facing**: Observable body language during tailing (pace changes, route doubling, reflection checks), dialogue that shifts based on how the player approaches them, NPCs who react differently to threats vs. appeals to conscience, informants whose reliability depends on personality

### Station Services & Infrastructure
- **Purpose**: Simulates Meridian Hub as a layered physical environment where the pursuit plays out — from public concourses to maintenance corridors to lower-ring hotels, each with different rules, access, and surveillance coverage
- **Key State**: Station layout (rings, sectors, levels, public vs. restricted areas), access permissions, surveillance camera coverage and blind spots, maintenance corridor network, crowd density per area, hotel/lodging registries, vendor locations, environmental noise levels, ventilation and utility access points
- **Player-facing**: Crowd density affecting line-of-sight during tailing, maintenance corridors as shortcuts or alternate routes, surveillance cameras the player must avoid while following a target, thin walls and ventilation grilles that allow eavesdropping, lower-ring areas with minimal security presence and no ID checks

### Law & Jurisdiction
- **Purpose**: Simulates the legal frameworks that make this scenario a genuine dilemma — the blockade is legal, the smuggling is illegal, but the humanitarian dimension complicates enforcement and creates jurisdictional grey areas
- **Key State**: Governing legal authority, applicable trade laws, blockade legality and enforcement provisions, contraband definitions, humanitarian exemption statutes (if any), corporate enforcement rights, smuggling penalties, evidentiary standards, whistleblower protections, jurisdictional overlaps between station law, transit law, and corporate charter
- **Player-facing**: Awareness that reporting is legally straightforward but morally complex, ability to research blockade legality at station legal terminals, option to file humanitarian challenges, legal consequences displayed for different choices, jurisdictional gaps the player can exploit

### Reputation & Trust
- **Purpose**: Tracks the cascading social consequences of the player's choice — every option burns trust with someone, and the scenario is designed so that no path leaves all relationships intact
- **Key State**: Reputation per faction (compliance bureau, smuggler network, station locals, Korren's Reach sympathizers), trust per individual NPC, known associations, promises made/kept/broken, perceived allegiance, professional reputation (reliability as a contractor), moral reputation (how people judge you as a person)
- **Player-facing**: Contract employers who judge reliability based on follow-through, smugglers who extend or revoke trust based on player actions, station locals who have opinions about blockade politics, long-term reputation consequences that affect future contract offers and faction access

### Communications
- **Purpose**: Simulates the information channels that define the scenario — contract communications, surveillance recordings, encrypted smuggler coordination, and the player's ability to transmit, withhold, or fabricate intelligence
- **Key State**: Communication channels (contract uplink, local comms, encrypted channels), message logs, recording devices and stored evidence, signal encryption levels, transmission delay to contract bureau, interception risk, dead drops, smuggler communication network topology
- **Player-facing**: Ability to transmit or withhold recorded evidence, encrypted channels the player can attempt to access, transmission delay that creates a decision window, option to send anonymous warnings, comm traffic analysis that reveals network structure

### Economy & Currency
- **Purpose**: Simulates the financial pressures on all sides — the player's contract payment, the smugglers' shoestring funding, the blockade's economic logic, and the costs of every moral choice
- **Key State**: Player account balance, contract payment terms (on delivery of intelligence), smuggler network funding, medical supply market value, blockade economic impact on Korren's Reach, black market rates at Meridian Hub, bribe costs, cost of fuel and provisions for a supply run, financial records linking the blockade to corporate debt enforcement
- **Player-facing**: Contract payment amount clearly displayed as a stake, cost calculations for joining the supply run, financial evidence of blockade profiteering if investigated, visible economic desperation of the smuggler network (people spending savings, selling personal items)

### Security & Threat
- **Purpose**: Simulates the enforcement layer at Meridian Hub — station security patrols, corporate compliance enforcement, and the smugglers' own countersurveillance measures that the player must navigate during and after the tailing sequence
- **Key State**: Station security patrol routes, security alert level, corporate compliance agents (present or remote), smuggler countersurveillance capability, player detection risk level, security response protocols, detention authority, evidence handling procedures
- **Player-facing**: Security patrols that constrain movement during tailing, risk of being identified as a surveillance operative by the smugglers' lookouts, station security response if the player is caught in restricted areas, corporate enforcement timeline if a report is filed

### Navigation & Fuel
- **Purpose**: Simulates the ship-phase tracking and the logistical reality of any choice that involves flying somewhere — joining the supply run means fuel, route planning, and blockade navigation
- **Key State**: Current fuel reserves, burn rate, distance to Korren's Reach, blockade patrol patterns around the colony, alternate route options, fuel costs at Meridian Hub, travel time estimates, nav hazards near blockaded space
- **Player-facing**: Fuel gauge reflecting the cost of commitment (joining the run means burning reserves), route planner showing the blockade zone, nav computer calculating risk profiles for different approaches to the colony, travel time that creates urgency for the medical supplies

## System Dependencies

### Hard Dependencies
- `Law & Jurisdiction` --depends on--> `Station Services & Infrastructure`: station legal authority is defined by its charter and governs what happens within its physical boundaries
- `Security & Threat` --depends on--> `Law & Jurisdiction`: security enforcement actions, detention authority, and rules of engagement are defined by legal framework
- `Communications` --depends on--> `Station Services & Infrastructure`: communication systems are physical infrastructure with access points, ranges, and vulnerabilities within the station
- `Navigation & Fuel` --depends on--> `Sensors & Scanning`: ship-phase tracking requires sensor data to follow the target vessel's course

### Soft Dependencies
- `NPC Identity & Personality` ~~depends on~~> `Reputation & Trust`: NPC willingness to speak, help, or warn the player is gated by trust and perceived allegiance
- `NPC Identity & Personality` ~~depends on~~> `Security & Threat`: NPC countersurveillance behavior intensifies when security presence or detection risk increases
- `Sensors & Scanning` ~~depends on~~> `Navigation & Fuel`: sensor effectiveness degrades with distance; fuel constraints limit how long the player can maintain a tracking position
- `Law & Jurisdiction` ~~depends on~~> `Economy & Currency`: the blockade's legal basis is economic (debt enforcement); financial evidence can challenge or reinforce its legitimacy
- `Law & Jurisdiction` ~~depends on~~> `Communications`: filing legal challenges, transmitting evidence, and contacting outside authorities require communication channels
- `Reputation & Trust` ~~depends on~~> `Communications`: what the player transmits (or is known to have transmitted) directly affects how factions perceive them
- `Security & Threat` ~~depends on~~> `Reputation & Trust`: security response escalates based on player heat level; smuggler countersurveillance intensifies if the player is perceived as a threat
- `Economy & Currency` ~~depends on~~> `Station Services & Infrastructure`: black market operations, hotel transactions, and bribe opportunities exist within station infrastructure

### Feedback Loops
- `Sensors & Scanning` -> `NPC Identity & Personality` -> `Station Services & Infrastructure`: Ship-phase tracking reveals the target's destination; the target's on-foot countersurveillance behavior determines which station areas the pursuit passes through; station layout constrains and enables surveillance options
- `Reputation & Trust` <-> `Communications` <-> `Law & Jurisdiction`: What the player reports (or fails to report) reshapes their reputation; reputation determines what legal options and faction contacts remain available; legal outcomes generate communications that further alter reputation
- `Security & Threat` <-> `NPC Identity & Personality` <-> `Reputation & Trust`: Security pressure makes NPCs cautious and harder to approach; NPC behavior changes based on who they think the player is; player reputation determines whether security treats them as an asset or a suspect
- `Economy & Currency` <-> `Law & Jurisdiction` <-> `Reputation & Trust`: The blockade's economic logic creates the legal framework; challenging the legal framework threatens economic interests; economic actors retaliate through reputation damage and contract blacklisting

## Emergent Possibilities
- The player discovers that the compliance bureau already knows the cargo is medical supplies — the contract isn't about law enforcement, it's about a corporation mapping the humanitarian network so they can shut it down permanently, making the player an unwitting tool of the blockade's cruelest dimension
- While tailing the nurse through the maintenance corridors, the player is spotted not by her but by a station maintenance worker who assumes the player is a stalker and alerts station security — the player must talk their way out of detention without revealing the real reason they were there
- A second surveillance operative is tracking the same target for a different client — the player spots them during the tail, and must decide whether to make contact, compete, or use the other operative as a decoy to maintain their own cover
- The smuggler network includes a station security officer who has been diverting patrol routes to create safe windows for cargo transfers — if the player reports, that officer's career and family are destroyed alongside the medical network

## Inspiration
- *Tinker Tailor Soldier Spy* (film/novel) — patient surveillance, moral ambiguity in intelligence work, the weight of what you learn
- *The Conversation* (film) — surveillance as intimacy, the horror of knowing too much, the listener's moral culpability
- *The Expanse* — corporate blockades, Belter medical crises, the politics of who deserves to live
- *Deus Ex* (game) — player choice in morally grey scenarios, corporate power vs. human need
- *Blade Runner* (film) — following a subject through layered urban spaces, empathy as a complication
