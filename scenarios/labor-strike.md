# Scenario: Labor Strike

## Narrative
You've been operations manager at Kovac Station for fourteen months — a mid-belt asteroid mining platform crewed by about six hundred souls, extracting palladium and platinum-group metals from a captured C-type asteroid. It's grueling work, but the money was supposed to be good. That was the promise, anyway. The reality is deferred bonuses, equipment that should have been condemned three quarters ago, and a corporate safety officer who files his reports from a pressurized office on Ganymede and hasn't visited in two years.

This morning, the day shift didn't show up. All four extraction teams, the ore processing crew, the transport haulers — three hundred and twelve workers, standing in the main concourse with their helmets off and their tools on the ground. They've got demands printed on actual paper and taped to every bulkhead between here and the command deck. Better pay. Replacement of the failing boring equipment that's already cost two people their hands. A union representative with binding arbitration authority, not the company-appointed liaison who rubber-stamps everything management sends down. And they want it in writing, countersigned by someone above your pay grade.

Your bosses at Meridian Extraction are seventeen light-minutes away on a comm relay, and their first message was short: restore production within forty-eight hours or they'll send a "resolution team." You know what that means — contract security, mass terminations, and a blacklist that'll follow every worker here to every station in the belt. You also know the workers are right about the equipment. You signed three of those maintenance requests yourself. But your name is on the operations charter, and if production stops long enough to trigger the penalty clause in Meridian's supply contract with the Jovian Cooperative, the financial fallout lands on this station — and on you.

Meanwhile, the air recyclers in Shaft 7 need their scheduled maintenance, which was supposed to happen today by the crew that's now standing in the concourse. Life support has a buffer, but buffers have limits. And your comms officer just flagged an interesting development: two vessels flagged to Tanaka Heavy Industries have been holding station at the edge of your sensor range for three days. Tanaka has been trying to break into this sector for years. A crippled operation with a skilled but disgruntled workforce is exactly the kind of opportunity they wait for.

## Setting
- **Location type**: station (asteroid mining platform)
- **Scale**: local
- **Tone**: political, economic, personal

## Player Agency
- **Support the workers**: Defy corporate, endorse the strike demands, use your position to legitimize their grievances and pressure Meridian to negotiate
- **Break the strike**: Follow corporate orders — threaten terminations, bring in replacement crews, isolate strike leaders
- **Mediate**: Position yourself as a neutral broker between workers and management, try to find a deal both sides can accept before the deadline
- **Stall for time**: Make promises to both sides, keep production partially running with volunteers, buy days while you figure out a real solution
- **Go over management's head**: Contact Meridian's board, the Jovian Cooperative, or belt labor authorities directly — risky but could change the power dynamics
- **Negotiate with Tanaka**: Secretly or openly engage the rival company — could mean better terms for the workers, or selling out the whole station
- **Address life support first**: Prioritize the maintenance crisis, use the safety emergency to force both sides to the table
- **Resign**: Walk away from the impossible position — but what happens to the people who trusted you?

## Resolution Paths
- **Best**: Broker a binding agreement — workers get pay adjustments and equipment replacement, Meridian avoids contract penalties, player earns trust from all sides and cements authority on station
- **Good**: Partial deal — most demands met, some compromises, production resumes with lingering tension but no violence and no corporate crackdown
- **Mixed**: Strike ends but at a cost — either workers forced back under threat, or management replaced by Tanaka buyout; player survives but relationships are damaged
- **Bad**: Deadline passes, corporate sends the resolution team — mass terminations, station destabilized, player's authority stripped or complicit in the crackdown
- **Worst**: Life support failure during the standoff — loss of life turns a labor dispute into a disaster, station placed under emergency external authority, everyone loses

## Required Simulation Systems

### Labor Market
- **Purpose**: Simulates workforce supply, demand, compensation, skill availability, worker satisfaction, and collective labor action
- **Key State**: Worker roster with skills and certifications, wage rates and bonus structures, labor contracts and terms, workforce morale per crew, strike participation rate, scab availability, replacement crew lead times, blacklist registries, union status and organizing progress, labor law jurisdiction, collective bargaining state, skill scarcity index for the region
- **Player-facing**: Workforce status dashboard, strike participation tracker, wage comparison tools, contract term displays, skill shortage warnings, union organizing progress indicators, labor market conditions across nearby stations
- **Political connection**: Labor market conditions feed directly into faction demands and political leverage — a tight labor market empowers workers and their political allies, while surplus labor strengthens corporate factions; labor law jurisdiction determines what tactics each side can legally employ; union recognition is as much a political act as an economic one

### Faction System
- **Purpose**: Simulates organized groups with shared interests, hierarchies, resources, and agendas
- **Key State**: Faction name, leadership, membership roster, resources, grievances, demands, current stance (negotiating/hostile/allied), relationships with other factions, internal cohesion, willingness to use force, splinter risk
- **Player-facing**: Faction reputation display, dialogue reflecting faction stance, access/denial based on faction relations, faction actions visible in the world, internal faction tension indicators

### Law & Jurisdiction
- **Purpose**: Simulates the legal framework governing labor rights, contracts, corporate authority, and dispute resolution in a specific jurisdiction
- **Key State**: Governing legal framework (belt compact, corporate charter, cooperative agreement), labor rights statutes, contract enforcement mechanisms, arbitration availability and binding status, legal precedents, jurisdictional disputes between corporate and civil authority, injunction status, penalty clause terms, whistleblower protections, right to organize status, legal counsel availability
- **Player-facing**: Legal briefing documents, contract clause highlights, jurisdictional authority indicators, legal action options (file grievance, request arbitration, invoke safety statutes), penalty countdown timers, rights advisories for both workers and management
- **Political connection**: Jurisdiction determines which political entity's laws apply — corporate charter law favors Meridian, belt compact law favors workers, and the Jovian Cooperative's trade agreements add a third layer; legal rulings reshape the political landscape by setting precedents that affect every station in the sector

### Economy & Currency
- **Purpose**: Simulates money flows, contract economics, production value, and the financial pressure driving both sides
- **Key State**: Station operating budget, production revenue per shift, contract penalty rates, worker compensation costs, equipment replacement costs, Meridian stock/financial pressure, Tanaka offer terms, supply contract deadlines, insurance and liability costs
- **Player-facing**: Production loss ticker, penalty countdown with financial projections, cost-benefit analysis of settlement terms, budget impact displays, rival offer comparisons

### Diplomacy & Negotiation
- **Purpose**: Simulates multi-party negotiation, demands, concessions, and deal-making
- **Key State**: Parties involved (workers, management, player, Tanaka, Jovian Cooperative), demands per party, red lines, willingness to negotiate, trust between parties, deal terms proposed/accepted/rejected, mediator credibility, leverage assessment, deadline pressure
- **Player-facing**: Negotiation dialogue, demand/offer interface, trust indicators, deal proposal system, leverage comparison, deadline warnings

### Task & Workforce Management
- **Purpose**: Simulates the assignment, execution, and tracking of operational tasks across a workforce, including what happens when that workforce is unavailable
- **Key State**: Task queue (maintenance, extraction, processing, transport), task priority and criticality, required skills per task, assigned personnel, task completion status, overdue task escalation, minimum staffing requirements for critical systems, volunteer and scab crew capabilities, cross-training availability, task failure consequences and cascading effects
- **Player-facing**: Operations board showing task status (on track/delayed/critical/failed), staffing gap warnings, critical system alerts for unmaintained equipment, volunteer assignment interface, cascade failure projections, maintenance backlog tracker
- **Workforce crisis scenarios**: When the workforce walks out, every deferred task becomes visible — the player sees exactly how dependent the station is on the people who do the work, and must triage which unmaintained systems will fail first

### Social Dynamics
- **Purpose**: Simulates interpersonal relationships, group tensions, solidarity, and community cohesion
- **Key State**: Population morale (segmented by group), tension level, grievance accumulation, solidarity index, rumor propagation, trust between population segments, scab stigma level, family and personal relationship pressures
- **Player-facing**: NPC mood and dialogue shifts, crowd behavior at picket lines and concourse gatherings, solidarity actions, rumor mill, visible signs of community fracture or unity

### NPC Identity & Personality
- **Purpose**: Gives non-player characters persistent identities, personalities, skills, motivations, and histories
- **Key State**: Name, background, skills, personality traits, current motivation, trust level, loyalty (to union/company/player), morale, family situation, injury history, desperation threshold, willingness to cross picket line
- **Player-facing**: Dialogue reflecting personality and stake in the dispute, observable behavior changes as pressure mounts, loyalty shifts based on player actions, personal stories that humanize the statistics

### Reputation & Trust
- **Purpose**: Tracks how factions and individuals perceive the player and each other
- **Key State**: Reputation per faction (workers, management, Tanaka, Jovian Cooperative), trust per individual, history of actions, promises kept/broken, public perception, perceived fairness, perceived loyalty
- **Player-facing**: Reputation summary, NPC dialogue shifts, faction willingness to cooperate, consequences of broken promises, trust erosion warnings when player talks to both sides

### Station Administration
- **Purpose**: Simulates station governance, operational authority, and the limits of the player's power as operations manager
- **Key State**: Player authority level and scope, corporate chain of command, emergency powers available, policy options (lockouts, safety declarations, emergency protocols), administrative resources, docking permissions, communication access levels
- **Player-facing**: Authority scope display, available policy actions, chain of command visualization, emergency power activation options, corporate directive notifications

### Equipment & Repair
- **Purpose**: Simulates the condition, maintenance needs, and failure risks of station equipment and infrastructure
- **Key State**: Equipment registry with condition ratings, maintenance schedule and overdue items, failure probability curves, spare parts inventory, repair skill requirements, safety inspection records, condemned equipment list, replacement procurement timelines
- **Player-facing**: Equipment status board with color-coded condition, overdue maintenance alerts, failure risk warnings, spare parts inventory, condemned equipment flags, the maintenance requests the player personally signed

### Atmosphere Management
- **Purpose**: Simulates life support systems including air recycling, pressure management, and the consequences of deferred maintenance
- **Key State**: Air recycler status per section, atmospheric composition readings, pressure differentials, CO2 buildup rate, maintenance schedule for life support, backup system capacity, time-to-critical for unmaintained systems, emergency sealant availability
- **Player-facing**: Atmospheric status displays, section-by-section air quality readings, life support maintenance countdown, emergency alerts, CO2 warnings, the ticking clock that makes the labor dispute a survival issue

### Time Pressure
- **Purpose**: Simulates converging deadlines that force decisions before the player is ready
- **Key State**: Corporate deadline (forty-eight hours to restore production), contract penalty trigger date, life support maintenance window, Tanaka approach timeline, supply contract deadlines, faction patience timers, resolution team ETA if deadline passes
- **Player-facing**: Multiple countdown timers, deadline convergence warnings, cascading consequence projections, daily situation briefings showing how time remaining maps to options remaining

### Communications
- **Purpose**: Simulates internal and external communications, signal delays, information control, and propaganda
- **Key State**: Comm relay access, signal delay to corporate (seventeen minutes), open channel broadcasts, private channel encryption, information known to each party, worker broadcast content, corporate directive content, Tanaka communication intercepts, comm officer loyalty
- **Player-facing**: Comm panel with delayed corporate messages, worker broadcast monitoring, private channel options, signal delay indicator, information asymmetry display, the ability to control or share information as a tool of leverage

## System Dependencies

### Hard Dependencies
- `Diplomacy & Negotiation` --depends on--> `Faction System`: negotiations occur between factions with defined interests and structures
- `Station Administration` --depends on--> `Economy & Currency`: station governance is constrained by budget and contract economics
- `Task & Workforce Management` --depends on--> `Labor Market`: task execution requires available workers with appropriate skills and willingness to work
- `Atmosphere Management` --depends on--> `Task & Workforce Management`: life support maintenance requires assigned and available maintenance crews
- `Social Dynamics` --depends on--> `NPC Identity & Personality`: group dynamics emerge from individual personalities, loyalties, and stakes

### Soft Dependencies
- `Labor Market` ~~depends on~~> `Law & Jurisdiction`: labor rights and contract law determine what tactics are legal for both sides
- `Labor Market` ~~depends on~~> `Faction System`: union organizing and strike action are collective political acts driven by faction cohesion
- `Labor Market` ~~depends on~~> `Economy & Currency`: wage grievances and production economics define the material stakes of the dispute
- `Faction System` ~~depends on~~> `Reputation & Trust`: trust between factions affects willingness to negotiate or escalate
- `Faction System` ~~depends on~~> `Social Dynamics`: solidarity and scab stigma shape faction cohesion and membership
- `Law & Jurisdiction` ~~depends on~~> `Communications`: legal filings, arbitration requests, and jurisdictional claims require comm relay access
- `Law & Jurisdiction` ~~depends on~~> `Station Administration`: administrative authority determines which legal frameworks are invoked
- `Equipment & Repair` ~~depends on~~> `Task & Workforce Management`: repairs require skilled workers who may be on strike
- `Diplomacy & Negotiation` ~~depends on~~> `Reputation & Trust`: mediator credibility depends on perceived fairness and history
- `Diplomacy & Negotiation` ~~depends on~~> `Time Pressure`: deadline convergence forces concessions neither side would otherwise make
- `Communications` ~~depends on~~> `Station Administration`: comm access and information control are administrative tools
- `Time Pressure` ~~depends on~~> `Atmosphere Management`: life support degradation sets the hardest deadline of all

### Feedback Loops
- `Labor Market` <-> `Faction System` <-> `Law & Jurisdiction`: Labor conditions drive faction formation and demands; factions push for legal recognition and rights; legal rulings reshape what labor actions are permissible, which changes the market dynamics for every station under that jurisdiction
- `Task & Workforce Management` <-> `Atmosphere Management` <-> `Time Pressure`: Striking workers mean unmaintained life support; degrading atmosphere creates urgency that pressures both sides; emergency maintenance requires workers to return, giving them leverage but also moral obligation
- `Diplomacy & Negotiation` <-> `Faction System` <-> `Economy & Currency`: Economic pressure drives faction demands; negotiation outcomes reshape economic terms; new economic reality changes faction satisfaction and cohesion
- `Reputation & Trust` <-> `Diplomacy & Negotiation` <-> `Communications`: Player's communications shape trust; trust determines negotiation access and credibility; negotiation outcomes are broadcast and reshape reputation with all parties
- `Labor Market` <-> `Economy & Currency` <-> `Station Administration`: Production halts trigger contract penalties; financial pressure forces administrative decisions; those decisions (lockouts, concessions, Tanaka deals) reshape the labor market for the entire station

## Emergent Possibilities
- The player discovers that the two workers who lost their hands filed safety complaints months ago that were buried by the corporate liaison — leaking this to belt media or the Jovian Cooperative transforms a local labor dispute into a sector-wide scandal, giving workers enormous leverage but making Meridian desperate and dangerous
- A veteran crew chief who initially led the strike starts losing support to a younger radical who wants to sabotage equipment to force the issue — the player can bolster the moderate leader's position through early concessions, or let the radicals take over and deal with the consequences
- Tanaka's offer to the workers is genuinely better — higher pay, newer equipment, real union recognition — but accepting it means Meridian retaliates by blacklisting the station from their supply network, creating a different crisis; the player might broker a deal where Tanaka buys out Meridian's contract, but Meridian's board won't sell without extracting a price

## Inspiration
- *The Expanse* — Belter labor exploitation, corporate indifference to worker safety, Anderson Dawes organizing on Ceres
- *Norma Rae* (1979) — the personal cost of labor organizing and the moment when someone in the middle picks a side
- *Germinal* (Emile Zola) — mine workers striking against impossible conditions, the tension between moderate and radical action
- *Alien* (1979) — Weyland-Yutani corporate indifference, expendable workers, the company always has another agenda
- *Severance* (TV series) — corporate control over workers' lives, the dehumanization of labor, institutional resistance to accountability
