# Scenario: Smuggling Run

## Narrative
The job came through three cutouts and paid four times the going rate for a standard Ceres-to-Vesta haul. That alone should have been enough to walk away. Instead, you watched a crew of people you'd never met load eight sealed containers into a compartment behind your aft water tank that you didn't know your ship had — because whoever owned her before you had it installed off-book. The containers are shielded, thermally masked, and bolted to shock mounts rated for combat maneuvers. You were told the cargo was "humanitarian medical supplies for a settlement that can't get them through legitimate channels." You were told not to scan the containers. You were told the manifest was already prepared and loaded into your ship's trade computer — clean, auditable, and completely fictional.

Now you're twelve hours out from the Hygiea Corridor checkpoint, and the situation is deteriorating. Traffic control has flagged all inbound ships for enhanced screening — something about an intelligence bulletin, increased threat posture, the usual euphemisms that mean someone tipped someone off. Your scanner shows two customs cutters running parallel patrol patterns and a dedicated inspection frigate parked at the checkpoint itself. They're cycling ships through one at a time. Average processing: forty minutes. Ships that get flagged for secondary inspection are being towed to a holding dock and taken apart for hours. Three ships ahead of you in the queue. Your falsified manifest will pass a cursory database check. It will not survive a physical cargo audit.

Your ship is running a suppressed drive signature — the previous owner's modifications extend well beyond the hidden compartment. You can reduce your thermal profile, mask your reactor output, and spoof a smaller mass reading on their gravimetric sensors. But going dark means going slow, and a ship that suddenly drops off the approach lane and drifts will attract exactly the kind of attention you're trying to avoid. You have contacts at this checkpoint — a customs official who takes bribes and a dockworker who can create distractions. You have a legitimate cargo in your main hold that gives you a reason to be here. And you have a growing suspicion that whatever is in those containers is worth a lot more than your life to the people who hired you.

## Setting
- **Location type**: deep space (customs checkpoint approach)
- **Scale**: tactical
- **Tone**: tension, deception, survival

## Player Agency
- **Bluff through**: Approach normally, present the falsified manifest, rely on your cover cargo and forged paperwork to survive a standard inspection
- **Bribe the inspector**: Contact your customs official, arrange a payoff, and hope their greed outweighs their fear of the heightened security posture
- **Run dark**: Kill your drive, suppress your signature, and drift off the approach lane — try to bypass the checkpoint entirely through the debris field
- **Jettison and recover**: Eject the hidden cargo at a marked location before the checkpoint, pass clean, then loop back to recover it later
- **Create a diversion**: Have your dockworker contact stage an incident at the checkpoint — a cargo spill, a reactor alarm, a brawl — to overwhelm the inspection team while you slip through
- **Surrender the cargo**: Come clean to customs, hand over the containers, and try to trade cooperation for leniency — betraying your employers in the process
- **Scan the cargo**: Finally open those containers and find out what you're actually carrying — the answer might change every calculation you've made
- **Abort the run**: Reverse course, return the cargo to the dead drop, and walk away from the job — if your employers will let you

## Resolution Paths
- **Best**: Slip through the checkpoint undetected with cargo intact — deliver on time, collect the extraordinary payout, and leave no trace connecting you to the shipment
- **Good**: Get through with some close calls — a suspicious inspector, a tense scan, a bribe that barely holds — but you're through and paid, carrying new heat on your reputation
- **Mixed**: Forced to jettison or partially sacrifice the cargo to avoid arrest — you survive and stay free, but the payout is reduced and your employers are unhappy
- **Bad**: Detained at the checkpoint, cargo discovered, ship impounded — facing criminal charges in a jurisdiction that doesn't favor smugglers, your employers denying any knowledge of you
- **Worst**: Your employers decide you're a liability before you reach the checkpoint — the cargo was rigged, the job was a setup, or a cleanup crew is already burning toward your position

## Required Simulation Systems

### Stealth & Detection
- **Purpose**: Simulates signature management, thermal masking, drive suppression, hidden compartments, scanner evasion techniques, and the cat-and-mouse dynamics between concealment and detection
- **Key State**: Thermal signature level, drive emission profile (active/suppressed/cold), gravimetric mass reading (actual vs. spoofed), radar cross-section, hidden compartment shielding integrity, scanner evasion mode (passive drift, active spoofing, compartment masking), detection probability per scan type (visual, thermal, gravimetric, active radar), time since last signature spike, hull coating degradation, electromagnetic leakage from shielded cargo
- **Player-facing**: Signature profile display showing current emissions across thermal, EM, and gravimetric bands, detection risk meter that fluctuates with system activity, compartment shielding status, drive suppression toggle with tradeoff indicators (speed vs. stealth), alert when scanned with probability of detection outcome, spoofing system controls with power draw and believability rating

### Cargo & Trade
- **Purpose**: Simulates cargo manifests, container tracking, trade documentation, customs declarations, and the gap between what paperwork says and what the hold actually contains
- **Key State**: Manifest entries (declared vs. actual), container inventory with contents and legal status, cargo mass and volume, trade permits and licenses, customs declaration status, manifest forgery quality, container seal integrity, contraband classification tier, cargo value (legal and black market), shipping route documentation, chain-of-custody records
- **Player-facing**: Trade computer interface showing declared manifest alongside actual cargo, forgery confidence rating per line item, contraband alert indicators, cargo hold schematic showing standard and hidden compartments, customs paperwork status, buyer/seller documentation trail

### Law & Jurisdiction
- **Purpose**: Simulates the legal frameworks governing customs enforcement, contraband classification, search-and-seizure authority, and the consequences of getting caught — including how different jurisdictions treat the same cargo differently
- **Key State**: Governing legal authority at checkpoint, contraband schedule (what's illegal and at what tier), search warrant requirements, probable cause threshold, inspection authority scope, penalty structure (fines, impound, imprisonment), jurisdictional boundaries, extradition treaties, legal representation availability, cooperation incentive programs, prosecution likelihood based on evidence quality, diplomatic immunity exceptions
- **Player-facing**: Legal status indicator showing current jurisdictional exposure, contraband classification lookup, penalty preview if caught, option to invoke jurisdictional technicalities, cooperation-for-leniency negotiation interface, awareness of which jurisdiction you'd prefer to be caught in versus which you're actually in

### Sensors & Scanning
- **Purpose**: Simulates both sides of the detection equation — the checkpoint's scanning capabilities trying to find your cargo, and your own sensors tracking patrol ship positions and scan patterns
- **Key State**: Checkpoint scanner types (thermal, gravimetric, active radar, cargo-penetrating), scan cycle timing, scan resolution and range, patrol ship sensor loadouts, player sensor mode (active/passive), contact tracking for customs vessels, scan warning detection, electronic countermeasure status, sensor cross-section of player ship
- **Player-facing**: Sensor board showing customs vessel positions and patrol patterns, scan warning indicators when targeted, scan type identification (knowing what they're looking for), ECM toggle with effectiveness estimate, passive listening mode for intercepting customs communications

### Security & Threat
- **Purpose**: Simulates the checkpoint's security posture, escalation protocols, and the threat assessment that customs officers are running on every approaching ship — including yours
- **Key State**: Checkpoint alert level, inspection intensity (routine/enhanced/lockdown), officer suspicion per ship, escalation triggers (manifest discrepancy, scan anomaly, behavioral flag), armed response threshold, boarding team readiness, pursuit ship availability, detention facility capacity, threat intelligence bulletin active, player flag status (clean/flagged/wanted)
- **Player-facing**: Checkpoint alert level display, suspicion meter reflecting how customs perceives your ship, escalation warning indicators, patrol ship behavior changes (tightening formation, active scanning), boarding team deployment alerts, detection of whether you've been specifically flagged

### Communications
- **Purpose**: Simulates the communication channels between you, the checkpoint, your contacts, and your employers — including what's encrypted, what's monitored, and what happens when you say the wrong thing on the wrong channel
- **Key State**: Channel status (open hail, encrypted, monitored), customs communication protocols, contact availability (bribed official, dockworker), employer communication channel, message intercept risk, comm discipline (radio silence vs. active), traffic control instructions, automated transponder responses, communication logs as evidence
- **Player-facing**: Comm panel with channel selection and encryption indicators, customs hail interface with scripted responses, secure channel to contacts with risk assessment, employer message queue, monitoring warning when transmitting on unsecured channels, ability to go radio silent with consequences

### Economy & Currency
- **Purpose**: Simulates the financial dimension — the extraordinary payout motivating the risk, bribe costs, legal defense funds, and the economic pressure that makes people take jobs like this in the first place
- **Key State**: Job payout (promised vs. likely), bribe cost per contact, legal defense retainer costs, impound fees, fine amounts, player account balance, black market cargo value, cost of fuel and supplies for alternate routes, economic pressure (debts, ship payments, crew wages), insurance status, asset seizure risk
- **Player-facing**: Financial overview showing payout vs. risk costs, bribe negotiation interface, running tally of expenses against expected profit, debt pressure indicators, asset seizure warnings if detained, cost comparison for different resolution approaches

### Navigation & Fuel
- **Purpose**: Simulates route planning through and around the checkpoint — approach lanes, debris fields, alternate trajectories, and the fuel cost of every option from straight compliance to full evasion
- **Key State**: Approach lane assignment, checkpoint queue position, alternate route options (debris field, long-arc bypass, retrograde), fuel reserves, burn rate per route option, delta-v budget, drift trajectory calculations, time-to-checkpoint, patrol ship intercept windows per route, debris field density and navigation hazard rating
- **Player-facing**: Nav computer with route options overlaid on checkpoint map, fuel cost per route with range estimates, queue position and estimated processing time, debris field navigation overlay, drift trajectory projector for dark-running scenarios, intercept window warnings for patrol ships on alternate routes

### Reputation & Trust
- **Purpose**: Tracks your standing with every party in this transaction — your employers who expect delivery, the contacts who expect payment, the customs officials who may remember your face, and the broader network that determines whether you ever work again
- **Key State**: Employer trust level, contact reliability rating, customs record (clean/flagged/known smuggler), professional reputation in smuggling networks, reputation with legitimate trade guilds, known associates list, betrayal consequences per party, heat level across jurisdictions, informant risk per contact
- **Player-facing**: Reputation dashboard showing standing with employers, contacts, and authorities, heat map across jurisdictions, trust indicators for each contact (will they hold or fold under pressure), consequence preview for betrayal or cooperation, professional reputation trend

### NPC Identity & Personality
- **Purpose**: Gives every person in this scenario a psychology — the customs inspector who's thorough because she's bucking for promotion, the bribed official who's terrified of the new security bulletin, the dockworker who'll help but only up to a point, the employer's fixer who's already calculating whether you're a loose end
- **Key State**: Name, role, personality traits, corruption willingness, fear level, loyalty to institution vs. self-interest, bribe threshold, breaking point, suspicion triggers, professional competence, personal motivations, relationship to other NPCs, knowledge of player's cargo
- **Player-facing**: Behavioral cues during interactions (nervous glances, aggressive questioning, rehearsed indifference), dialogue that shifts based on approach and pressure, observable tells when NPCs are lying or scared, customs inspector personality affecting inspection thoroughness, contact reliability visible through their behavior under stress

## System Dependencies

### Hard Dependencies
- `Stealth & Detection` --depends on--> `Sensors & Scanning`: evasion techniques are defined relative to the detection capabilities they must defeat
- `Stealth & Detection` --depends on--> `Navigation & Fuel`: running dark constrains speed and trajectory; evasion routes consume fuel differently than standard approaches
- `Law & Jurisdiction` --depends on--> `Cargo & Trade`: legal consequences are determined by what the cargo is, how it's documented, and which contraband schedule it falls under
- `Security & Threat` --depends on--> `Sensors & Scanning`: customs threat assessment relies on scan results and sensor data from patrol ships
- `Security & Threat` --depends on--> `Law & Jurisdiction`: inspection authority, search scope, and escalation rules are defined by the governing legal framework

### Soft Dependencies
- `Stealth & Detection` ~~depends on~~> `Economy & Currency`: signature suppression hardware quality scales with investment; better shielding costs more money
- `Cargo & Trade` ~~depends on~~> `Reputation & Trust`: manifest forgery quality depends on the network that produced it; contact reliability affects documentation chain
- `Law & Jurisdiction` ~~depends on~~> `Communications`: invoking jurisdictional rights, contacting legal representation, and filing complaints require communication channels
- `Law & Jurisdiction` ~~depends on~~> `Reputation & Trust`: prior record and reputation influence how customs treats you; clean history buys benefit of the doubt
- `Security & Threat` ~~depends on~~> `Reputation & Trust`: customs suspicion scales with player heat level and known associations
- `Security & Threat` ~~depends on~~> `Communications`: checkpoint coordination, boarding requests, and pursuit orders travel through comm channels
- `Communications` ~~depends on~~> `Stealth & Detection`: transmitting on any channel risks breaking stealth; radio silence is part of signature management
- `NPC Identity & Personality` ~~depends on~~> `Reputation & Trust`: NPC willingness to help or betray is gated by trust, fear, and perceived risk
- `NPC Identity & Personality` ~~depends on~~> `Security & Threat`: contact fear level rises with checkpoint alert status; bribed officials may refuse to act under heightened security
- `Economy & Currency` ~~depends on~~> `Cargo & Trade`: the financial dimension of the scenario is driven by cargo value, both legal and contraband

### Feedback Loops
- `Stealth & Detection` <-> `Sensors & Scanning` <-> `Security & Threat`: Suppressing your signature reduces detection probability; lower detection means less customs scrutiny; but active scanning adapts to evasion — if they suspect spoofing, they switch to scan types your countermeasures don't cover, forcing you to adapt or be found
- `Cargo & Trade` <-> `Law & Jurisdiction` <-> `Security & Threat`: What you're carrying determines your legal exposure; legal exposure determines what customs is looking for; what customs finds determines whether your documentation holds; documentation failure escalates the legal situation further
- `Communications` <-> `Stealth & Detection` <-> `NPC Identity & Personality`: Contacting your bribed official requires breaking radio silence, which risks detection; detection raises checkpoint alert, which makes your contact more afraid to act; a frightened contact may refuse or betray you, forcing you deeper into stealth
- `Reputation & Trust` <-> `NPC Identity & Personality` <-> `Economy & Currency`: Your reputation determines contact reliability; reliable contacts cost more but deliver; unreliable contacts are cheap but may fold under pressure; a contact who folds exposes you, destroying reputation and making future runs harder and more expensive

## Emergent Possibilities
- The player scans the cargo and discovers it's not weapons or medicine but a cryo-preserved human being — someone important enough to smuggle, someone whose identity changes the moral calculus of every option on the table, and someone whose employers will kill to keep secret
- The bribed customs official accepts the payoff but then tips off the inspection frigate anyway, playing both sides — the player realizes mid-approach that they've been sold out and must improvise with a closing patrol and a contact who's already spent the bribe money
- The player goes dark and drifts into the debris field to bypass the checkpoint, but their suppressed drive signature matches the profile of a ship involved in a piracy incident last month — now the patrol ships aren't looking for a smuggler, they're hunting a pirate, and the rules of engagement just changed from "inspect" to "weapons free"

## Inspiration
- *Firefly / Serenity* — smuggling as a way of life, hidden compartments, the tension of customs inspections, "what's in the box" moral ambiguity
- *The Expanse* — Belter smuggling operations, checkpoint politics, jurisdictional gaps between inner and outer system law
- *Star Wars: Solo* — the Kessel Run as a smuggling gauntlet, improvised evasion, cargo that isn't what it seems
- *Elite Dangerous* — interdiction mechanics, cargo scanning, silent running, heat management as stealth
- *Deus Ex: Human Revolution* — social manipulation at checkpoints, multiple approaches to the same obstacle, consequence cascades
