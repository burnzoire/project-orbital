# Scenario: Spaceport Crew Hiring

## Narrative
You're standing in the lower concourse of Callisto Freight Terminal, a greasy, overcrowded waystation where half the docking clamps are rusted and the other half are occupied by ships that haven't moved in months. Your ship — salvaged, barely legal, held together with aftermarket patches and optimism — is berthed at Dock 14. She flies. Mostly. But she doesn't fly herself.

You need crew. A pilot who can handle her sluggish thrust-to-mass. An engineer who won't panic when the reactor hiccups. Maybe a medic, if you can afford one. You can't afford much of anything, actually. Your accounts are nearly zeroed and the berthing fees are ticking. But desperation cuts both ways — there are people on this station who need off it as badly as you need them on your ship. Burned-out miners, ex-military with the wrong discharge papers, drifters one missed meal from trouble.

The trick isn't finding warm bodies. It's finding people who won't steal your ship, break your ship, or kill each other before you make your first haul. And you need to do it before the berthing fees eat your last credits and the port authority impounds your vessel.

## Setting
- **Location type**: port
- **Scale**: local
- **Tone**: social, economic

## Player Agency
- Choose which crew roles to prioritize (can't afford all positions)
- Evaluate candidates: skills vs. personality vs. desperation vs. trustworthiness
- Negotiate compensation — wages, shares, bunk quality, promises of future payoff
- Decide whether to take on crew with red flags (criminal history, addiction, instability) for lower cost
- Invest time in vetting vs. rushing to beat berthing fee deadline
- Choose recruitment methods — post listings, visit bars, ask around, check labor boards

## Resolution Paths
- **Best**: Assemble a competent, compatible crew within budget and depart with time to spare
- **Good**: Crew has gaps but is functional — you'll manage with what you have
- **Mixed**: Crew is capable but volatile — interpersonal tensions will be a problem
- **Bad**: Took on someone untrustworthy out of desperation — theft, mutiny, or sabotage risk
- **Worst**: Ran out of money before finding enough crew — ship impounded, back to square one

## Required Simulation Systems

### NPC Identity & Personality
- **Purpose**: Gives non-player characters persistent identities, personalities, skills, motivations, and histories
- **Key State**: Name, background, skills (rated), personality traits, current motivation, trust level, loyalty, morale, reputation, relationships with other NPCs
- **Player-facing**: Dialogue that reflects personality, observable behavior patterns, crew interactions, performance variation based on morale/skill

### Economy & Currency
- **Purpose**: Simulates money, pricing, wages, costs, and economic pressure
- **Key State**: Player account balance, local price levels, wage expectations by role, berthing/docking fees (time-based), cost of goods and services, inflation/deflation
- **Player-facing**: Account balance display, price tags, wage negotiation, fee timers, economic pressure from costs ticking up

### Labor Market
- **Purpose**: Simulates the availability, quality, and cost of hireable personnel at a given location
- **Key State**: Available candidates (generated from local population), skill distribution, wage expectations, desperation index, local unemployment, role demand
- **Player-facing**: Job board listings, bar conversations, NPC availability changing over time, competition from other captains hiring

### Reputation & Trust
- **Purpose**: Tracks how entities (player, NPCs, factions, organizations) perceive and trust each other
- **Key State**: Reputation score per faction/entity, trust level (per relationship), history of interactions, promises made/kept/broken
- **Player-facing**: NPC willingness to deal, dialogue tone shifts, access to opportunities, consequences of broken promises

### Ship Crewing
- **Purpose**: Simulates crew positions, role requirements, and the effects of staffing on ship capability
- **Key State**: Required crew positions, minimum skill thresholds per role, current crew manifest, crew compatibility, morale aggregate, efficiency modifier
- **Player-facing**: Crew roster interface, role vacancy warnings, ship capability ratings based on crew quality, interpersonal event notifications

### Social Dynamics
- **Purpose**: Simulates interpersonal relationships, tensions, and group dynamics among NPCs and the player
- **Key State**: Relationship scores (per NPC pair), tension level, shared history, personality compatibility, grievances, alliances
- **Player-facing**: Crew arguments, alliances forming, morale impacts, NPCs refusing to work together, loyalty events

### Station Services & Infrastructure
- **Purpose**: Simulates the facilities, services, and conditions available at a port or station
- **Key State**: Available services (repair, refuel, medical, markets, bars, labor offices), quality/cost, congestion, operating hours, black market availability
- **Player-facing**: Station directory, service availability, quality variation, queue times, sketchy back-alley options

### Time Pressure
- **Purpose**: Simulates deadlines, ticking costs, and the passage of time as a resource
- **Key State**: Current date/time, active deadlines (berthing fees, contract windows, NPC availability windows), cost accumulation rate
- **Player-facing**: Clock/calendar display, fee accumulation warnings, "time remaining" indicators, NPCs leaving if not hired promptly

## System Dependencies

### Hard Dependencies
- `Labor Market` --depends on--> `NPC Identity & Personality`: candidates must be generated with skills, personalities, and backgrounds
- `Ship Crewing` --depends on--> `NPC Identity & Personality`: crew members are NPCs with persistent state
- `Social Dynamics` --depends on--> `NPC Identity & Personality`: relationships require personality data to simulate

### Soft Dependencies
- `Labor Market` ~~depends on~~> `Economy & Currency`: local economic conditions affect candidate availability and wage expectations
- `Labor Market` ~~depends on~~> `Reputation & Trust`: player's reputation affects willingness of quality candidates to sign on
- `Ship Crewing` ~~depends on~~> `Social Dynamics`: crew compatibility affects ship efficiency and event generation
- `NPC Identity & Personality` ~~depends on~~> `Station Services & Infrastructure`: NPC behavior and availability influenced by local conditions
- `Time Pressure` ~~depends on~~> `Economy & Currency`: costs tick up over time, creating economic urgency

### Feedback Loops
- `Reputation & Trust` <-> `Labor Market`: Good reputation attracts better candidates; hiring and treating crew well builds reputation; bad hires damage reputation
- `Economy & Currency` <-> `Time Pressure`: Costs accumulate over time; time pressure forces economic compromises; running out of money creates time pressure (impound deadline)
- `Social Dynamics` <-> `Ship Crewing`: Crew compatibility affects ship performance; ship performance (success/failure of missions) affects crew morale and dynamics

## Emergent Possibilities
- A highly skilled engineer is available cheap because she's on the run from a faction the player hasn't encountered yet — hiring her is great for the ship but paints a target on it later
- Two candidates the player hires independently turn out to have a shared history — old grudge, old romance, or old debt — that the player only discovers once underway
- The player can't afford a medic, so they hire a veterinarian from an agricultural colony who turns out to be surprisingly competent in trauma situations but terrible with pharmaceuticals

## Inspiration
- *Firefly* (TV series) — assembling a misfit crew, living on the edge financially
- *Cowboy Bebop* (anime) — desperate people finding each other on the margins
- *Elite Dangerous* (game) — station economies and crew hiring
- *The Expanse* — Belter labor politics, desperation economics
