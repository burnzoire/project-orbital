# Scenario: Black Market Bazaar

## Narrative
You found The Hollows through a contact who owed you a favor — a set of docking coordinates pointing to a decommissioned asteroid mining complex in the trailing Trojans, officially listed as "structurally condemned" in every survey database. The transponder codes got you past the automated perimeter drones. The docking bay swallowed your ship into a cavern carved out of raw nickel-iron, where a kid with a hand terminal scanned your hull, charged you a docking fee in physical chits, and told you the rules: no weapons fire inside the market walls, all disputes settled by the arbiters, and if station security raids, you're on your own.

Inside, The Hollows is a maze of repurposed mining tunnels and blown-out ore processing chambers converted into a sprawling bazaar. Cargo containers stacked three high form shop walls. Bioluminescent fungi someone cultivated in the old ventilation shafts provide a sickly green ambient light where the rigged LED strips have burned out. The air smells like lubricant, cooked protein, and ozone from overloaded power taps. Hundreds of people move through the corridors — traders, buyers, fixers, thieves, refugees, and the desperate. Everything is for sale. Everything.

You came for a specific reason: a CX-40 plasma relay coupling, a military-spec component your ship needs and that no licensed dealer will sell to a civilian. You've been told a parts dealer called Mako has one. But The Hollows doesn't let you walk in, buy one thing, and walk out clean. A fence named Dusana is offering stolen Martian Navy hardware at a tenth of market price — railgun targeting modules, countermeasure pods, things that would make your ship genuinely dangerous. An information broker called The Ledger claims to have a file on you, something from before, something you thought was buried. In a side tunnel near the food stalls, a family of four — parents and two children — is sitting behind a hand-lettered sign offering indentured labor contracts to anyone who will cover their debt to a local syndicate boss. And the chatter in the bazaar says that Transit Authority enforcement has been scouting the perimeter. A raid could come in hours or days. Nobody knows. Everybody is nervous.

You need the part. You want to get out. But now you're here, and every stall you pass, every conversation you overhear, every pair of eyes that lingers on you too long is another decision about who you are and what you're willing to do.

## Setting
- **Location type**: station (interior, illegal)
- **Scale**: local
- **Tone**: economic, moral, tense

## Player Agency
- Find and negotiate for the CX-40 plasma relay coupling — price, payment method, and strings attached
- Decide whether to buy stolen military hardware from Dusana — massive upgrade potential, massive legal and moral risk
- Engage with The Ledger's offer — pay to see your own file, trade information, or walk away from whatever past is in there
- Respond to the indentured family — ignore them, buy their contracts (and then what?), try to help them another way, or report the debt holder
- Manage your visible inventory — what you carry openly signals wealth, threat level, and intent to everyone watching
- Choose what to sell — offload cargo, personal items, or information to fund purchases
- Navigate the social fabric — who you talk to, who sees you, who you're associated with changes your options
- React to the incoming raid — leave early with less, stay and risk getting caught, warn others, use the chaos
- Deal with the arbiters — The Hollows has its own justice system, and crossing it has consequences

## Resolution Paths
- **Best**: Acquire the relay coupling at a fair price, navigate the bazaar without entangling yourself in anything dangerous, and depart before any raid — maybe even help the family without painting a target on yourself
- **Good**: Get the part and get out, but with compromises — you paid too much, owed someone a favor, or bought something you shouldn't have
- **Mixed**: Acquired what you needed but drew attention — the military hardware is in your hold and someone knows it, The Ledger's information has destabilized your sense of your own past, or the family's debt holder now considers you an enemy
- **Bad**: The raid hits while you're still inside — loss of purchased goods, detention, ship impoundment, or forced to flee and leave inventory behind
- **Worst**: Betrayed by a contact, robbed in the tunnels, or caught by Transit Authority with stolen military hardware in your hold — criminal charges, ship seizure, and a reputation that closes doors across the system

## Required Simulation Systems

### Economy & Currency
- **Purpose**: Simulates the shadow economy of The Hollows — barter, chits, favors, and the fluid pricing of illegal goods where trust and desperation set the rates
- **Key State**: Player account balance (formal credits), physical chit balance, local black market price index, supply/demand per commodity, barter exchange rates, vendor price memory (what you paid before affects future offers), syndicate debt ledgers, favor economy (owed and owing), markup volatility based on raid threat level
- **Player-facing**: Prices that shift as raid rumors intensify, vendors who accept different payment types, haggling that depends on what you're carrying and who vouches for you, economic pressure from limited funds against multiple temptations

### Cargo & Trade
- **Purpose**: Simulates the movement, storage, ownership, and legality of physical goods — what's being bought, sold, moved, and hidden throughout the bazaar
- **Key State**: Player cargo manifest, ship hold capacity and contents, item legality classification (legal, restricted, contraband, military), item provenance (clean, stolen, forged documentation), cargo transfer logs, vendor inventory, black market supply chains, item condition and authenticity
- **Player-facing**: Cargo management interface, decisions about what to buy and where to store it, risk assessment of carrying contraband through a potential raid, authentication checks on goods (is this really military-spec or a knockoff?), smuggling compartment options

### Law & Jurisdiction
- **Purpose**: Simulates the overlapping legal realities — The Hollows has no legal standing, but Transit Authority jurisdiction extends to the asteroid belt, and possession of stolen military hardware is a crime everywhere
- **Key State**: Applicable legal authorities (Transit Authority, Martian Navy, corporate security), contraband classifications, warrant status, detention authority, evidence standards, jurisdictional reach to this location, raid authorization status, legal consequences per item type, statute of limitations on past crimes
- **Player-facing**: Awareness that different items carry different legal risks, the looming threat of a raid that would bring jurisdiction crashing down, ability to assess legal exposure before purchasing, the tension between the lawless space of the bazaar and the law that exists just outside it

### Reputation & Trust
- **Purpose**: Tracks the web of perception in a place where everyone is watching and trust is the only currency that matters more than credits
- **Key State**: Reputation per faction (bazaar traders, syndicates, arbiters, Transit Authority), trust per individual relationship, known associations (who you've been seen talking to), transaction history, heat level (how much attention the player is drawing), vouching chain (who introduced you, who will speak for you), betrayal flags
- **Player-facing**: Vendors who won't deal until someone vouches for you, prices that drop as trust builds, stall owners who hide their best merchandise until you've proven yourself, people who avoid you because you talked to the wrong person, the arbiter's willingness to hear your side in a dispute

### NPC Identity & Personality
- **Purpose**: Gives every character in The Hollows a reason to be there, a thing they want, a thing they fear, and a line they will or won't cross
- **Key State**: Name, background, occupation, personality traits, current motivation, desperation level, moral boundaries, secrets held, inventory held, asking price vs. real price, loyalty to The Hollows vs. self-interest, willingness to betray under pressure, relationships with other NPCs, flight-or-fight threshold if raid occurs
- **Player-facing**: A fence who genuinely enjoys the thrill of the deal vs. one who's dead-eyed and calculating, the information broker whose smug confidence cracks when you mention a specific name, the family whose children stare at you while the parents try to maintain dignity, vendors who pack up and vanish when the raid rumors get loud enough

### Security & Threat
- **Purpose**: Simulates both the internal security of The Hollows (the arbiters) and the external threat (Transit Authority raid) as active, evolving forces
- **Key State**: Arbiter roster and patrol zones, arbiter rules of engagement, arbiter corruption level, Transit Authority raid probability (escalating over time), raid force composition, perimeter drone status, early warning system, escape route availability, bazaar alert level, NPC flight behavior thresholds, player threat assessment by both internal and external security
- **Player-facing**: Arbiters who settle disputes with rough justice, the mounting tension of raid probability ticking upward, NPCs who start packing up and heading for docking bays, escape route congestion, the moment when the perimeter drones go silent and everyone knows what's coming

### Station Services & Infrastructure
- **Purpose**: Simulates The Hollows as a physical place — a decommissioned mine repurposed into a bazaar, with all the improvised infrastructure, hidden passages, and failing systems that implies
- **Key State**: Tunnel network layout, active market zones, docking bay capacity and congestion, power grid status (overloaded, prone to blackouts), ventilation system, surveillance (internal cameras run by arbiters), hidden storage caches, escape tunnels, structural integrity warnings, improvised medical facilities, food stalls, repair shops
- **Player-facing**: Navigation through a maze of tunnels and converted chambers, power flickering in deep sections, hidden passages that locals know and outsiders don't, docking bay traffic that signals whether people are arriving or fleeing, the physical experience of a place built from salvage and desperation

### Communications
- **Purpose**: Simulates information flow in a place with no official network — word of mouth, dead drops, encrypted hand-terminal signals, and the rumor mill that is the bazaar's real nervous system
- **Key State**: Communication channels (hand-terminal mesh, dead drops, word of mouth, arbiter announcements), rumor propagation speed, information accuracy degradation, eavesdropping risk per location, external comms capability (jammed or monitored), Transit Authority signal intercepts, encrypted broker channels
- **Player-facing**: Rumors that arrive distorted and must be evaluated, the ability to spread disinformation, eavesdropping on conversations in adjacent stalls, encrypted messages from The Ledger, the sudden silence on external channels that might mean jamming has started

### Social Dynamics
- **Purpose**: Simulates the social ecosystem of the bazaar — alliances, rivalries, hierarchies, and the collective behavior of a population under threat
- **Key State**: Faction relationships (trader collectives, syndicates, independent operators, refugee groups), collective mood, crowd density and flow, group panic threshold, alliance networks, rivalry intensity, collective response to threat (solidarity vs. every-person-for-themselves), social stratification (established traders vs. desperate newcomers)
- **Player-facing**: The bazaar's mood shifting from tense commerce to fearful evacuation, traders who band together and traders who undercut each other, the social cost of helping or ignoring the indentured family, crowd movement that signals danger before you hear the announcement

### Equipment & Repair
- **Purpose**: Simulates the condition, maintenance, and modification of the player's ship and the availability of repair services in an unlicensed facility
- **Key State**: Ship component manifest, component condition ratings, required parts list, available repair services (quality, cost, legality), modification options (legal vs. illegal), installation skill requirements, counterfeit part risk, warranty void status, repair time estimates
- **Player-facing**: The reason you're here — the CX-40 relay coupling and its installation, the temptation to upgrade other systems while you have access to parts no licensed shop would carry, the risk of counterfeit components, improvised repair bays staffed by people of uncertain competence

### Inventory & Personal Equipment
- **Purpose**: Simulates what the player is carrying on their person, wearing, and has immediately accessible — and how that loadout is perceived by everyone around them
- **Key State**: Carried items (weapons, tools, trade goods, credits, chits, documents), worn equipment (suit, armor, visible holsters), concealed items, encumbrance, item visibility to NPCs, item legality per jurisdiction, quick-access slots, storage (pockets, bags, suit compartments), item condition
- **Player-facing**: The choice of what to carry into the bazaar and what to leave on the ship, visible weapons that deter theft but attract attention, concealed valuables that reduce robbery risk but slow access, the moment-to-moment awareness that what you're carrying defines how people treat you — a visible sidearm says one thing, an empty holster says another, and walking in with a crate of trade goods says you're here to deal

## System Dependencies

### Hard Dependencies
- `Cargo & Trade` --depends on--> `Economy & Currency`: all trade requires a functioning price and payment system
- `Security & Threat` --depends on--> `Station Services & Infrastructure`: security forces (arbiters and raiders) operate within and are constrained by physical infrastructure
- `Law & Jurisdiction` --depends on--> `Security & Threat`: legal consequences are enforced by security forces, and the raid is the mechanism by which external law reaches The Hollows
- `Inventory & Personal Equipment` --depends on--> `Cargo & Trade`: personal inventory is a subset of the broader cargo and trade system, items move between ship cargo and personal carry

### Soft Dependencies
- `NPC Identity & Personality` ~~depends on~~> `Reputation & Trust`: NPC willingness to deal is gated by trust, vouching chains, and perceived reputation
- `NPC Identity & Personality` ~~depends on~~> `Security & Threat`: NPC behavior shifts dramatically as raid probability increases — desperation, flight, or opportunism
- `Economy & Currency` ~~depends on~~> `Security & Threat`: prices spike and crash as raid threat fluctuates; vendors liquidate inventory at discount when fleeing
- `Cargo & Trade` ~~depends on~~> `Law & Jurisdiction`: item legality classification determines risk profile and affects price, storage decisions, and player legal exposure
- `Cargo & Trade` ~~depends on~~> `Inventory & Personal Equipment`: what the player carries personally vs. stores on the ship affects trade interactions and risk
- `Reputation & Trust` ~~depends on~~> `Social Dynamics`: collective bazaar dynamics amplify or dampen individual reputation effects
- `Communications` ~~depends on~~> `Station Services & Infrastructure`: the improvised mesh network and dead drop system depends on physical infrastructure
- `Communications` ~~depends on~~> `Social Dynamics`: rumor propagation speed and accuracy depend on collective mood and crowd behavior
- `Equipment & Repair` ~~depends on~~> `Economy & Currency`: repair costs and part prices are subject to the same shadow economy dynamics as everything else
- `Equipment & Repair` ~~depends on~~> `Cargo & Trade`: parts are cargo with provenance, legality, and authenticity concerns
- `Inventory & Personal Equipment` ~~depends on~~> `Reputation & Trust`: visible loadout directly affects how NPCs perceive and interact with the player
- `Social Dynamics` ~~depends on~~> `Security & Threat`: collective behavior is driven primarily by threat level — commerce when calm, panic when threatened

### Feedback Loops
- `Economy & Currency` <-> `Security & Threat`: Rising raid threat drives panic selling and price volatility; price crashes incentivize risk-taking; risk-taking draws security attention that raises threat further
- `Reputation & Trust` <-> `NPC Identity & Personality` <-> `Cargo & Trade`: Who you buy from and what you buy changes how others perceive you; your reputation determines what vendors will show you; access to better goods changes your trade options, which changes who you interact with
- `Inventory & Personal Equipment` <-> `Reputation & Trust` <-> `Security & Threat`: Visible equipment shapes NPC perception; perception determines threat assessment by arbiters; arbiter attention changes what you can safely carry; carrying less changes perception again
- `Communications` <-> `Social Dynamics` <-> `Security & Threat`: Rumors of a raid spread through the bazaar and shift collective mood; collective mood changes how information propagates (panic accelerates rumors, paranoia distorts them); distorted information triggers security responses that generate new rumors

## Emergent Possibilities
- The player buys the relay coupling from Mako only to discover it's counterfeit — forcing a confrontation with Mako, a complaint to the arbiters (who may or may not care), or a desperate search for another source as the raid clock ticks
- The Ledger's file on the player turns out to contain information that another NPC in the bazaar — someone the player has already interacted with — is actively searching for, making the player a target the moment that information changes hands
- The indentured family's debt holder is the same syndicate boss supplying Dusana's stolen military hardware — helping the family means crossing someone whose supply chain the player may also depend on for parts
- The raid hits mid-transaction: the player must choose between grabbing unpaid-for goods in the chaos (theft that will be remembered if The Hollows survives), abandoning purchased items to flee, or using the confusion to settle a score with someone who cheated them
- A vendor the player befriended offers to hide the player's most illegal purchases in a hidden cache accessible only after the raid passes — but trusting a black market vendor with your property and your return is its own gamble

## Inspiration
- *Mos Eisley Cantina* (Star Wars) — a den of scum and villainy where every stranger is a story and a threat
- *The Expanse* — Belter black markets, contraband economics, the tension between survival and law
- *Firefly* — the moral weight of illegal commerce, stolen goods with histories, helping people at cost to yourself
- *Blade Runner* (film) — street-level markets in the cracks of a larger system, noir lighting, moral ambiguity
- *Deus Ex* (game) — navigating a marketplace of information, upgrades, and compromised ethics
