# Scenario: Colony Food Crisis

## Narrative
You've been on Kepler's Reach for six weeks — a mid-size settlement bored into the basalt of a tidally locked moon, home to roughly four thousand people who mine rare earths and export refined alloys. It's not a bad posting. Or it wasn't, until the blight hit. Hydroponics Bay 3 went first, some fungal pathogen that ate through the soybean crop in days. Then the protein vats in the lower levels started producing biomass that made people sick — contamination in the feedstock, maybe sabotage, nobody knows yet. The backup greenhouses are producing at maybe fifteen percent capacity. The colony's food reserves, which were never more than a few weeks deep, are burning down fast.

Rationing started three days ago. Administration announced it as "temporary caloric adjustment" and nobody believed them. The miners are furious — they burn five thousand calories a day on shift and they're getting allotments sized for desk workers. The research staff say their work is critical and they should be prioritized. The families in the residential ring are hoarding what they can and locking their doors at night. A supply ship from Ceres is nineteen days out. Nineteen days is a long time when your children are hungry and the neighbor has a full pantry they won't share.

You're not in charge here, but you have connections, resources, and enough standing that people listen when you talk. The station administrator is overwhelmed and making bad calls. The security chief is one riot away from declaring martial law. Someone in the merchant quarter is already selling protein bars at ten times the going rate. And there are rumors — credible ones — that a faction of miners is planning to seize the remaining food stores by force. You can try to hold this place together, or you can make sure you and yours survive what's coming. Either way, the clock is the growling in four thousand stomachs.

## Setting
- **Location type**: colony (subsurface)
- **Scale**: local
- **Tone**: political, survival

## Player Agency
- **Support rationing**: Back the administration's plan, help enforce fair distribution, maintain order
- **Reform the system**: Push for a new rationing formula — calorie-weighted by labor output, medical need, or age
- **Side with the miners**: Help them pressure administration for larger shares — or look the other way when they take what they need
- **Protect the vulnerable**: Focus on families, children, elderly, and medical patients — organize a shadow distribution network
- **Seize control**: Convince or coerce the administrator to step aside, take over crisis management directly
- **Play the black market**: Stockpile food, control supply, sell at premium — profit from desperation
- **Investigate the contamination**: Find out whether the protein vat failure was accident or sabotage — and who benefits
- **Call for outside help**: Attempt to reroute closer ships, negotiate emergency supply drops, or arrange evacuation of non-essential personnel
- **Do nothing**: Keep your head down, conserve your own supplies, wait for the ship from Ceres

## Resolution Paths
- **Best**: Identify and fix the contamination source, restore partial food production, implement fair rationing, and hold the colony together until resupply — player becomes a trusted community leader
- **Good**: Rationing holds, tensions are managed through negotiation, no violence erupts — colony survives bruised but intact
- **Mixed**: Order is maintained but at a cost — martial law, broken trust, faction grudges that will fester long after the food arrives
- **Bad**: Riots break out, food stores are raided, people are hurt — the colony survives physically but its social fabric is torn apart
- **Worst**: Full collapse — factional violence, food stores destroyed or hoarded by a few, deaths from starvation or conflict, colony abandoned or placed under external authority

## Required Simulation Systems

### Food & Water Supply
- **Purpose**: Simulates production, storage, distribution, and consumption of food and water across a settlement
- **Key State**: Production sources (hydroponics, protein vats, greenhouses) with individual capacity and health status, total reserves (calories/days), consumption rate per population segment, distribution method (open/rationed/black market), spoilage rate, contamination status, nutritional quality, water recycling efficiency
- **Player-facing**: Food reserve countdown, production status dashboards, rationing tier displays, hunger indicators on NPCs, spoilage warnings, contamination alerts, black market price tracking

### Faction System
- **Purpose**: Simulates organized groups with shared interests, hierarchies, resources, and agendas
- **Key State**: Faction name, leadership, membership roster, resources, grievances, demands, current stance (negotiating/hostile/allied), relationships with other factions, internal cohesion, willingness to use force
- **Player-facing**: Faction reputation display, dialogue reflecting faction stance, access/denial based on faction relations, faction actions visible in the world, splinter group formation

### Diplomacy & Negotiation
- **Purpose**: Simulates multi-party negotiation, demands, concessions, and deal-making
- **Key State**: Parties involved, demands per party, red lines, willingness to negotiate, trust between parties, deal terms proposed/accepted/rejected, mediator credibility, leverage (who controls what resources)
- **Player-facing**: Negotiation dialogue, demand/offer interface, trust indicators, deal proposal system, leverage assessment

### Economy & Currency
- **Purpose**: Simulates money flows, pricing, black markets, and economic pressure under scarcity
- **Key State**: Local price index, commodity prices (food inflated, everything else deflated), black market markup, player account balance, wage disruptions, trade contracts, hoarding levels, price controls (if enacted)
- **Player-facing**: Market price displays, black market contacts, inflation warnings, economic impact of policy decisions, profiteering alerts

### Station Administration
- **Purpose**: Simulates colony governance — authority, policy, legitimacy, and the limits of bureaucratic control
- **Key State**: Administrator identity and competence, current policies (rationing tiers, martial law, curfews), legitimacy rating, security forces available, public communications, emergency powers status, chain of command
- **Player-facing**: Admin broadcasts, policy change announcements, security posture shifts, legitimacy erosion indicators, opportunities to influence or replace leadership

### Social Dynamics
- **Purpose**: Simulates interpersonal relationships, group tensions, mob psychology, and community cohesion
- **Key State**: Population morale (segmented by group), tension level, grievance accumulation, rumor propagation, trust between population segments, mob formation threshold, altruism vs. selfishness index, community events
- **Player-facing**: NPC mood and dialogue shifts, crowd behavior, rumor mill, visible signs of social breakdown or solidarity, community gathering events

### NPC Identity & Personality
- **Purpose**: Gives non-player characters persistent identities, personalities, skills, motivations, and histories
- **Key State**: Name, background, skills, personality traits, current motivation, trust level, loyalty, morale, hunger level, health, dependents, faction affiliation, desperation threshold
- **Player-facing**: Dialogue reflecting personality and hunger state, observable behavior changes as desperation increases, loyalty shifts, willingness to break laws for food

### Reputation & Trust
- **Purpose**: Tracks how factions and individuals perceive the player and each other
- **Key State**: Reputation per faction, trust per individual, history of actions, promises kept/broken, public perception, perceived fairness of player decisions
- **Player-facing**: Reputation summary, NPC dialogue shifts, faction willingness to cooperate, consequences of broken promises, public opinion indicators

### Security & Threat
- **Purpose**: Simulates security forces, civil unrest, crime, and escalation toward violence
- **Key State**: Security force size and loyalty, rules of engagement, escalation level, crime rate, riot probability, weapons availability, curfew enforcement, flashpoint locations, informant network
- **Player-facing**: Security alerts, crime reports, riot warnings, curfew notifications, escalation status indicators, patrol presence in different sectors

### Time Pressure
- **Purpose**: Simulates the countdown to resupply and the mounting consequences of each passing day
- **Key State**: Days until resupply ship arrival, daily calorie deficit, reserve depletion rate, health deterioration timeline, faction patience timers, event escalation schedule
- **Player-facing**: Resupply countdown display, reserve projections, health decline warnings, faction ultimatum deadlines, daily situation briefings

### Player Health
- **Purpose**: Simulates the player's own physical condition, including the effects of hunger and stress
- **Key State**: Calorie intake, hydration, fatigue, stress level, cognitive impairment from malnutrition, injury status, immune function
- **Player-facing**: Health status display, hunger and fatigue indicators, performance debuffs from malnutrition, stress-induced dialogue options

## System Dependencies

### Hard Dependencies
- `Food & Water Supply` --depends on--> `Station Administration`: distribution policies are set and enforced by governance
- `Diplomacy & Negotiation` --depends on--> `Faction System`: negotiations occur between factions with defined interests and structures
- `Station Administration` --depends on--> `Security & Threat`: governance requires enforcement capability
- `Social Dynamics` --depends on--> `NPC Identity & Personality`: group dynamics emerge from individual personalities and states

### Soft Dependencies
- `Faction System` ~~depends on~~> `Food & Water Supply`: faction grievances are driven by hunger and perceived unfairness of distribution
- `Faction System` ~~depends on~~> `Reputation & Trust`: trust between factions affects willingness to negotiate or cooperate
- `Economy & Currency` ~~depends on~~> `Food & Water Supply`: food scarcity drives price inflation and black market emergence
- `Security & Threat` ~~depends on~~> `Social Dynamics`: civil unrest and mob formation drive security escalation
- `Security & Threat` ~~depends on~~> `Faction System`: faction actions (raids, protests) create security events
- `Diplomacy & Negotiation` ~~depends on~~> `Reputation & Trust`: mediator credibility depends on reputation and history of fairness
- `Player Health` ~~depends on~~> `Food & Water Supply`: player is subject to the same scarcity as everyone else
- `Social Dynamics` ~~depends on~~> `Food & Water Supply`: hunger degrades morale, increases tension, lowers cooperation threshold
- `Time Pressure` ~~depends on~~> `Food & Water Supply`: reserve depletion rate sets the urgency of every decision
- `NPC Identity & Personality` ~~depends on~~> `Food & Water Supply`: hunger level modifies NPC behavior, loyalty, and desperation threshold

### Feedback Loops
- `Food & Water Supply` <-> `Faction System` <-> `Security & Threat`: Unequal food distribution creates faction grievances; faction actions (raids, hoarding) reduce available food supply; security crackdowns restore order but consume resources and deepen resentment
- `Social Dynamics` <-> `Security & Threat`: Rising tension triggers security response; heavy-handed security deepens social breakdown; social cohesion reduces need for security intervention
- `Diplomacy & Negotiation` <-> `Faction System` <-> `Station Administration`: Administration policies drive faction demands; negotiation outcomes reshape policy; faction pressure forces administrative concessions or triggers authoritarian response
- `Economy & Currency` <-> `Food & Water Supply` <-> `Social Dynamics`: Scarcity drives prices up; high prices increase desperation and resentment; black markets emerge to fill gaps but deepen inequality; inequality fuels social tension
- `Time Pressure` <-> `Faction System` <-> `Diplomacy & Negotiation`: Shrinking reserves increase faction urgency; urgent factions make harder demands; failed negotiations waste time the colony does not have

## Emergent Possibilities
- A mid-level technician confesses she can fix the protein vats but needs components that are locked in a storage bay controlled by a hostile faction — the player must negotiate, steal, or trade to get them, turning an engineering problem into a political one
- The black market food dealer turns out to be stockpiling not for profit but to feed an entire hidden sector of undocumented workers the administration pretends don't exist — exposing them gets more mouths added to rationing, but hiding them means people starve in the dark
- A group of children organizes their own food-sharing network across faction lines, shaming the adults into temporary cooperation — but only if the player protects them from a security chief who sees unauthorized distribution as a crime

## Inspiration
- *The Expanse* — Belter resource scarcity, air and water as political leverage, Anderson Dawes rationing on Ceres
- *Battlestar Galactica* — fleet-wide food shortages, black markets, civilian unrest under military authority
- *The Road* (Cormac McCarthy) — what people become when sustenance is not guaranteed
- *Mars* (National Geographic series) — colony governance under resource pressure, science vs. survival priorities
