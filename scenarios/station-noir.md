# Scenario: Station Noir

## Narrative
You've been stuck on Tartarus Ring for six days — docked for repairs that keep getting delayed because the parts depot is "under audit." You've been killing time in the lower-ring bars, staying out of trouble, when trouble finds you instead. A dockhand named Soren Cade turns up dead in a maintenance crawlspace behind Recycling Bay 7. Throat cut. Station security sweeps the scene, asks a few questions, and closes the case in under four hours. Suicide, they call it. Nobody who saw the body believes that.

Cade's sister corners you in a noodle bar the next morning. She knows you talked to Soren two nights ago — he'd been asking around about irregularities in cargo manifests, containers marked for recycling that never made it to the smelters. She wants you to find out what happened. You don't owe her anything. But you owe Soren a drink you never bought him, and the way station security shut this down so fast has a smell to it — the kind of smell that means someone with a badge or a budget wanted it shut down. Your ship isn't going anywhere until those parts clear audit. You've got nothing but time and a bad feeling.

The deeper you dig, the worse it gets. Cade's cargo discrepancies lead to a warehousing operation that doesn't exist on any official registry. People who talked to Soren before he died are suddenly transferring off-station or going quiet. The station administrator's office is stonewalling requests. Security Chief Valdez seems more interested in where you're poking around than in who killed a dockhand. And somewhere in the upper ring, someone is making a lot of money moving things that aren't supposed to be moved — and they've already demonstrated what happens to people who notice.

## Setting
- **Location type**: station (interior)
- **Scale**: local
- **Tone**: noir, investigative

## Player Agency
- Investigate Cade's death — follow the cargo manifests, interview witnesses, search his quarters
- Decide who to trust: the victim's sister, a sympathetic security officer, a journalist, a bar owner who knows everyone
- Confront or avoid Station Security — they may be compromised, but they still have authority
- Pursue evidence through official channels (station records, filing jurisdiction complaints) or unofficial ones (break-ins, bribes, hacking terminals)
- Choose how deep to go — surface answers are safe, the real conspiracy is dangerous
- Leverage or withhold information — trade what you know for favors, access, or protection
- Decide whether to seek outside legal authority (corporate oversight, transit court, guild arbitration) or handle it locally
- Take sides when the guilty parties try to buy you off or threaten you

## Resolution Paths
- **Best**: Uncover the smuggling operation, identify Cade's killer, and get the evidence to a jurisdiction that will act on it — station administration is exposed, arrests are made, reforms begin
- **Good**: Gather enough evidence to force a settlement — the killer is quietly removed, the operation shuts down, but the people who ordered it stay in power
- **Mixed**: Get the truth but can't prove it — you know who did it, they know you know, and you negotiate your way off the station alive with leverage but no justice
- **Bad**: Get too close without enough protection — framed for the murder, evidence destroyed, forced to flee the station under suspicion
- **Worst**: Disappear like Cade did — the station adds another unsolved case to the file and nobody asks questions

## Required Simulation Systems

### NPC Identity & Personality
- **Purpose**: Gives every character a persistent inner life — loyalties, fears, secrets, breaking points — that determines whether they help you, lie to you, or sell you out
- **Key State**: Name, background, occupation, personality traits, secrets held, fear level, loyalty allegiances, trust toward player, trust toward other NPCs, willingness to talk, breaking point threshold, alibi consistency
- **Player-facing**: Dialogue that shifts based on trust and fear, observable nervousness or evasion, NPCs contradicting each other's stories, witnesses who clam up or open up based on approach, informants who feed bad information if threatened too hard

### Station Administration
- **Purpose**: Simulates station governance as a political body with its own interests, corruption, and capacity to obstruct or assist
- **Key State**: Administrator identity, deputy officials, budget/treasury, policy priorities, corruption level, complicity in criminal activity, public approval, relationship with security forces, responsiveness to external oversight, cover-up active (boolean), pressure threshold
- **Player-facing**: Bureaucratic delays, access denials, official statements that contradict evidence, admin officials who avoid the player, policy changes in response to player pressure, internal memos if accessed

### Law & Jurisdiction
- **Purpose**: Simulates the legal frameworks, jurisdictional boundaries, and enforcement mechanisms that govern stations, ships, and territories — and the gaps between them
- **Key State**: Governing legal authority (corporate charter, transit compact, sovereign claim), applicable laws, jurisdictional overlaps and gaps, law enforcement bodies (local security, corporate compliance, transit court, guild arbitration), evidentiary standards per jurisdiction, active warrants, legal proceedings status, statute of limitations, right of detention, extradition agreements, corruption index per body
- **Player-facing**: Ability to file complaints or charges with different authorities, jurisdictional conflicts that block or enable action, legal threats from NPCs, warrants issued for or against the player, awareness that different authorities have different standards of evidence and different motivations, option to forum-shop for a sympathetic jurisdiction

### Reputation & Trust
- **Purpose**: Tracks the web of who trusts whom and why — critical in a scenario where everyone is watching everyone and information is currency
- **Key State**: Reputation per faction/individual, trust per relationship, known associations, information shared with whom, promises made/kept/broken, perceived allegiance, heat level (how much attention the player is drawing)
- **Player-facing**: NPCs who refuse to talk because you were seen with the wrong people, doors that open because someone vouched for you, increasing surveillance as heat rises, faction leaders who offer help contingent on loyalty

### Station Services & Infrastructure
- **Purpose**: Simulates the physical station as a place with areas, access controls, maintenance systems, surveillance, and infrastructure that can be leveraged or exploited
- **Key State**: Station layout (rings, sectors, levels), access permissions per area, surveillance coverage, maintenance schedules, infrastructure condition, service availability (repair, medical, legal, commerce), black market access points, hidden or decommissioned areas, ventilation/crawlspace network
- **Player-facing**: Locked doors and access terminals, surveillance cameras to avoid or disable, maintenance crawlspaces as alternate routes, decommissioned sections where illegal activity hides, infrastructure breakdowns that create opportunities or dangers

### Security & Threat
- **Purpose**: Simulates station security as an active force with patrols, jurisdiction, loyalties, and varying degrees of corruption
- **Key State**: Security chief identity, officer roster, patrol routes and schedules, loyalty split (clean vs. compromised), rules of engagement, alert level, active investigations, surveillance priorities, detention authority, evidence locker contents, willingness to use force, relationship with administration
- **Player-facing**: Security patrols the player must avoid or navigate, officers who help or hinder depending on loyalty, interrogation scenes, detention threats, evidence being tampered with or disappearing, security escalation if the player is too visible

### Communications
- **Purpose**: Simulates information flow — who can talk to whom, what's encrypted, what's intercepted, and how information travels through a closed station environment
- **Key State**: Communication channels (public, private, encrypted), message logs, surveillance intercepts, dead drops, rumor propagation speed, information known per NPC, journalist access, external communication capability (off-station calls)
- **Player-facing**: Intercepted messages as clues, ability to send anonymous tips, encrypted channels that require access codes, rumor mill that spreads player actions, option to contact outside authorities via long-range comms

### Economy & Currency
- **Purpose**: Simulates the money trail — bribes, payoffs, shell companies, and the financial evidence that links the conspiracy together
- **Key State**: Player account balance, local price levels, bribe costs, black market rates, financial records (cargo payments, shell accounts, slush funds), money laundering pathways, asset seizure authority
- **Player-facing**: Bribing contacts for information, following financial records to identify conspirators, cost of black market tools and services, financial pressure from delayed repairs, discovering payment trails that prove motive

## System Dependencies

### Hard Dependencies
- `Law & Jurisdiction` --depends on--> `Station Administration`: legal authority on the station flows from its governance charter and administrative decisions
- `Security & Threat` --depends on--> `Station Administration`: security forces operate under administrative authority and are constrained or corrupted by it
- `Security & Threat` --depends on--> `Law & Jurisdiction`: rules of engagement, detention authority, and evidentiary standards are defined by legal framework
- `Communications` --depends on--> `Station Services & Infrastructure`: communication systems are physical infrastructure with access points and vulnerabilities

### Soft Dependencies
- `NPC Identity & Personality` ~~depends on~~> `Reputation & Trust`: NPC willingness to talk is gated by trust level and perceived risk
- `NPC Identity & Personality` ~~depends on~~> `Security & Threat`: NPC fear level rises with security alert level and visible consequences for talking
- `Station Administration` ~~depends on~~> `Economy & Currency`: administrative corruption is motivated and evidenced by financial flows
- `Law & Jurisdiction` ~~depends on~~> `Communications`: filing complaints, contacting outside authorities, and transmitting evidence require communication channels
- `Law & Jurisdiction` ~~depends on~~> `Reputation & Trust`: credibility with legal bodies depends on player reputation; corrupt jurisdictions are influenced by faction reputation
- `Security & Threat` ~~depends on~~> `Reputation & Trust`: security response escalates based on player heat level and perceived threat
- `Station Services & Infrastructure` ~~depends on~~> `Station Administration`: access permissions and maintenance priorities are set by administration
- `Economy & Currency` ~~depends on~~> `Station Services & Infrastructure`: black market operates within station infrastructure; financial records are stored in administrative systems

### Feedback Loops
- `NPC Identity & Personality` <-> `Reputation & Trust`: Talking to NPCs changes trust relationships; trust levels determine what NPCs reveal; revealed information reshapes the player's reputation with other NPCs
- `Security & Threat` <-> `Station Administration` <-> `Law & Jurisdiction`: Security acts on administrative orders; administration uses legal authority to justify obstruction; player invoking outside jurisdiction pressures administration, which pressures security to either escalate or back down
- `Reputation & Trust` <-> `Security & Threat`: Drawing attention raises heat; raised heat makes NPCs afraid to help; lack of allies forces riskier moves that draw more attention
- `Communications` <-> `Security & Threat` <-> `NPC Identity & Personality`: Intercepted communications reveal NPC secrets; exposed secrets change NPC behavior; NPC behavior changes trigger security responses; security surveillance generates more interceptable communications

## Emergent Possibilities
- The player discovers that the sympathetic security officer feeding them leads is actually running a parallel investigation for an outside jurisdiction — and may sacrifice the player's safety to protect a larger case the player knows nothing about
- A witness the player pressured too hard panics and goes to the conspirators, who stage the witness's "accidental" death in a way that implicates the player — forcing the player to solve two murders while being a suspect in one of them
- The station's infrastructure fails in a sector where the player is investigating (power outage, atmosphere leak) — possibly an accident, possibly an attempt on the player's life — and the player must survive while deciding whether to use the chaos to access a restricted area

## Inspiration
- *Chinatown* (film) — uncovering institutional corruption layer by layer, nobody is clean
- *Blade Runner* (film) — noir investigation in a decaying future infrastructure
- *The Expanse* — Belter station politics, Miller's investigation on Ceres
- *Babylon 5* — station-bound mysteries, jurisdictional conflicts between Earth and station law
- *Disco Elysium* (game) — investigation driven by personality, dialogue, and moral compromise
