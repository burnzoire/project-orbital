# Scenario: Refugee Flotilla

## Narrative
The distress call comes in at 0340 station time, when half of Providence Station is asleep and the other half wishes they were. A flotilla of eleven ships — if you can call them ships — is decelerating hard on an intercept course. They're broadcasting on emergency frequencies, automated and manned, overlapping each other in a mess of static and desperation. The lead vessel identifies itself as the *Cana's Promise*, formerly registered to Helios-4, a sulfur-processing colony on Io's trailing trojans. Helios-4 doesn't exist anymore. Reactor containment failed eight weeks ago. The colony is cold, dark, and irradiated. These eleven ships are what got out.

There are fourteen hundred people in that flotilla. Men, women, children. You can see the ships on the long-range display and none of them look right — jury-rigged thrust assemblies, hull patches made from cargo container walls, one vessel that appears to be a mining barge with a pressurized tent bolted to its deck. They've been traveling for fifty-three days on drives that were never rated for sustained burn. They're running out of air. They're running out of water. They have wounded who've been lying in the same cots since the evacuation, and sick who are getting sicker in ships with failing atmosphere scrubbers.

Providence Station has a population of two thousand and resources scaled to match. Life support runs at eighty-two percent capacity on a good day. The water recyclers need an overhaul that keeps getting pushed back. The station has maybe three weeks of surplus food if nobody new shows up. And now fourteen hundred people are asking to come aboard.

The flotilla's de facto leader is a woman named Maren Vasik, former shift supervisor at Helios-4. She's calm on comms but you can hear the exhaustion underneath — she's been holding eleven ships and fourteen hundred terrified people together through force of will for almost two months. She's asking for docking clearance, medical assistance, food, water, and air. She's not demanding. Not yet. But the *Cana's Promise* has three hundred children aboard, and the youngest is four months old, and Maren Vasik is not going to let them die quietly.

Station Administrator Liang has called an emergency session. The council is already splitting. Councilor Davi Okonkwo is organizing a volunteer welcome committee and clearing space in the recreation decks. Councilor Petra Šelić is running the numbers and the numbers don't work — she's not heartless, but she can count, and she says taking on fourteen hundred people will put Providence below survival margins within ten days. Councilor Ruud Hendriks is on the comms telling anyone who'll listen that Helios-4 had a reputation for cutting corners, that the reactor failure was their own fault, that Providence shouldn't pay for their incompetence. He's getting traction. The dockworkers are worried about their jobs. The families in Ring B are worried about their children's air.

You're on this station. You know these people. You have standing, connections, resources — enough that when you speak, the room adjusts. The flotilla is six hours out. In six hours, Maren Vasik and fourteen hundred refugees will be close enough to see Providence through their portholes. What happens when they get here is partly up to you.

## Setting
- **Location type**: station (orbital)
- **Scale**: regional
- **Tone**: humanitarian, political, survival

## Player Agency
- **Open the doors**: Advocate full admission — take everyone in, figure out the logistics later, because turning away dying people is not something you can live with
- **Triage and select**: Push for partial admission — take the critically injured, the children, the most vulnerable, and send the rest onward with supplies. Choose who lives comfortably and who keeps drifting
- **Refuse entry**: Back Hendriks and the isolationists — Providence can't save everyone, and trying will kill both populations. Offer fuel and supplies but no docking clearance
- **Negotiate distribution**: Contact neighboring stations and settlements to distribute the refugees across multiple locations — spread the burden, but this takes time the flotilla may not have
- **Demand concessions**: Offer entry in exchange for labor contracts, resource rights, or political subordination — the refugees work for their air
- **Seize the opportunity**: Fourteen hundred desperate people with skills, knowledge, and nothing to lose. Recruit selectively. Build your own power base from their gratitude
- **Stabilize the flotilla**: Rather than dock them, organize repair crews and supply transfers to make the flotilla ships livable — keep the refugees close but off-station while longer-term solutions are negotiated
- **Take control**: The council is deadlocked and people are going to die while politicians argue. Push Liang aside and manage the crisis directly
- **Do nothing**: Stay out of it. Let the council decide. Keep your hands clean and your conscience dirty

## Resolution Paths
- **Best**: Full or partial admission succeeds — medical emergencies treated, refugees integrated or distributed to multiple stations, Providence strained but intact, player becomes a bridge between communities
- **Good**: Triage admission holds — the most vulnerable are saved, the flotilla is stabilized, neighboring stations agree to share the burden over time
- **Mixed**: Refugees admitted under harsh terms — indentured labor, segregated quarters, second-class status. They survive but resentment festers on both sides
- **Bad**: The council deadlocks, violence breaks out at the docks — refugees force entry or station security fires on desperate people. Deaths on one or both sides. Providence is scarred
- **Worst**: The flotilla is turned away and breaks apart — ships fail in transit, hundreds die in the void. Providence learns about it weeks later through comm intercepts. The station's reputation is destroyed, trade partners pull contracts, and the guilt hollows out the community from within

## Required Simulation Systems

### Food & Water Supply
- **Purpose**: Simulates production, storage, distribution, and consumption of food and water across the station and flotilla
- **Key State**: Station reserves (calories/days at current population), projected reserves if refugees admitted (full/partial), flotilla remaining supplies, water recycler capacity and load percentage, rationing tiers, spoilage rate, emergency reserve threshold, distribution logistics for dual-population supply chains
- **Player-facing**: Reserve countdown projections (with and without refugees), water recycler load warnings, rationing tier displays, flotilla supply status, hunger and thirst indicators on NPCs from both populations

### Social Dynamics
- **Purpose**: Simulates interpersonal relationships, group tensions, xenophobia, solidarity, and community cohesion under humanitarian pressure
- **Key State**: Station population morale (segmented by faction and ring), refugee morale, tension between station residents and refugees, xenophobia index, solidarity movements, rumor propagation, protest formation threshold, hate incident tracking, cultural friction points, altruism vs. selfishness index
- **Player-facing**: NPC mood and dialogue shifts, graffiti and vandalism appearing in corridors, volunteer sign-up boards vs. protest gatherings, visible solidarity or hostility between populations, refugee NPCs expressing gratitude or resentment depending on treatment

### Diplomacy & Negotiation
- **Purpose**: Simulates multi-party negotiation between station council, flotilla leadership, neighboring stations, and external authorities
- **Key State**: Parties involved (station council factions, Maren Vasik's flotilla leadership, neighboring station contacts), demands per party, red lines, willingness to negotiate, trust between parties, deal terms proposed/accepted/rejected, mediator credibility, communication lag with distant stations, leverage
- **Player-facing**: Negotiation dialogue, demand/offer interface, trust indicators, deal proposal system, inter-station communication delays, leverage assessment

### Faction System
- **Purpose**: Simulates organized groups with shared interests, hierarchies, resources, and agendas on both station and flotilla sides
- **Key State**: Faction name, leadership, membership roster, resources, grievances, demands, current stance, relationships with other factions, internal cohesion, willingness to use force. Key factions: Okonkwo's humanitarian coalition, Šelić's pragmatist bloc, Hendriks' isolationist movement, flotilla leadership council, dockworker union, Ring B families association
- **Player-facing**: Faction reputation display, dialogue reflecting faction stance, access/denial based on faction relations, faction actions visible in the world, splinter group formation, protest and counter-protest events

### Economy & Currency
- **Purpose**: Simulates economic impact of a sudden population influx — labor markets, price shocks, resource valuation, and trade disruption
- **Key State**: Local price index, commodity prices under scarcity pressure, labor market saturation, wage depression projections, trade contract status with external partners, refugee labor value, station budget strain, black market emergence for scarce goods
- **Player-facing**: Market price displays, labor market warnings, economic impact projections, trade partner sentiment, budget shortfall alerts, black market contacts

### Station Administration
- **Purpose**: Simulates station governance under crisis — authority, legitimacy, emergency powers, and the limits of democratic process under time pressure
- **Key State**: Administrator Liang's authority and competence, council composition and voting alignment, current policies, legitimacy rating, emergency powers status, security forces available, public communications, chain of command, docking authorization status
- **Player-facing**: Council session broadcasts, policy change announcements, emergency power declarations, legitimacy erosion indicators, docking authorization status, opportunities to influence or replace leadership

### Medical & Injury
- **Purpose**: Simulates medical needs of both station population and incoming refugees — triage, treatment capacity, contagion risk, and resource allocation
- **Key State**: Medical bay capacity (beds, staff, supplies), current patient load, incoming casualty projections, injury severity roster (flotilla wounded), disease and contagion risk from long-duration cramped spaceflight, quarantine protocols, medical supply reserves, staff exhaustion, triage priority queue
- **Player-facing**: Medical bay capacity display, incoming casualty briefings, contagion risk warnings, triage decision interface, medical supply countdown, staff fatigue indicators, quarantine zone status

### Reputation & Trust
- **Purpose**: Tracks how factions, individuals, and external entities perceive the player and each other — including the wider political consequences of the station's decision
- **Key State**: Reputation per faction (station and flotilla), trust per individual, history of actions, promises kept/broken, public perception, external reputation (how other stations and trade partners view Providence's response), refugee community trust in station leadership
- **Player-facing**: Reputation summary, NPC dialogue shifts, faction willingness to cooperate, consequences of broken promises, external trade partner sentiment, news broadcast reactions from other stations

### Security & Threat
- **Purpose**: Simulates security forces, civil unrest, dock confrontations, and escalation dynamics when desperate people meet locked doors
- **Key State**: Security force size and loyalty, rules of engagement, escalation level, dock security posture, weapons armed status, riot probability, flashpoint locations (docking ring, council chamber, refugee processing area), refugee desperation level, forced entry probability, hate crime incidents
- **Player-facing**: Security alerts, escalation status indicators, dock camera feeds, riot warnings, forced entry risk assessment, hate crime reports, patrol deployment options

### Fleet & Ship Movement
- **Purpose**: Simulates the flotilla's approach, individual ship conditions, docking logistics, and potential departure trajectories
- **Key State**: Ship positions and velocities, flotilla formation, individual ship hull integrity and life support status, docking port availability, docking queue and priority, departure vectors to alternate stations, fuel reserves per flotilla vessel, ship-to-ship transfer logistics
- **Player-facing**: Nav display with flotilla contacts, individual ship condition reports, docking port status, approach timeline, alternate destination calculations

### Communications
- **Purpose**: Simulates open and private communications between station, flotilla, neighboring stations, and external authorities
- **Key State**: Open channel traffic, private comm channels, flotilla distress broadcasts, inter-station diplomatic channels, media coverage, information known to each party, signal range and lag to neighboring stations, propaganda and counter-messaging
- **Player-facing**: Comm panel with open/private channels, flotilla broadcast content, inter-station message interface, media coverage tracking, ability to transmit/intercept/suppress information

### Time Pressure
- **Purpose**: Simulates the countdown of flotilla life support, medical emergencies, and political deadlines that compress every decision
- **Key State**: Hours until flotilla arrival, flotilla air reserves by ship, flotilla water reserves by ship, medical emergency timelines (patients who will die without treatment within X hours), council decision deadline, neighboring station response ETA, faction patience timers
- **Player-facing**: Flotilla arrival countdown, ship-by-ship life support projections, medical emergency tickers, council deadline display, inter-station response ETA, daily situation briefings

### NPC Identity & Personality
- **Purpose**: Gives non-player characters persistent identities, personalities, skills, motivations, and histories on both sides of the airlock
- **Key State**: Name, background, skills, personality traits, current motivation, trust level, loyalty, morale, health, dependents, faction affiliation, desperation threshold. Key NPCs: Maren Vasik (flotilla leader, exhausted but unbreakable), Davi Okonkwo (humanitarian councilor), Petra Šelić (pragmatist councilor), Ruud Hendriks (isolationist councilor), Administrator Liang (overwhelmed), Dr. Yuki Tanaka (station chief medical officer, already short-staffed), Tomasz Vasik (Maren's teenage son, injured in evacuation), Aisha Konte (refugee mother with sick infant)
- **Player-facing**: Dialogue reflecting personality and crisis state, observable behavior changes as pressure mounts, loyalty shifts, personal stories emerging through interaction, named refugee NPCs the player meets at docking

### Atmosphere Management
- **Purpose**: Simulates atmospheric composition, scrubber capacity, and the hard math of how much air exists for how many lungs
- **Key State**: Station atmospheric volume, O2 generation rate, CO2 scrubber capacity and current load, scrubber maintenance status, atmosphere quality by section, projected capacity at increased population, emergency reserve atmosphere, flotilla ship atmospheric status
- **Player-facing**: Atmosphere quality displays by section, scrubber load percentage, capacity projection warnings, emergency reserve status, flotilla ship atmosphere countdown

### Habitat Integrity
- **Purpose**: Simulates the physical condition of both station infrastructure and flotilla vessels — what can hold pressure and what is about to fail
- **Key State**: Station hull integrity by section, docking port structural ratings, maximum safe population density per section, flotilla ship hull integrity ratings, structural risk from jury-rigged flotilla vessels docking, maintenance backlog, emergency repair capacity
- **Player-facing**: Hull integrity displays, docking port stress warnings, population density alerts, flotilla ship condition reports, structural failure risk indicators

### Station Services & Infrastructure
- **Purpose**: Simulates the station's capacity to absorb a population increase — housing, sanitation, power, and all the systems that keep people alive beyond air and food
- **Key State**: Housing capacity and vacancy, temporary shelter availability, sanitation system load, power generation and distribution capacity, waste processing load, water recycler maintenance status, school and childcare capacity, corridor and common area crowding
- **Player-facing**: Infrastructure capacity dashboards, housing availability, sanitation overload warnings, power grid strain indicators, crowding alerts, temporary shelter setup options

## System Dependencies

### Hard Dependencies
- `Food & Water Supply` --depends on--> `Station Administration`: distribution policies and rationing tiers are set and enforced by governance
- `Diplomacy & Negotiation` --depends on--> `Faction System`: negotiations occur between factions with defined interests, structures, and red lines
- `Station Administration` --depends on--> `Security & Threat`: governance authority requires enforcement capability, especially at the docks
- `Social Dynamics` --depends on--> `NPC Identity & Personality`: group tensions and solidarity emerge from individual personalities, histories, and states
- `Medical & Injury` --depends on--> `Station Services & Infrastructure`: medical treatment requires functioning power, sanitation, and facilities

### Soft Dependencies
- `Faction System` ~~depends on~~> `Food & Water Supply`: faction positions harden or soften based on projected resource impact of refugee admission
- `Faction System` ~~depends on~~> `Reputation & Trust`: trust between factions affects willingness to compromise on refugee policy
- `Faction System` ~~depends on~~> `Social Dynamics`: xenophobic incidents or solidarity movements shift faction membership and influence
- `Economy & Currency` ~~depends on~~> `Food & Water Supply`: scarcity projections drive price inflation and hoarding behavior
- `Economy & Currency` ~~depends on~~> `Station Services & Infrastructure`: infrastructure strain affects economic productivity and trade capacity
- `Security & Threat` ~~depends on~~> `Social Dynamics`: tension between populations drives security escalation
- `Security & Threat` ~~depends on~~> `Faction System`: isolationist faction actions (dock protests, confrontations) create security events
- `Security & Threat` ~~depends on~~> `Time Pressure`: approaching flotilla increases urgency and raises stakes of every confrontation
- `Diplomacy & Negotiation` ~~depends on~~> `Reputation & Trust`: mediator credibility depends on reputation and history of fairness
- `Diplomacy & Negotiation` ~~depends on~~> `Communications`: inter-station negotiation requires functional comms with acceptable lag
- `Fleet & Ship Movement` ~~depends on~~> `Habitat Integrity`: docking jury-rigged flotilla ships risks structural damage to station ports
- `Fleet & Ship Movement` ~~depends on~~> `Time Pressure`: flotilla approach timeline drives every decision
- `Atmosphere Management` ~~depends on~~> `Station Services & Infrastructure`: scrubber capacity is constrained by power and maintenance infrastructure
- `Social Dynamics` ~~depends on~~> `Food & Water Supply`: resource scarcity amplifies xenophobia and erodes solidarity
- `Social Dynamics` ~~depends on~~> `Medical & Injury`: visible suffering (or visible treatment) shifts public sentiment
- `NPC Identity & Personality` ~~depends on~~> `Medical & Injury`: health status modifies NPC behavior, dialogue, and desperation threshold
- `Time Pressure` ~~depends on~~> `Fleet & Ship Movement`: flotilla approach speed and ship conditions set the countdown
- `Time Pressure` ~~depends on~~> `Atmosphere Management`: flotilla air reserves create the hardest deadlines

### Feedback Loops
- `Food & Water Supply` <-> `Faction System` <-> `Social Dynamics`: Resource scarcity projections fuel isolationist arguments; isolationist policy prevents refugee admission; refugees denied entry suffer visibly on comms, generating sympathy that strengthens humanitarian factions; humanitarian admission strains resources, validating isolationist warnings
- `Security & Threat` <-> `Social Dynamics` <-> `Faction System`: Xenophobic incidents trigger security crackdowns; crackdowns alienate moderates and radicalize both sides; faction polarization increases incident frequency; visible security presence at docks signals hostility to refugees, worsening first contact dynamics
- `Diplomacy & Negotiation` <-> `Time Pressure` <-> `Fleet & Ship Movement`: Shrinking flotilla life support compresses negotiation timelines; failed negotiations waste hours the refugees don't have; desperate flotilla may attempt forced docking, escalating the crisis beyond diplomacy
- `Medical & Injury` <-> `Social Dynamics` <-> `Faction System`: Visible refugee suffering (broadcast medical emergencies, dying children) shifts public opinion toward compassion; successful medical treatment builds goodwill; medical system overload affecting station residents fuels resentment and isolationist recruitment
- `Station Administration` <-> `Faction System` <-> `Diplomacy & Negotiation`: Council deadlock paralyzes governance; paralysis increases pressure from all factions; faction pressure forces snap decisions or triggers emergency powers; emergency powers erode legitimacy, weakening the administration's ability to enforce whatever it decides
- `Atmosphere Management` <-> `Station Services & Infrastructure` <-> `Food & Water Supply`: Admitting refugees increases atmospheric load; overloaded scrubbers require more power and maintenance; diverted maintenance resources degrade other infrastructure; infrastructure degradation reduces food production capacity; reduced food worsens the resource crisis that drives the political conflict

## Emergent Possibilities
- Aisha Konte's infant is dying of a respiratory infection treatable with standard antibiotics that the flotilla ran out of weeks ago. Dr. Tanaka can save the child in twenty minutes if given docking clearance for one medical shuttle. Hendriks argues that one exception becomes a flood. The player can push for the medical shuttle, smuggle Tanaka aboard the flotilla, or watch the situation play out on open comms while the council argues — and if that baby dies on a broadcast frequency, the political landscape shifts overnight
- Maren Vasik privately reveals that one of the flotilla ships — the *Kersey's Folly* — is carrying survivors who were actually responsible for the maintenance failures that caused the Helios-4 reactor breach. She's been protecting them because they have families too. If this information leaks, it could destroy sympathy for the entire flotilla and validate Hendriks' narrative. The player must decide whether to bury it, use it as leverage, or let the truth out
- A group of Providence dockworkers — people who fix ships for a living — quietly ignore the council deadlock and start sending repair parts and atmosphere patches to the flotilla on their own. This unauthorized aid buys time but infuriates the isolationists and puts the dockworkers at legal risk. The player can support them openly, help them stay hidden, or shut them down
- Tomasz Vasik, Maren's injured teenage son, manages to patch into Providence's local network from the *Cana's Promise* and starts posting firsthand accounts of conditions aboard the flotilla — names, faces, stories. Station residents who were abstract about "fourteen hundred refugees" start seeing specific human beings. Hendriks wants the signal jammed. Okonkwo wants it amplified. The information war becomes as important as the resource math

## Inspiration
- *Battlestar Galactica* — the fleet's arrival at new settlements, civilian ship conditions, Adama's impossible resource decisions, the *Pegasus* encounter
- *The Expanse* — Belter refugee crises, Ganymede aftermath, the Ilus colonists, Naomi's flotilla
- *Children of Men* (Alfonso Cuaron) — the refugee camp sequences, humanitarian crisis rendered at human scale
- *Station Eleven* (Emily St. John Mandel) — communities deciding who they let in after catastrophe
- *The Dispossessed* (Ursula K. Le Guin) — the moral weight of borders, resource sharing between unequal societies
