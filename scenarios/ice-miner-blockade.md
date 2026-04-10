# Scenario: Ice Miner Blockade

## Narrative
You're on final approach to Hestia Station — a mid-belt refinery hub, nothing glamorous but it has the parts you need and a dry dock that won't ask questions. Except you're not docking today. Your nav display is cluttered with transponder signatures: dozens of mining haulers arranged in a loose cordon around the station's approach vectors. The ice miners' guild has had enough.

Three months of unpaid wages. Broken contracts. A station administration that keeps promising payments "next cycle" while the executive tier still has pressurized champagne in their lounges. The miners have blocked the shipping lanes, and they're broadcasting on open channels: nobody docks, nobody departs, until they get paid. Station security is holding position but hasn't engaged — half of them are sympathetic, and the other half know the miners outnumber them ten to one.

You're burning fuel on a holding pattern. Your ship needs that dry dock. You have cargo that's losing value by the hour. You can divert to another station — days of extra travel and fuel you can barely afford. You can try to talk your way through the blockade. You can try to run it. Or you can get involved — take a side, broker a deal, or exploit the chaos. Everyone here is desperate, and desperate people create opportunities.

## Setting
- **Location type**: station (approach/exterior)
- **Scale**: regional
- **Tone**: political, economic

## Player Agency
- **Divert**: Plot course to another station — safe but costly in fuel, time, and cargo value
- **Negotiate passage**: Attempt to convince blockade leaders to let you through as a neutral party
- **Run the blockade**: Fly through the cordon — risk confrontation with armed mining vessels
- **Side with miners**: Help them pressure the station (deliver supplies, amplify their broadcast, intimidate scabs)
- **Side with station**: Offer to help break the blockade in exchange for docking priority, discounts, or favors
- **Broker a deal**: Position yourself as a mediator — high risk, high reward if successful
- **Exploit the chaos**: Smuggle goods past the blockade at inflated prices, play both sides
- **Wait it out**: Hold position, conserve fuel, see how it unfolds — but costs mount

## Resolution Paths
- **Best**: Broker a fair resolution — miners paid, station functional, player gains reputation with both sides and docks for free
- **Good**: Negotiate passage without taking sides — dock and leave before things escalate
- **Mixed**: Take a side and succeed — accomplish goals but make enemies
- **Bad**: Attempt to run the blockade and take damage or get turned back
- **Worst**: Situation escalates to violence while player is caught in the middle — ship damaged, cargo lost, trapped in a warzone

## Required Simulation Systems

### Faction System
- **Purpose**: Simulates organized groups with shared interests, hierarchies, resources, and agendas
- **Key State**: Faction name, leadership, membership roster, resources, grievances, demands, current stance (negotiating/hostile/allied), relationships with other factions, internal cohesion
- **Player-facing**: Faction reputation display, dialogue reflecting faction stance, access/denial based on faction relations, faction actions visible in the world

### Economy & Currency
- **Purpose**: Simulates money flows, debts, trade, and economic grievances
- **Key State**: Wage ledgers, debt records, commodity prices, trade route values, cargo depreciation rates, fuel costs, contract terms
- **Player-facing**: Cargo value ticking down, fuel cost calculations, contract and debt information, price differences between stations

### Fleet & Ship Movement
- **Purpose**: Simulates the positions, movements, and formations of multiple ships in space
- **Key State**: Ship positions, velocities, formation patterns, approach vectors, patrol routes, fuel reserves per ship, transponder data
- **Player-facing**: Nav display with ship contacts, transponder IDs, formation patterns visible, approach/departure vectors

### Diplomacy & Negotiation
- **Purpose**: Simulates multi-party negotiation, demands, concessions, and deal-making
- **Key State**: Parties involved, demands per party, red lines, willingness to negotiate, trust between parties, deal terms proposed/accepted/rejected, mediator credibility
- **Player-facing**: Negotiation dialogue, demand/offer interface, trust indicators, deal proposal system

### Station Administration
- **Purpose**: Simulates station governance — who runs it, their priorities, their resources, their corruption
- **Key State**: Administration leadership, budget/treasury, policies, corruption level, security forces, public sentiment, docking queue, service availability
- **Player-facing**: Admin communications, policy announcements, security posture changes, docking permissions

### Navigation & Fuel
- **Purpose**: Simulates route planning, fuel consumption, and travel time between locations
- **Key State**: Current position, destination options, fuel reserves, burn rate, travel time estimates, route hazards, diversion costs
- **Player-facing**: Nav computer interface, fuel gauge, route planner, ETA calculations, diversion cost estimates

### Cargo & Trade
- **Purpose**: Simulates goods being transported, their value, condition, and market dynamics
- **Key State**: Cargo manifest, unit value (fluctuating), spoilage/depreciation rate, demand at destination, trade route profitability, contraband status
- **Player-facing**: Cargo hold inventory, value tracker, market price comparisons, spoilage warnings

### Communications & Broadcasting
- **Purpose**: Simulates open and private communications, broadcasts, propaganda, and information warfare
- **Key State**: Open channel traffic, broadcast content, encryption level, signal range, jamming status, information known to each party
- **Player-facing**: Comm panel with open/private channels, broadcast content, ability to transmit/jam/intercept

### Reputation & Trust
- **Purpose**: Tracks how factions and individuals perceive the player and each other
- **Key State**: Reputation per faction, trust per individual, history of actions, promises kept/broken, public perception
- **Player-facing**: Reputation summary, NPC/faction dialogue shifts, access to opportunities, consequences of past choices

### Security & Threat
- **Purpose**: Simulates armed forces, threat assessment, rules of engagement, and escalation dynamics
- **Key State**: Security force disposition, loyalty/sympathy splits, rules of engagement, escalation level, weapons armed status, patrol patterns
- **Player-facing**: Threat warnings, security hails, weapon lock alerts, escalation status indicators

## System Dependencies

### Hard Dependencies
- `Fleet & Ship Movement` --depends on--> `Navigation & Fuel`: ship movements consume fuel and follow navigational constraints
- `Diplomacy & Negotiation` --depends on--> `Faction System`: negotiations occur between factions with defined interests and structures
- `Station Administration` --depends on--> `Economy & Currency`: station governance is constrained by budget and economic conditions

### Soft Dependencies
- `Faction System` ~~depends on~~> `Economy & Currency`: faction grievances often have economic roots (unpaid wages, broken contracts)
- `Faction System` ~~depends on~~> `Reputation & Trust`: trust between factions affects willingness to negotiate
- `Security & Threat` ~~depends on~~> `Faction System`: security forces may be split in loyalty across factions
- `Security & Threat` ~~depends on~~> `Diplomacy & Negotiation`: escalation level affects security posture
- `Cargo & Trade` ~~depends on~~> `Navigation & Fuel`: trade requires transport, which consumes fuel
- `Cargo & Trade` ~~depends on~~> `Fleet & Ship Movement`: blockades disrupt trade routes
- `Communications & Broadcasting` ~~depends on~~> `Faction System`: factions use comms for coordination and propaganda
- `Diplomacy & Negotiation` ~~depends on~~> `Reputation & Trust`: mediator credibility depends on reputation

### Feedback Loops
- `Faction System` <-> `Diplomacy & Negotiation`: Faction demands drive negotiations; negotiation outcomes reshape faction stance and cohesion
- `Security & Threat` <-> `Diplomacy & Negotiation`: Failed negotiations escalate threat level; high threat level makes negotiation harder but more urgent
- `Economy & Currency` <-> `Faction System` <-> `Station Administration`: Economic failures create faction grievances; faction actions (blockades) worsen economic conditions; station admin responses affect both
- `Cargo & Trade` <-> `Economy & Currency`: Blockade disrupts trade, worsening station economy, increasing pressure to resolve — but also creating smuggling opportunities

## Emergent Possibilities
- A faction of miners splinters — moderates willing to negotiate, hardliners wanting to escalate. The player's actions might determine which faction prevails, reshaping the political landscape of the station permanently
- The player smuggles medical supplies through the blockade to the station's hospital and gains massive reputation with civilians, which pressures the administration to settle — an economic action with political consequences
- While everyone's attention is on the blockade, a pirate crew uses the chaos to raid an unguarded cargo depot on the station's far side — the player might notice, intervene, or join in

## Inspiration
- *The Expanse* — Belter labor disputes, Ceres station politics, Anderson Dawes
- *Babylon 5* — station politics and dock worker strikes
- *Deadwood* (TV series) — frontier power dynamics and deal-making under pressure
- *Battlestar Galactica* — fleet politics, resource scarcity, civilian/military tensions
