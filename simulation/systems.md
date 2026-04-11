# Simulation Systems Definition
> Last reviewed: 2026-04-11
> Scenarios analyzed: 20

## Systems Overview
| System | Category | Maturity | Scenario Coverage |
|--------|----------|----------|-------------------|
| Atmosphere Management | Physical | Refined | cold-habitat-survival, deep-space-transit, colony-overseer, gravity-well-rescue, labor-strike, refugee-flotilla |
| Attitude Control | Technical | Refined | zero-g-wound, pirate-ambush, gravity-well-rescue |
| Cargo & Trade | Economic | Refined | ice-miner-blockade, smuggling-run, patrol-captain, black-market-bazaar |
| Combat & Weapons | Technical | Developing | pirate-ambush, boarding-action |
| Communications | Technical | Refined | cold-habitat-survival, ice-miner-blockade, pirate-ambush, station-noir, eva-rescue, gravity-well-rescue, port-surveillance, boarding-action, double-dealing, smuggling-run, labor-strike, surface-expedition, refugee-flotilla, patrol-captain, black-market-bazaar |
| Diplomacy & Negotiation | Political | Refined | ice-miner-blockade, colony-food-crisis, double-dealing, labor-strike, refugee-flotilla |
| Economy & Currency | Economic | Refined | spaceport-crew-hiring, ice-miner-blockade, station-noir, colony-food-crisis, double-dealing, smuggling-run, labor-strike, refugee-flotilla, black-market-bazaar |
| Equipment & Repair | Technical | Refined | cold-habitat-survival, deep-space-transit, pirate-ambush, eva-rescue, colony-overseer, gravity-well-rescue, boarding-action, labor-strike, surface-expedition, patrol-captain, black-market-bazaar |
| EVA & Spacewalk | Technical | Refined | eva-rescue, boarding-action, surface-expedition |
| Faction System | Political | Refined | ice-miner-blockade, colony-food-crisis, double-dealing, labor-strike, refugee-flotilla |
| Fleet & Ship Movement | Physical | Refined | ice-miner-blockade, pirate-ambush, refugee-flotilla |
| Fluid Dynamics | Physical | Developing | zero-g-wound, eva-rescue |
| Food & Water Supply | Biological | Refined | deep-space-transit, colony-food-crisis, colony-overseer, refugee-flotilla |
| Habitat Integrity | Physical | Refined | cold-habitat-survival, zero-g-wound, colony-overseer, gravity-well-rescue, boarding-action, refugee-flotilla |
| Inventory & Personal Equipment | Technical | Draft | black-market-bazaar |
| Labor Market | Economic | Developing | spaceport-crew-hiring, labor-strike |
| Law & Jurisdiction | Political | Refined | station-noir, smuggling-run, labor-strike, port-surveillance, patrol-captain, black-market-bazaar |
| Medical & Injury | Biological | Refined | zero-g-wound, pirate-ambush, eva-rescue, boarding-action, surface-expedition, refugee-flotilla, patrol-captain |
| Navigation & Fuel | Technical | Refined | ice-miner-blockade, deep-space-transit, pirate-ambush, eva-rescue, gravity-well-rescue, smuggling-run, surface-expedition, patrol-captain, port-surveillance |
| NPC Identity & Personality | Social | Refined | spaceport-crew-hiring, deep-space-transit, station-noir, colony-food-crisis, colony-overseer, port-surveillance, boarding-action, double-dealing, smuggling-run, labor-strike, surface-expedition, refugee-flotilla, patrol-captain, black-market-bazaar |
| Player Health | Biological | Refined | cold-habitat-survival, zero-g-wound, deep-space-transit, pirate-ambush, eva-rescue, colony-food-crisis, colony-overseer, gravity-well-rescue, boarding-action, surface-expedition, patrol-captain |
| Power Grid | Technical | Refined | cold-habitat-survival, zero-g-wound, pirate-ambush, eva-rescue, colony-overseer, gravity-well-rescue, boarding-action, patrol-captain |
| Reputation & Trust | Social | Refined | spaceport-crew-hiring, ice-miner-blockade, station-noir, colony-food-crisis, port-surveillance, double-dealing, smuggling-run, labor-strike, refugee-flotilla, black-market-bazaar |
| Rotational Gravity | Physical | Developing | zero-g-wound, eva-rescue |
| Security & Threat | Political | Refined | ice-miner-blockade, pirate-ambush, station-noir, colony-food-crisis, port-surveillance, boarding-action, double-dealing, smuggling-run, refugee-flotilla, patrol-captain, black-market-bazaar |
| Sensors & Scanning | Technical | Refined | deep-space-transit, pirate-ambush, eva-rescue, gravity-well-rescue, port-surveillance, boarding-action, smuggling-run, surface-expedition, patrol-captain |
| Ship Crewing | Social | Refined | spaceport-crew-hiring, deep-space-transit, patrol-captain |
| Social Dynamics | Social | Refined | spaceport-crew-hiring, deep-space-transit, colony-food-crisis, colony-overseer, double-dealing, labor-strike, refugee-flotilla, patrol-captain, black-market-bazaar |
| Station Administration | Political | Refined | ice-miner-blockade, station-noir, colony-food-crisis, colony-overseer, double-dealing, labor-strike, refugee-flotilla |
| Station Services & Infrastructure | Technical | Refined | spaceport-crew-hiring, station-noir, port-surveillance, refugee-flotilla, black-market-bazaar |
| Stealth & Detection | Technical | Draft | smuggling-run |
| Surface Environment | Physical | Developing | colony-overseer, surface-expedition |
| Task & Workforce Management | Technical | Refined | colony-overseer, boarding-action, labor-strike, surface-expedition, patrol-captain |
| Thermal Regulation | Physical | Refined | cold-habitat-survival, colony-overseer, gravity-well-rescue |
| Time Pressure | Technical | Refined | spaceport-crew-hiring, ice-miner-blockade, deep-space-transit, colony-food-crisis, colony-overseer, gravity-well-rescue, double-dealing, labor-strike, surface-expedition, refugee-flotilla, patrol-captain |

**Summary**: 35 systems — 2 Draft, 5 Developing, 28 Refined, 0 Final

---

## System Definitions

### Atmosphere Management
- **Category**: Physical
- **Maturity**: Refined
- **Purpose**: Simulates breathable air composition, recycling, scrubbing, and environmental quality within enclosed spaces. Covers O2/CO2 balance, pressure maintenance, humidity, trace contaminant buildup, leak management, long-duration air quality degradation, and the hard math of how much air exists for how many lungs. Applies to ships, stations, habitats, and the critical question of atmospheric capacity during population surges.
- **Key State Variables**:
  - `o2_level`: float (%) — Oxygen concentration per compartment
  - `co2_level`: float (ppm) — Carbon dioxide concentration (toxic above threshold)
  - `pressure`: float (kPa) — Total atmospheric pressure
  - `humidity`: float (%) — Relative humidity level
  - `trace_contaminants`: float — Accumulated volatile organic compounds, off-gassing
  - `recycler_status`: enum (online/offline/degraded) — Air recycler operational state
  - `scrubber_condition`: float (0-1) — CO2 scrubber filter remaining life
  - `scrubber_load_percentage`: float (0-1) — Current demand vs. capacity
  - `air_quality_index`: float (0-1) — Composite air quality score
  - `leak_rate`: float (kPa/hr) — Rate of atmosphere loss through breaches
  - `odor_accumulation`: float — Long-duration staleness factor
  - `atmospheric_volume`: float (m³) — Total breathable volume
  - `population_load`: int — Number of people consuming atmosphere
  - `maintenance_window`: float (hrs) — Time until scheduled scrubber maintenance
- **Player-Facing Effects**:
  - Breathing difficulty at low O2 or high CO2
  - Drowsiness and cognitive impairment from CO2 buildup
  - Headaches from poor air quality on long transits
  - Audible hissing from pressure leaks
  - Stale air complaints from crew NPCs
  - Condensation on surfaces from humidity issues
  - Filter replacement maintenance prompts
  - Scrubber load warnings when population exceeds capacity
  - Section-by-section air quality displays
  - Life support as a ticking clock during labor disputes or refugee crises
- **Exercised By**: cold-habitat-survival, deep-space-transit, colony-overseer, gravity-well-rescue, labor-strike, refugee-flotilla

### Attitude Control
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates orientation, rotation, and stabilization of vessels and habitats in space. Manages angular momentum, thruster compensation during spin changes, weapon alignment, tumble recovery, and the dual-use tension of attitude thrusters serving as both orientation and emergency braking systems. Critical for habitat spin-up sequences, combat maneuvering, and gravity-well escape burns.
- **Key State Variables**:
  - `angular_momentum`: vec3 — Current rotational state
  - `ship_facing`: quaternion — Current orientation vs. travel vector
  - `rotation_rate`: float (deg/s) — Current rotation speed
  - `thruster_fuel`: float (kg) — Remaining reaction mass for attitude thrusters
  - `gyroscope_status`: enum (online/offline/degraded) — Gyroscope operational state
  - `compensation_load`: float — Current demand for stabilization thrust
  - `tumble_state`: bool — Whether vessel is in uncontrolled tumble
  - `gimbal_status`: enum — Thruster gimbal condition
  - `facing_lock`: bool — Whether orientation is locked for weapon alignment or burn
  - `tidal_torque`: float — External torque from gravity gradients
  - `thruster_allocation`: enum (orientation/braking/split) — How thruster fuel is being used
- **Player-Facing Effects**:
  - Habitat drift or wobble felt/seen by player
  - Thruster firing sounds and vibrations
  - Fuel gauge warnings on HUD
  - Attitude indicator (navball) showing facing vs. velocity
  - Tumble recovery alerts
  - Rotation warnings during maneuvers
  - Dual allocation slider (orientation vs. braking) in emergency scenarios
  - Tidal torque warnings near massive bodies
- **Exercised By**: zero-g-wound, pirate-ambush, gravity-well-rescue

### Cargo & Trade
- **Category**: Economic
- **Maturity**: Refined
- **Purpose**: Simulates goods being transported, their documentation, value, legality, and the gap between what paperwork says and what the hold actually contains. Covers cargo manifests (declared vs. actual), container tracking, trade documentation, customs declarations, contraband classification, hidden compartments, manifest forgery, cargo provenance and authenticity, and the economic context that makes smuggling profitable and detection difficult.
- **Key State Variables**:
  - `manifest_declared`: list — Cargo items as documented (type, quantity, origin)
  - `manifest_actual`: list — What's really in the hold
  - `unit_value`: float — Current market value per unit
  - `depreciation_rate`: float (/hr) — Rate at which perishable cargo loses value
  - `demand_at_destination`: float — How badly the destination needs this cargo
  - `contraband_status`: enum (legal/restricted/contraband/military) — Legality classification per jurisdiction
  - `condition`: float (0-1) — Cargo physical condition (spoilage, damage)
  - `forgery_quality`: float (0-1) — How well falsified documentation holds up to inspection
  - `container_seal_integrity`: float (0-1) — Whether containers show signs of tampering
  - `hidden_compartment`: bool — Whether ship has concealed cargo space
  - `compartment_shielding`: float (0-1) — How well hidden cargo resists scanning
  - `provenance`: enum (clean/stolen/forged) — Chain of custody legitimacy
  - `authenticity`: float (0-1) — Whether goods are genuine vs. counterfeit
  - `cargo_mass`: float (kg) — Actual vs. declared mass (discrepancy flags scanning)
- **Player-Facing Effects**:
  - Trade computer showing declared manifest alongside actual cargo
  - Forgery confidence rating per line item
  - Contraband alert indicators
  - Cargo hold schematic showing standard and hidden compartments
  - Value tracker showing depreciation in real time
  - Market price comparisons between stations
  - Spoilage/damage warnings
  - Inspection depth selector (quick/standard/thorough)
  - Smuggling pattern analysis during inspections
  - Counterfeit risk warnings on purchases
- **Exercised By**: ice-miner-blockade, smuggling-run, patrol-captain, black-market-bazaar

### Combat & Weapons
- **Category**: Technical
- **Maturity**: Developing
- **Purpose**: Simulates offensive and defensive armaments at both ship-to-ship and personnel scales. Covers targeting, firing solutions, ammunition, weapon state, damage output, point-defense systems, and the distinct perspective of combat experienced through helmet cams and biometric feeds rather than directly. Includes Rules of Engagement modes, suppression mechanics, and the lethality of firefights in pressurized environments.
- **Key State Variables**:
  - `weapon_type`: enum — Weapon classification and mount point
  - `ammunition`: int — Remaining rounds or charge level
  - `firing_arcs`: geometry — Angular coverage of each weapon
  - `lock_on_status`: enum (searching/locking/locked) — Targeting state
  - `rate_of_fire`: float — Shots per second
  - `heat_buildup`: float (0-1) — Thermal load from sustained fire
  - `accuracy_at_range`: curve — Hit probability vs. distance
  - `damage_output`: float — Damage per hit
  - `point_defense_mode`: bool — Automated intercept of incoming projectiles
  - `engagement_status`: enum (no contact/contact/suppressed/pinned/advancing) — Per-unit fire status
  - `rules_of_engagement`: enum (lethal/non-lethal/restricted) — Current ROE mode
  - `fire_superiority`: float (0-1) — Which side has the advantage in an engagement
  - `friendly_fire_risk`: float (0-1) — Risk in tight compartments
- **Player-Facing Effects**:
  - Targeting reticle and lock indicators (ship combat)
  - Weapon heat gauge and ammo counter
  - Firing arc overlay on nav display
  - Hit/miss feedback with visual and audio cues
  - Point-defense interception alerts
  - Helmet cam feeds showing firefights (boarding)
  - Fire team engagement indicators on tactical board
  - ROE toggle with consequences
  - Suppression and pinned-down alerts
  - Breaching charge authorization prompts
- **Exercised By**: pirate-ambush, boarding-action

### Communications
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates all forms of signal transmission and reception — distress calls, open broadcasts, private channels, encrypted messages, propaganda, electronic warfare, monitored channels, dead drops, word-of-mouth networks, and the rumor mill. Covers signal degradation from distance, terrain, magnetosphere interference, hull shielding, dust storms, and the critical distinction between what's encrypted, what's monitored, and what happens when you say the wrong thing on the wrong channel.
- **Key State Variables**:
  - `antenna_status`: enum (online/offline/damaged) — Physical antenna condition
  - `power_allocation`: float (W) — Power dedicated to comms
  - `signal_range`: float (km) — Effective broadcast/receive range
  - `channels`: list — Active channels (open/encrypted/military/faction) with content
  - `encryption_level`: int — Security of private communications
  - `jamming_status`: bool — Whether signals are being jammed
  - `nearby_receivers`: list — Entities in range that can hear broadcasts
  - `spoofed_signals`: list — Fake transponder or distress signals active
  - `message_logs`: list — Recorded communications history (potential evidence)
  - `line_of_sight`: bool — Whether direct signal path exists
  - `rumor_propagation`: float — Rate at which information spreads through NPC network
  - `signal_delay`: float (s) — Light-speed lag to recipients
  - `interference_level`: float (0-1) — Environmental signal degradation
  - `intercept_risk`: float (0-1) — Probability of transmission being captured by hostiles
  - `dead_drops`: list — Physical message exchange points
- **Player-Facing Effects**:
  - Comms panel with open and private channel tabs
  - Static and signal degradation at range limits or during interference
  - Ability to broadcast, jam, intercept, or spoof
  - Distress beacon toggle
  - Intercepted messages as investigation clues
  - Anonymous tip capability
  - Suit radio with breathing audio in EVA
  - Response delay based on distance
  - Monitoring warnings when transmitting on unsecured channels
  - Comm range circles on maps showing where contact will be lost
  - Rumor mill distortion of information through NPC networks
- **Exercised By**: cold-habitat-survival, ice-miner-blockade, pirate-ambush, station-noir, eva-rescue, gravity-well-rescue, port-surveillance, boarding-action, double-dealing, smuggling-run, labor-strike, surface-expedition, refugee-flotilla, patrol-captain, black-market-bazaar

### Diplomacy & Negotiation
- **Category**: Political
- **Maturity**: Refined
- **Purpose**: Simulates multi-party negotiation between factions, groups, or individuals. Tracks demands, concessions, red lines, leverage, trust, deal-making, and the formal/informal dynamics of backroom dealing. The player can act as participant, mediator, spoiler, or double agent. Covers treaty negotiation, labor arbitration, humanitarian crises, and the compounding risk of playing both sides.
- **Key State Variables**:
  - `parties`: list — Entities involved in negotiation
  - `demands`: map (party → list) — What each party wants
  - `red_lines`: map (party → list) — Non-negotiable positions
  - `willingness`: map (party → float) — How open each party is to compromise
  - `trust_between`: map (pair → float) — Bilateral trust levels
  - `leverage`: map (party → list) — Resources or threats each party controls
  - `proposed_deals`: list — Terms on the table
  - `mediator_credibility`: float — Player's standing as a neutral broker
  - `negotiation_phase`: enum (opening/mid-stage/endgame) — Where talks stand
  - `public_position`: map (party → text) — What each party says publicly
  - `private_bottom_line`: map (party → text) — What each party will actually accept
  - `deadlock_status`: bool — Whether negotiations have stalled
  - `backroom_deals`: list — Unofficial arrangements in progress
- **Player-Facing Effects**:
  - Negotiation dialogue with visible faction stances
  - Demand/offer proposal interface
  - Trust indicators shifting based on actions
  - Leverage assessment display
  - Deal acceptance/rejection with consequences
  - Faction ultimatum deadlines
  - Backroom briefing sessions with each side
  - Tension indicators when contradictory advice surfaces
  - Information asymmetry the player can exploit or be trapped by
- **Exercised By**: ice-miner-blockade, colony-food-crisis, double-dealing, labor-strike, refugee-flotilla

### Economy & Currency
- **Category**: Economic
- **Maturity**: Refined
- **Purpose**: Simulates money flows, pricing, wages, debts, black markets, barter systems, favor economies, and economic pressure across the simulation. Covers personal finances, institutional budgets, commodity markets, contract economics, production value, shadow economies with physical chits, and the financial evidence trails that link to corruption and crime. Economic conditions drive faction grievances, labor availability, black market emergence, smuggling incentives, and player urgency.
- **Key State Variables**:
  - `player_balance`: float — Player's available funds (formal credits)
  - `physical_currency`: float — Chits, barter tokens, off-book funds
  - `local_price_index`: float — Cost multiplier at current location
  - `wage_expectations`: map (role → range) — What workers expect to be paid locally
  - `debt_ledgers`: list — Outstanding debts (who owes whom, how much, terms)
  - `fee_rates`: map (service → float/hr) — Ticking costs like berthing, docking, storage
  - `commodity_prices`: map (good → float) — Market prices for trade goods
  - `inflation_rate`: float — Local economic health indicator
  - `black_market_markup`: float — Price multiplier for illegal/scarce goods
  - `financial_records`: list — Transaction logs, shell accounts, money trails
  - `hoarding_levels`: map (good → float) — How much of a commodity is being hoarded
  - `price_controls`: map (good → float) — Government-imposed price caps if active
  - `favor_economy`: map (entity → list) — Favors owed and owing
  - `raid_threat_markup`: float — Price volatility driven by enforcement threat
  - `bribe_costs`: map (contact → float) — What it costs to buy cooperation
- **Player-Facing Effects**:
  - Account balance display with transaction history
  - Price tags on goods and services
  - Wage negotiation during hiring
  - Fee timers showing accumulating costs
  - Black market contacts and inflated prices
  - Financial records as investigation evidence
  - Economic impact of policy decisions
  - Inflation warnings
  - Bribe negotiation interface
  - Prices that shift as raid rumors intensify
  - Favor economy tracking (owed and owing)
  - Cost-benefit analysis of settlement terms
- **Exercised By**: spaceport-crew-hiring, ice-miner-blockade, station-noir, colony-food-crisis, double-dealing, smuggling-run, labor-strike, refugee-flotilla, black-market-bazaar

### Equipment & Repair
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates the state of mechanical and electrical components and the ability to maintain, repair, or jury-rig them. Covers tool requirements, spare parts, skill modifiers, bypass feasibility, cascading failure risk, field repair under adverse conditions (EVA suits, combat, dust storms, zero-g), condemned equipment, counterfeit parts risk, and the severe dexterity penalties of working in hostile environments. Scales from personal tool kits to ship drive couplings to station-scale industrial equipment.
- **Key State Variables**:
  - `component_health`: map (component → float 0-1) — Condition of each component
  - `wear_rate`: map (component → float/hr) — How fast components degrade under use
  - `required_parts`: map (repair → list) — Parts needed for each repair job
  - `spare_parts_inventory`: list — Available replacement parts
  - `available_tools`: list — Tools currently accessible
  - `bypass_feasibility`: map (system → bool) — Whether safety bypasses are possible
  - `repair_skill`: float — Competence modifier (player or assigned crew)
  - `repair_difficulty`: float — Environmental modifier (gloves, zero-g, combat, dust, darkness)
  - `cascading_failure_risk`: map (component → float) — Probability of failure spreading
  - `maintenance_backlog`: list — Queued repairs with priority
  - `jury_rig_effectiveness`: float — How well improvised repairs hold
  - `condemned_equipment`: list — Items that should have been replaced
  - `counterfeit_risk`: float (0-1) — Probability replacement parts are fake
  - `repair_time_estimate`: float (hrs) — Expected duration of repair
  - `field_repair_quality`: float (0-1) — Durability of repairs done outside a proper shop
- **Player-Facing Effects**:
  - Damage control board with system status lights
  - Component inspection showing health and required repairs
  - Repair interface with part and tool requirements
  - Scavenging mini-interactions (strip this to fix that)
  - Jury-rig attempts with success/failure outcomes
  - Degradation warnings before failures occur
  - Sparks/smoke/venting visual cues for active damage
  - Repair time countdowns
  - Glove dexterity warnings during EVA repairs
  - Condemned equipment flags
  - Counterfeit part detection challenges
  - "Repair quality" indicator for field fixes
- **Exercised By**: cold-habitat-survival, deep-space-transit, pirate-ambush, eva-rescue, colony-overseer, gravity-well-rescue, boarding-action, labor-strike, surface-expedition, patrol-captain, black-market-bazaar

### EVA & Spacewalk
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates extravehicular activity across all contexts — vacuum spacewalks, surface expeditions on hostile moons, combat ship-to-ship crossings, and multi-day suit operations far from shelter. Covers suit integrity, consumable budgets (oxygen, battery, propellant, thermal, water, filters), tether management, the extreme physical toll of working outside, dust degradation of seals and visors, and the qualitative difference between a short excursion and a multi-day traverse in a sealed suit.
- **Key State Variables**:
  - `suit_o2_reserve`: float (minutes) — Remaining breathable oxygen
  - `suit_battery`: float (0-1) — Suit power level
  - `thruster_propellant`: float (kg) — Maneuvering fuel mass
  - `thermal_balance`: float — Heat state (sun exposure vs. shadow vs. exertion)
  - `suit_integrity`: float (0-1) — Seal and hull condition
  - `tether_status`: enum (attached/detached/broken) — Tether state
  - `visor_condition`: enum (clear/fogged/scored/damaged) — Visibility state
  - `fatigue_rate_multiplier`: float — EVA exertion factor (3-5x normal)
  - `radiation_exposure`: float (mSv) — Accumulated dose outside shielding
  - `co2_filter_saturation`: float (0-1) — Scrubber filter life (degrades faster in dust)
  - `water_reserve`: float (L) — Drinking water in suit
  - `glove_dexterity`: float (0-1) — Manual interaction penalty (degrades with cold, fatigue)
  - `boot_traction`: float (0-1) — Surface grip (varies with terrain)
  - `dust_seal_wear`: float (0-1) — Joint seal degradation from abrasive dust
  - `days_in_suit`: int — Multi-day EVA duration tracker
- **Player-Facing Effects**:
  - HUD overlay with consumable gauges ticking down in real time
  - Fogging visor at high exertion
  - Glove dexterity penalties on all manual interactions
  - Audio limited to suit radio and own breathing
  - Tether tension/snap warnings
  - Radiation dosimeter ticking in unshielded zones
  - Movement is slow, deliberate, and exhausting
  - Per-crew consumable dashboard on multi-person expeditions
  - Filter clog warnings when dust density is high
  - Visor clarity degradation from dust scoring
  - Breathing audio and heartbeat intensifying with exertion
  - Crossing status display during ship-to-ship transit
- **Exercised By**: eva-rescue, boarding-action, surface-expedition

### Faction System
- **Category**: Political
- **Maturity**: Refined
- **Purpose**: Simulates organized groups with shared interests, hierarchies, resources, grievances, and agendas. Factions have internal cohesion that can fracture, relationships with other factions, internal politics (hawks vs. doves), and the ability to take collective action (blockades, strikes, raids, protests, negotiations). Faction formation can be emergent — occupational groups, ethnic groups, or ad-hoc alliances forming under pressure. Factions have delegation rosters with individual members who may not all agree with leadership strategy.
- **Key State Variables**:
  - `name`: string — Faction identifier
  - `leadership`: list (NPC refs) — Who makes decisions
  - `membership`: int — Size and manpower
  - `resources`: float — Financial and material resources
  - `grievances`: list — Active complaints with targets and severity
  - `demands`: list — What the faction is currently seeking
  - `stance`: enum (passive/negotiating/hostile/allied) — Current posture
  - `cohesion`: float (0-1) — Internal unity (low = risk of splintering)
  - `willingness_to_use_force`: float (0-1) — How close to violence
  - `relationships`: map (faction → float) — Standing with other factions
  - `internal_politics`: map (wing → strength) — Hawks vs. doves, moderates vs. radicals
  - `delegation_roster`: list (NPC refs) — Individual members with personal agendas
  - `war_readiness`: float (0-1) — Military/economic capacity for sustained conflict
  - `splinter_risk`: float (0-1) — Probability of faction breaking apart
- **Player-Facing Effects**:
  - Faction reputation display
  - Dialogue reflecting faction stance toward player
  - Access granted/denied based on faction relations
  - Faction actions visible in the world (blockades, patrols, strikes, raids, protests)
  - Splinter events when cohesion drops
  - Faction formation visible as tensions rise
  - Internal faction disagreements the player can exploit
  - Faction members who might be turned or who independently discover information
- **Exercised By**: ice-miner-blockade, colony-food-crisis, double-dealing, labor-strike, refugee-flotilla

### Fleet & Ship Movement
- **Category**: Physical
- **Maturity**: Refined
- **Purpose**: Simulates positions, velocities, accelerations, and formation tactics of multiple ships in 3D space. Covers patrol routes, blockade formations, intercept trajectories, pursuit/evasion calculations, flotilla management, docking logistics, individual ship condition tracking, and the tactical geometry of multi-ship encounters.
- **Key State Variables**:
  - `ship_positions`: map (ship → vec3) — Current position of each vessel
  - `ship_velocities`: map (ship → vec3) — Current velocity vectors
  - `formation`: enum/pattern — Current fleet arrangement
  - `intercept_trajectories`: map (ship → path) — Calculated intercept courses
  - `closure_rates`: map (ship pair → float) — How fast ships are converging
  - `patrol_routes`: list (path) — Defined movement patterns
  - `transponder_data`: map (ship → identity) — Broadcast identification
  - `fuel_reserves`: map (ship → float) — Per-ship fuel state
  - `formation_break_conditions`: list — When the formation falls apart
  - `hull_integrity`: map (ship → float) — Per-ship structural condition
  - `life_support_status`: map (ship → data) — Per-ship atmosphere and supplies
  - `docking_port_availability`: list — Available berths and queue
- **Player-Facing Effects**:
  - Nav display with ship contacts and vector lines
  - Transponder IDs and formation patterns visible
  - Intercept countdown timers
  - Pursuit cone visualization
  - Relative velocity readouts
  - Formation overlay on tactical display
  - Individual ship condition reports in flotilla scenarios
  - Docking port status and queue
  - Approach timeline displays
- **Exercised By**: ice-miner-blockade, pirate-ambush, refugee-flotilla

### Fluid Dynamics
- **Category**: Physical
- **Maturity**: Developing
- **Purpose**: Simulates how liquids (blood, water, fuel, coolant, oxygen) behave under varying gravity conditions and in vacuum. Critical for medical scenarios in micro-gravity, EVA suit breaches, propellant management, and engineering scenarios involving leaks.
- **Key State Variables**:
  - `gravity_level`: float (g) — Current effective gravity affecting fluids
  - `fluid_volumes`: map (fluid → float) — Tracked fluid quantities
  - `fluid_locations`: map (fluid → spatial) — Where fluids are accumulating or floating
  - `surface_tension_regime`: enum (gravity-dominant/tension-dominant) — Behavior mode
  - `containment_status`: map (fluid → bool) — Whether fluid is contained or free
  - `aspiration_risk`: float (0-1) — Risk of fluid entering airways (medical)
  - `leak_rate`: float — Rate of fluid loss through breaches
  - `crystallization`: bool — Whether venting fluids are freezing in vacuum
- **Player-Facing Effects**:
  - Floating blood globules in zero-g, pooling/flowing under gravity
  - Fluid behavior visibly changing during spin-up/spin-down
  - Blood/fluid drift into dangerous areas (electronics, airways, helmets)
  - Oxygen venting visibly as crystallizing gas from suit punctures
  - Propellant slosh behavior during thrust
- **Exercised By**: zero-g-wound, eva-rescue

### Food & Water Supply
- **Category**: Biological
- **Maturity**: Refined
- **Purpose**: Simulates production, storage, distribution, and consumption of food and water. Covers individual production sources (hydroponics, protein vats, greenhouses), total reserves as calorie/day countdowns, rationing, spoilage, contamination, nutritional quality, water recycler capacity, and the physiological and social effects of scarcity — including the hard math of surplus capacity when populations suddenly change.
- **Key State Variables**:
  - `production_sources`: map (source → capacity/health) — Individual food production systems
  - `total_reserves`: float (calories) — Total food energy available
  - `days_of_supply`: float — Reserves ÷ daily consumption at current rate
  - `consumption_rate`: map (group → kcal/day) — Caloric consumption per population segment
  - `distribution_method`: enum (open/rationed/black_market) — How food reaches people
  - `spoilage_rate`: float — Rate of food loss from degradation
  - `contamination_status`: map (source → bool) — Whether a food source is compromised
  - `nutritional_quality`: float (0-1) — How nutritionally complete the available food is
  - `water_reserves`: float (L) — Potable water available
  - `water_recycler_efficiency`: float (0-1) — Water reclamation rate
  - `water_filter_condition`: float (0-1) — Filter remaining life
  - `surplus_capacity`: float — How much population growth reserves can absorb
- **Player-Facing Effects**:
  - Food reserve countdown display (with and without population changes)
  - Pantry/stores inventory
  - Production status dashboards
  - Rationing controls and tier displays
  - Meal quality and variety indicators
  - Hunger indicators on NPCs
  - Spoilage and contamination alerts
  - Water reserves and recycler status
  - Crew complaints about food quality
  - Black market food price tracking
- **Exercised By**: deep-space-transit, colony-food-crisis, colony-overseer, refugee-flotilla

### Habitat Integrity
- **Category**: Physical
- **Maturity**: Refined
- **Purpose**: Simulates the structural condition of habitats, stations, ship hulls, and target vessels during boarding — including seals, compartments, radiation shielding, pressure management, and stress tolerance. Covers static damage (micrometeorites, debris), dynamic stress (spin loads, impacts, tidal forces, emergency maneuvers), combat damage (breaching charges, weapons fire, explosions), thermal expansion, atmospheric friction during aerobraking, and the cascading structural consequences of fighting inside a pressurized ship.
- **Key State Variables**:
  - `hull_integrity`: map (section → float 0-1) — Structural health per section
  - `seal_status`: map (seal → enum) — Door, hatch, and viewport seal condition
  - `structural_stress`: map (section → float) — Current stress load vs. tolerance
  - `spin_rated_rpm`: float — Maximum safe rotation speed
  - `breach_status`: map (section → bool) — Active hull breaches
  - `radiation_shielding`: map (section → float) — Shielding effectiveness
  - `pressure_status`: map (section → enum) — Pressurized/leaking/vacuum per compartment
  - `tidal_flexing_stress`: float — Stress from gravity gradients
  - `thermal_expansion_stress`: float — Stress from temperature differentials
  - `ablation_rate`: float — Material loss during atmospheric contact
  - `microcrack_propagation`: float — Rate of structural degradation
  - `blast_damage`: map (section → float) — Damage from explosives and weapons fire
  - `decompression_cascade_risk`: map (section → list) — Adjacent sections at risk
- **Player-Facing Effects**:
  - Visible hull damage, frost on interior surfaces, cracks
  - Creaking/groaning sounds under structural stress
  - Breach alarms and compartment isolation prompts
  - Structural warnings during spin-up or maneuvers
  - Deformation visible at extreme stress
  - Target ship cross-section showing pressure status (color-coded)
  - "Breach here will decompress these adjacent compartments" preview
  - Ablation effects during atmospheric contact
  - Population density alerts for stations
- **Exercised By**: cold-habitat-survival, zero-g-wound, colony-overseer, gravity-well-rescue, boarding-action, refugee-flotilla

### Inventory & Personal Equipment
- **Category**: Technical
- **Maturity**: Draft
- **Purpose**: Simulates what the player is carrying on their person, wearing, and has immediately accessible — and how that loadout is perceived by everyone around them. Covers carried items, worn equipment, concealed items, encumbrance, item visibility to NPCs, and the social signaling of personal equipment in environments where appearances determine how people treat you.
- **Key State Variables**:
  - `carried_items`: list — Weapons, tools, trade goods, credits, documents
  - `worn_equipment`: list — Suit, armor, visible holsters, clothing
  - `concealed_items`: list — Hidden items with detection difficulty
  - `encumbrance`: float (0-1) — Carry weight vs. capacity
  - `item_visibility`: map (item → float) — How visible each item is to NPCs
  - `item_legality`: map (item → enum) — Legal status per jurisdiction
  - `quick_access_slots`: list — Items available for immediate use
  - `storage_locations`: list — Pockets, bags, suit compartments
  - `item_condition`: map (item → float 0-1) — Wear and damage on carried items
- **Player-Facing Effects**:
  - Choice of what to carry into a location and what to leave on the ship
  - Visible weapons that deter theft but attract attention
  - Concealed valuables that reduce robbery risk but slow access
  - NPC reactions changing based on visible loadout
  - Encumbrance affecting movement speed and fatigue
  - Legal exposure from carrying contraband items
  - Social signaling through equipment choices
- **Exercised By**: black-market-bazaar

### Labor Market
- **Category**: Economic
- **Maturity**: Developing
- **Purpose**: Simulates workforce supply, demand, compensation, skill availability, worker satisfaction, and collective labor action. Covers hiring pools, wage structures, labor contracts, workforce morale, strike mechanics, scab availability, blacklist registries, union organizing, and the political dimension of labor rights. Labor market conditions feed directly into faction demands and political leverage.
- **Key State Variables**:
  - `available_candidates`: list (NPC refs) — Pool of hireable NPCs at this location
  - `skill_distribution`: map (skill → distribution) — Statistical spread of skills
  - `wage_floor`: float — Minimum wage anyone will accept locally
  - `desperation_index`: float (0-1) — How desperate the local labor pool is
  - `unemployment_rate`: float — Fraction of population seeking work
  - `competing_demand`: int — How many other employers are hiring
  - `labor_contracts`: list — Active employment agreements with terms
  - `workforce_morale`: map (crew → float) — Satisfaction per work group
  - `strike_participation_rate`: float (0-1) — Fraction of workforce on strike
  - `scab_availability`: int — Replacement workers available
  - `blacklist_registries`: list — Workers banned by employers
  - `union_status`: enum (none/organizing/recognized/bargaining) — Collective bargaining state
  - `skill_scarcity_index`: map (skill → float) — How hard specific skills are to find
- **Player-Facing Effects**:
  - Job board listings with varying quality
  - Bar/cantina conversations revealing available talent
  - Candidate availability changing over time
  - Competition from other captains visibly hiring
  - Desperation-driven candidates approaching the player
  - Workforce status dashboard and strike participation tracker
  - Wage comparison tools
  - Union organizing progress indicators
  - Labor market conditions across nearby stations
- **Exercised By**: spaceport-crew-hiring, labor-strike

### Law & Jurisdiction
- **Category**: Political
- **Maturity**: Refined
- **Purpose**: Simulates legal frameworks, jurisdictional boundaries, and enforcement mechanisms that govern stations, ships, and territories — and the gaps between them. Covers corporate charters, transit compacts, sovereign claims, evidentiary standards, warrants, extradition, customs enforcement authority, contraband classification, search-and-seizure, labor rights, humanitarian exemptions, blockade legality, patrol mandates, and the ability to forum-shop between authorities with different motivations. Different jurisdictions treat the same cargo, the same actions, and the same people differently.
- **Key State Variables**:
  - `governing_authority`: enum — Legal basis (corporate charter, transit compact, sovereign claim, military)
  - `applicable_laws`: list — Laws in effect at current location
  - `jurisdictional_overlaps`: list — Areas where multiple authorities claim jurisdiction
  - `enforcement_bodies`: list — Local security, corporate compliance, transit court, guild arbitration
  - `evidentiary_standards`: map (body → enum) — What each authority considers proof
  - `active_warrants`: list — Warrants issued for/against entities
  - `legal_proceedings`: list — Active cases and their status
  - `corruption_index`: map (body → float) — How compromised each authority is
  - `extradition_agreements`: map (pair → bool) — Which authorities cooperate
  - `detention_authority`: map (body → enum) — Who can hold whom and for how long
  - `contraband_schedule`: map (jurisdiction → list) — What's illegal where and at what tier
  - `search_authority`: enum — Probable cause requirements for inspection
  - `labor_rights_statutes`: list — Worker protections in current jurisdiction
  - `humanitarian_exemptions`: list — Legal carve-outs for medical/aid supplies
  - `penalty_structure`: map (offense → consequence) — Fines, impound, imprisonment
  - `patrol_mandate`: data — Authorized actions, sector boundaries, reporting requirements
- **Player-Facing Effects**:
  - Ability to file complaints or charges with different authorities
  - Jurisdictional conflicts that block or enable action
  - Legal threats from NPCs
  - Warrants issued for or against the player
  - Option to forum-shop for a sympathetic jurisdiction
  - Different evidentiary standards at different authorities
  - Extradition risks when moving between jurisdictions
  - Contraband classification lookup by jurisdiction
  - Penalty preview if caught
  - Legal advisor prompts during inspections
  - Humanitarian challenge filings
  - Jurisdiction overlay on navigation plot
- **Exercised By**: station-noir, smuggling-run, labor-strike, port-surveillance, patrol-captain, black-market-bazaar

### Medical & Injury
- **Category**: Biological
- **Maturity**: Refined
- **Purpose**: Simulates wound types, bleeding, infection, treatment options, recovery, triage, and medical facility capacity. Treatment effectiveness varies dramatically with available equipment, gravity conditions, EVA suit constraints, field conditions, dust contamination, and medical skill. Covers everything from minor cuts to combat trauma, radiation sickness, contagion risk from long-duration spaceflight, pharmaceutical inventory management, and the severe constraints of treating wounds inside a sealed suit in the field.
- **Key State Variables**:
  - `wound_location`: enum (body part) — Where the injury is
  - `wound_type`: enum (laceration/fracture/burn/shrapnel/g-force/decompression/radiation/hypothermia/hyperthermia) — Injury classification
  - `severity`: float (0-1) — How life-threatening the wound is
  - `bleed_rate`: float (mL/min) — Current rate of blood loss
  - `blood_volume`: float (L) — Remaining blood volume
  - `clotting_status`: enum (normal/impaired/impossible) — Affected by gravity
  - `infection_risk`: float (0-1) — Probability of wound infection (elevated by dust contamination)
  - `treatment_applied`: list — Medical interventions performed
  - `medical_supplies_remaining`: int — Available treatment resources
  - `consciousness_threshold`: float — Blood volume at which patient loses consciousness
  - `in_suit_treatment_limitation`: bool — Whether patient is in EVA suit
  - `medical_bay_capacity`: data — Beds, staff, supplies available
  - `contagion_risk`: float (0-1) — Disease transmission probability
  - `triage_priority_queue`: list — Patients ranked by urgency
  - `staff_fatigue`: float (0-1) — Medical personnel exhaustion
  - `pharmaceutical_inventory`: map (drug → count) — Tracked medications with discrepancies
  - `pain_level`: float (0-1) — Affects performance and behavior
- **Player-Facing Effects**:
  - Wound inspection interface showing severity and options
  - Blood loss visual effects (screen darkening, tunnel vision)
  - Pain indicators affecting movement and actions
  - Treatment options varying by supplies, gravity, and suit status
  - Casualty biometric readout on HUD
  - Recovery timeline after treatment
  - Injury alerts with severity classification
  - High-g warning overlays during combat
  - Medical bay capacity display
  - Triage decision interface
  - Pharmaceutical inventory with shortage alerts
  - Contagion risk warnings
  - Biometric dashboard per marine (boarding scenarios)
- **Exercised By**: zero-g-wound, pirate-ambush, eva-rescue, boarding-action, surface-expedition, refugee-flotilla, patrol-captain

### Navigation & Fuel
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates route planning, fuel consumption, trajectory management, and travel time across all scales. Covers delta-v budgets, burn calculations, intercept windows, diversion costs, escape trajectories, orbital mechanics (periapsis, Oberth effect, aerobraking), patrol routes, terrain navigation on surfaces, debris field passage, and the critical "point of no return" calculations where fuel becomes insufficient for safe options. Every diversion costs fuel that cannot be replaced.
- **Key State Variables**:
  - `position`: vec3 — Current location
  - `velocity`: vec3 — Current velocity vector
  - `destination_options`: list — Reachable destinations with costs
  - `fuel_reserves`: float (kg) — Remaining propellant mass
  - `burn_rate`: float (kg/s) — Fuel consumption during thrust
  - `delta_v_budget`: float (m/s) — Remaining velocity change capacity
  - `travel_time`: map (destination → hours) — ETA to each option
  - `route_hazards`: list — Debris fields, radiation zones, subsurface voids, etc.
  - `intercept_windows`: list — Time-critical approach opportunities
  - `escape_vectors`: list — Available flee trajectories with fuel costs
  - `drift_trajectory`: path — Where the ship goes if engines fail
  - `orbital_parameters`: data — Periapsis, apoapsis, inclination, time-to-periapsis
  - `escape_velocity_threshold`: float — Delta-v needed to leave current gravity well
  - `oberth_multiplier`: float — Efficiency bonus near periapsis
  - `terrain_map`: data — Surface route options with hazard ratings (surface scenarios)
  - `diversion_cost_calculator`: func — Fuel to reach a target and return to route
  - `patrol_completion_percentage`: float — How much of assigned route is covered
- **Player-Facing Effects**:
  - Nav computer interface with route planner
  - Fuel gauge with remaining delta-v
  - ETA calculations and diversion cost comparisons
  - Intercept countdown timers
  - Escape route highlights during combat
  - "Point of no return" indicators for fuel-critical decisions
  - Hazard warnings on planned routes
  - Burn schedule display for long transits
  - Decaying orbit display with periapsis countdown
  - Terrain map with route overlays and hazard ratings
  - Diversion calculator showing cost of off-route actions
  - Patrol route with sectors covered vs. skipped
- **Exercised By**: ice-miner-blockade, deep-space-transit, pirate-ambush, eva-rescue, gravity-well-rescue, smuggling-run, surface-expedition, patrol-captain, port-surveillance

### NPC Identity & Personality
- **Category**: Social
- **Maturity**: Refined
- **Purpose**: Gives non-player characters persistent identities, skills, personalities, motivations, histories, secrets, and behavioral patterns. NPCs are simulated entities with their own agendas and needs — not quest dispensers. Under sustained stress, hidden traits emerge: coping mechanisms, breaking points, vices, loyalties, and fears. NPCs lie, hoard, form alliances, betray trust, and surprise the player based on their internal state. Scales from four-person expedition crews to marine fire teams to hundreds of station residents to faction leaders shaping policy.
- **Key State Variables**:
  - `name`: string — NPC identifier
  - `background`: text — History, origin, experience
  - `skills`: map (skill → float) — Rated competencies
  - `personality_traits`: list — Core descriptors (trusting/paranoid, methodical/impulsive, aggressive/cautious)
  - `motivation`: enum/text — What this NPC currently wants most
  - `trust`: map (entity → float) — Trust toward player and other NPCs
  - `loyalty`: float (0-1) — Commitment to current employer/group/faction
  - `morale`: float (0-1) — Current emotional/mental state
  - `fear_level`: float (0-1) — How afraid the NPC currently is
  - `secrets`: list — Information the NPC is hiding
  - `breaking_point`: float — Stress threshold beyond which behavior changes dramatically
  - `stress_tolerance`: float — How much pressure the NPC can absorb
  - `coping_mechanisms`: list — How the NPC deals with stress
  - `hunger_level`: float (0-1) — Current nutritional state
  - `faction_affiliation`: ref — Which faction this NPC belongs to
  - `relationships`: map (NPC → relationship) — Connections to other NPCs
  - `alibi_consistency`: float — How well their story holds up under questioning
  - `perceptiveness`: float (0-1) — How likely to notice anomalies
  - `corruption_willingness`: float (0-1) — How open to bribes or rule-bending
  - `personal_agenda`: text — Goals beyond faction loyalty
  - `combat_experience`: float (0-1) — Military/tactical competence
  - `desperation_threshold`: float — Point at which self-preservation overrides loyalty
- **Player-Facing Effects**:
  - Dialogue reflecting personality, trust, fear, and current state
  - Observable behavior patterns (nervous, aggressive, helpful, evasive)
  - Performance variation based on morale, skill, and stress
  - Relationship-driven events (alliances, conflicts, betrayals)
  - Witnesses who clam up or open up based on approach
  - NPCs contradicting each other's stories
  - Stress responses emerging over sustained scenarios
  - Background revealed through conversation and observation
  - Behavioral cues during surveillance (pace changes, reflection checks)
  - Personality-driven dialogue in helmet cam audio
  - NPCs who pack up and flee when threat escalates
  - Trust indicators shifting based on player decisions
- **Exercised By**: spaceport-crew-hiring, deep-space-transit, station-noir, colony-food-crisis, colony-overseer, port-surveillance, boarding-action, double-dealing, smuggling-run, labor-strike, surface-expedition, refugee-flotilla, patrol-captain, black-market-bazaar

### Player Health
- **Category**: Biological
- **Maturity**: Refined
- **Purpose**: Tracks the player's physical and cognitive condition and its cascading effects on capability. Synthesized across survival (temperature, oxygen, fatigue), trauma (blood loss, consciousness), endurance (nutrition, sleep debt), combat (g-force, adrenaline), EVA (radiation, exertion), command (decision fatigue, psychological weight of authority), and surface expedition (cumulative multi-day degradation) scenarios. The player is subject to the same environmental pressures as NPCs, and visible deterioration affects crew confidence.
- **Key State Variables**:
  - `core_temperature`: float (°C) — Hypothermia/hyperthermia tracking
  - `blood_volume`: float (L) — Current blood volume
  - `blood_pressure`: float (mmHg) — Cardiovascular state
  - `o2_saturation`: float (0-1) — Blood oxygen level
  - `consciousness`: float (0-1) — Awareness level
  - `fatigue`: float (0-1) — Exhaustion level
  - `sleep_debt`: float (hours) — Accumulated sleep deficit
  - `caloric_reserves`: float (kcal) — Energy from food
  - `hydration`: float (0-1) — Water balance
  - `pain`: float (0-1) — Pain level affecting concentration and speed
  - `stress`: float (0-1) — Psychological stress level
  - `radiation_exposure`: float (mSv) — Accumulated radiation dose
  - `g_force_tolerance`: float — Current tolerance for acceleration
  - `immune_function`: float (0-1) — Resistance to illness
  - `decision_fatigue`: float (0-1) — Accumulated cognitive load from hard calls
  - `command_presence`: float (0-1) — How steady the player appears to crew
- **Player-Facing Effects**:
  - Visual effects: blurring, tunnel vision, screen darkening, blackout at high g
  - Movement speed and stamina reductions
  - Labored breathing sounds, intensifying with exertion
  - Reaction time degradation
  - Irritability affecting dialogue options
  - Status indicators on HUD
  - Hunger and thirst indicators
  - Radiation dosimeter
  - Incapacitation/death at critical thresholds
  - Decision-making debuffs (missed details, narrowed options)
  - Crew noticing the player's exhaustion in dialogue
  - Information overload blur when too many inputs compete
- **Exercised By**: cold-habitat-survival, zero-g-wound, deep-space-transit, pirate-ambush, eva-rescue, colony-food-crisis, colony-overseer, gravity-well-rescue, boarding-action, surface-expedition, patrol-captain

### Power Grid
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates electrical power generation, storage, distribution, and consumption. The foundational technical system — most other technical systems depend on it. Covers reactor/solar/battery sources, distribution buses, load balancing, overclock capability, and the hard tradeoffs of routing limited energy to competing systems under crisis. Applies to player ships, target ships during boarding, and stations where power must serve expanded populations.
- **Key State Variables**:
  - `stored_energy`: float (kWh) — Total energy in batteries/capacitors
  - `generation_rate`: float (kW) — Current power production
  - `reactor_output_mode`: enum (cruise/combat/emergency) — Operating level
  - `consumption_rate`: map (subsystem → kW) — Power draw per subsystem
  - `distribution_bus_status`: enum (online/offline/damaged) — Main power bus state
  - `cell_health`: map (cell → float 0-1) — Battery degradation
  - `load_priority`: ordered list — Which systems get power first when scarce
  - `overclock_status`: bool — Whether reactor is running above safe limits
  - `overclock_heat`: float — Thermal risk from overclocking
  - `reactor_damage_risk`: float — Probability of reactor failure at current output
  - `section_power_status`: map (section → bool) — Per-section power (for boarding/station scenarios)
  - `emergency_power_reserves`: float — Backup power duration
- **Player-Facing Effects**:
  - Power distribution panel with allocation controls
  - Reactor heat gauge and overclock warnings
  - Lights flickering or dead when power is low
  - Systems refusing to start without sufficient power
  - Battery health indicators
  - Brownout flicker effects
  - System shutdown notifications when power is pulled
  - Load management interface for prioritizing subsystems
  - "Cut power to this section" command interface (boarding)
  - Section-by-section power status for target ships
- **Exercised By**: cold-habitat-survival, zero-g-wound, pirate-ambush, eva-rescue, colony-overseer, gravity-well-rescue, boarding-action, patrol-captain

### Reputation & Trust
- **Category**: Social
- **Maturity**: Refined
- **Purpose**: Tracks how factions, organizations, and individuals perceive the player and each other. Reputation is public (what people have heard), trust is personal (direct experience). Both affect access to opportunities, dialogue, pricing, willingness to cooperate, the player's credibility as mediator, investigator, or leader, and the wider political consequences of decisions. Information about whom the player associates with propagates through social and vouching networks. In espionage contexts, maintains the delicate balance of dual allegiances.
- **Key State Variables**:
  - `reputation`: map (faction/entity → float) — Public standing with each group
  - `trust`: map (individual → float) — Personal trust from direct interactions
  - `interaction_history`: list — Log of significant actions and their witnesses
  - `promises`: list — Commitments made, with kept/broken status
  - `public_perception`: float — Aggregate reputation across all factions
  - `known_associations`: list — Who the player has been seen with
  - `heat_level`: float — How much unwanted attention the player is drawing
  - `perceived_fairness`: float — How fair the player's decisions appear
  - `vouching_chain`: list — Who introduced the player to whom
  - `exposure_risk_score`: float — Probability of dual role being discovered
  - `professional_reputation`: float — Standing in professional networks (smuggling, contracting, etc.)
  - `external_reputation`: float — How entities beyond the immediate scenario perceive the player
- **Player-Facing Effects**:
  - Reputation summary screen
  - NPC dialogue tone shifting based on reputation
  - Access granted/denied to locations, services, opportunities
  - Price modifiers (trusted customers get better deals)
  - NPCs refusing to talk because player was seen with the wrong people
  - Doors opening because someone vouched for the player
  - Increasing surveillance as heat rises
  - Consequences of broken promises surfacing later
  - Public opinion indicators in political scenarios
  - Vendors hiding best merchandise until trust is built
  - Dual-allegiance tension indicators in espionage scenarios
  - External trade partner sentiment
- **Exercised By**: spaceport-crew-hiring, ice-miner-blockade, station-noir, colony-food-crisis, port-surveillance, double-dealing, smuggling-run, labor-strike, refugee-flotilla, black-market-bazaar

### Rotational Gravity
- **Category**: Physical
- **Maturity**: Developing
- **Purpose**: Simulates centripetal artificial gravity via rotating habitat sections or spin drums. Covers spin-up/spin-down dynamics, effective gravity at different radii, Coriolis effects, structural stress from rotation, and the critical role of rotation in EVA docking approach geometry.
- **Key State Variables**:
  - `spin_rate`: float (RPM) — Current rotation speed
  - `effective_gravity`: float (g) — Gravity felt at habitat floor radius
  - `rotation_period`: float (seconds) — Time for one full rotation
  - `spin_up_time`: float (seconds) — Time to reach target RPM
  - `structural_stress`: float — Rotational stress on structure
  - `coriolis_magnitude`: float — Strength of Coriolis effect at current spin
  - `balance`: float (0-1) — Mass distribution balance (wobble risk)
  - `docking_approach_geometry`: data — Airlock position as a function of rotation phase
- **Player-Facing Effects**:
  - Gradual weight return during spin-up
  - Coriolis effects on thrown/moving objects at partial spin
  - Objects settling and fluids pooling as gravity increases
  - Structural creaking at high RPM
  - Zero-g ↔ gravity transition effects
  - Visible station rotation through visor during EVA
  - Timing cues for docking window approach
- **Exercised By**: zero-g-wound, eva-rescue

### Security & Threat
- **Category**: Political
- **Maturity**: Refined
- **Purpose**: Simulates armed forces, threat assessment, rules of engagement, escalation dynamics, civil unrest, checkpoint operations, boarding operations, internal security investigations, arbiter justice systems, and the loyalty splits within security forces. Covers station security patrols, customs cutters, military vessels, pirate threats, riot control, and the escalation ladder from posturing through warning to lethal engagement. Security forces may be compromised, sympathetic to different factions, overwhelmed by competing demands, or operating under dual authority (internal arbiters vs. external law enforcement).
- **Key State Variables**:
  - `force_disposition`: map (unit → position/status) — Where security forces are
  - `officer_roster`: list — Individual security personnel with loyalty flags
  - `loyalty_split`: map (faction → float) — How security loyalties divide
  - `rules_of_engagement`: enum (hold/warn/engage) — Current ROE
  - `escalation_level`: int (0-5) — How close to violence
  - `weapons_status`: map (unit → enum) — Armed/unarmed/weapons-hot
  - `threat_assessment`: map (entity → level) — Perceived threat from each entity
  - `alert_level`: enum — Station/fleet/checkpoint alert status
  - `patrol_routes`: list — Security patrol patterns and schedules
  - `crime_rate`: float — Current crime level
  - `riot_probability`: float — How likely civil unrest is
  - `evidence_locker`: list — Seized evidence
  - `informant_network`: list — Intelligence sources
  - `checkpoint_posture`: enum (routine/enhanced/lockdown) — Inspection intensity
  - `raid_probability`: float (0-1) — Probability of enforcement raid
  - `boarding_team_readiness`: float — Tactical team availability
  - `suspect_behavior_flags`: list — Behavioral indicators triggering escalation
  - `arbiter_authority`: data — Internal justice system rules (for lawless zones)
- **Player-Facing Effects**:
  - Threat warnings and weapon lock alerts
  - Security hails demanding identification or compliance
  - Escalation status visible in NPC behavior and comms
  - Patrol patterns visible on sensors or observable on station
  - Security officers who help or hinder depending on loyalty
  - Interrogation scenes
  - Riot warnings and curfew notifications
  - Evidence being tampered with or disappearing
  - Consequences of violating rules of engagement
  - Checkpoint alert level display
  - Suspicion meter reflecting how customs perceives the player
  - Raid probability tension building through NPC behavior
  - Arbiter justice resolution in lawless zones
- **Exercised By**: ice-miner-blockade, pirate-ambush, station-noir, colony-food-crisis, port-surveillance, boarding-action, double-dealing, smuggling-run, refugee-flotilla, patrol-captain, black-market-bazaar

### Sensors & Scanning
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates detection, identification, and tracking of objects, ships, hazards, personnel, and conditions at all scales. Covers ship-scale sensors (active/passive radar, thermal, gravimetric, cargo-penetrating), personal-scale (suit sensors, biometric telemetry, ground-penetrating radar), hull-penetrating scans during boarding operations, and customs scanning capabilities. Sensor quality directly affects threat assessment, navigation safety, rescue operations, contraband detection, and terrain hazard identification. Includes the cat-and-mouse dynamics between scanning and evasion.
- **Key State Variables**:
  - `sensor_mode`: enum (active/passive) — Current operating mode
  - `detection_range`: float (km) — Effective sensor range
  - `resolution`: float — Detail level of sensor returns
  - `contact_list`: list — Detected objects with bearing, range, velocity, IFF
  - `radar_cross_section`: map (target → float) — How visible each target is
  - `ecm_active`: bool — Electronic countermeasures running
  - `eccm_active`: bool — Counter-countermeasures running
  - `false_contacts`: int — Spurious returns from interference or spoofing
  - `stealth_detection_threshold`: float — Minimum signature to detect stealthy contacts
  - `power_draw`: float — Energy consumed by sensors
  - `biometric_telemetry`: data — Suit-to-suit health data link
  - `scan_cycle_time`: float — How often sensor picture updates
  - `scan_types_available`: list — Thermal, gravimetric, active radar, cargo-penetrating
  - `hull_penetrating_resolution`: float — Through-hull detection capability
  - `ground_penetrating_radar`: data — Subsurface void detection (surface scenarios)
  - `operator_fatigue_effect`: float — Detection quality degradation from tired operators
  - `environmental_interference`: float — Signal degradation from dust, magnetosphere, etc.
- **Player-Facing Effects**:
  - Sensor board with contact markers and IFF tags
  - Target detail panel (mass, drive signature, weapons profile)
  - ECM/ECCM indicators
  - Detection warnings when scanned by hostiles
  - Hazard warnings (debris, radiation, subsurface voids)
  - Long-range scan results
  - Casualty vitals feed (intermittent if signal is poor)
  - "Something on sensors" ambiguous alerts
  - Scan type identification (knowing what they're looking for)
  - Through-hull heat signature overlay during boarding
  - Terrain scan overlay showing void risk zones
  - Scan quality warnings when operator is fatigued or dust is heavy
- **Exercised By**: deep-space-transit, pirate-ambush, eva-rescue, gravity-well-rescue, port-surveillance, boarding-action, smuggling-run, surface-expedition, patrol-captain

### Ship Crewing
- **Category**: Social
- **Maturity**: Refined
- **Purpose**: Simulates crew positions, role requirements, minimum competency thresholds, qualification tiers, shift scheduling, fatigue, and the cascading effects of understaffing on ship capability. Bridges NPC simulation and ship capability — an unfilled role or exhausted crew member degrades the systems they operate. Understaffing forces overtime, overtime increases fatigue, fatigue degrades performance — the core constraint of long-duration ship operations.
- **Key State Variables**:
  - `required_positions`: list (role) — Crew slots the ship needs filled
  - `crew_manifest`: map (role → NPC ref) — Who's in each position
  - `min_skill_threshold`: map (role → float) — Minimum competency for each role
  - `shift_schedule`: map (NPC → schedule) — Work/rest rotation
  - `hours_worked`: map (NPC → float) — Current shift duration
  - `fatigue_level`: map (NPC → float) — Per-crew exhaustion
  - `crew_efficiency`: float (0-1) — Aggregate crew performance modifier
  - `compatibility_matrix`: map (NPC pair → float) — How well crew members work together
  - `vacancy_penalties`: map (role → effect) — What breaks when a role is unfilled
  - `double_duty_assignments`: list — Crew covering multiple roles
  - `minimum_safe_manning`: map (watch → int) — Fewest people for safe operation per watch
  - `cross_training_status`: map (NPC → list) — Secondary qualifications
  - `watch_rotation_count`: int — Number of watches running (typically 3)
  - `consecutive_days_without_rest`: map (NPC → int) — Extended duty tracking
- **Player-Facing Effects**:
  - Crew roster interface showing filled/vacant positions
  - Shift calendar and scheduling controls
  - Ship capability ratings changing with crew quality
  - Vacancy warnings (e.g., "No engineer — repair capability disabled")
  - Fatigue warnings and overtime notifications
  - Crew compatibility events (arguments, cooperation bonuses)
  - Performance degradation indicators
  - Watch bill interface with gap warnings
  - Cross-training progress
  - "Ship capability" summary showing what you can/cannot do with current manning
- **Exercised By**: spaceport-crew-hiring, deep-space-transit, patrol-captain

### Social Dynamics
- **Category**: Social
- **Maturity**: Refined
- **Purpose**: Simulates interpersonal relationships, tensions, group morale, mob psychology, community cohesion, and the informal social ecosystem. Covers personality compatibility, grudges, alliances, cabin fever, rumor propagation, emergence of group culture, xenophobia, solidarity, protest formation, gossip networks, and the social cost of being seen in the wrong place at the wrong time. Operates at scales from a five-person crew to a four-thousand-person station with intersecting communities.
- **Key State Variables**:
  - `relationship_scores`: map (pair → float) — How each pair of people feel about each other
  - `tension_level`: float (0-1) — Overall group tension
  - `population_morale`: map (group → float) — Segmented morale by faction/group
  - `shared_history`: map (pair → list) — Events experienced together
  - `compatibility`: map (pair → float) — Personality-derived compatibility
  - `grievances`: list — Active interpersonal or group complaints
  - `alliances`: list (group) — Informal subgroups that have formed
  - `cabin_fever_index`: float — Confinement stress in enclosed spaces
  - `rumor_propagation`: map (rumor → spread) — How information/misinformation travels
  - `mob_formation_threshold`: float — How close to collective action
  - `altruism_index`: float (0-1) — Community cooperation vs. selfishness
  - `xenophobia_index`: float (0-1) — Hostility toward outsiders
  - `solidarity_movements`: list — Active collective support actions
  - `social_gathering_locations`: list — Where people congregate and gossip flows
  - `hate_incident_tracking`: list — Recorded hostile acts between groups
- **Player-Facing Effects**:
  - Crew arguments and visible friction
  - Alliances forming (NPCs backing each other up)
  - Morale impacts from interpersonal dynamics
  - NPCs refusing to work with specific others
  - Loyalty events (standing up for or betraying crewmates)
  - Crowd behavior and mob dynamics in larger populations
  - Rumor mill spreading player actions
  - Visible signs of social breakdown or solidarity
  - Community gathering events
  - Gossip that reaches the wrong ears
  - Social events where the player must navigate contradictory relationships
  - Graffiti, vandalism, protests, counter-protests
  - The danger of being seen in the wrong place at the wrong time
- **Exercised By**: spaceport-crew-hiring, deep-space-transit, colony-food-crisis, colony-overseer, double-dealing, labor-strike, refugee-flotilla, patrol-captain, black-market-bazaar

### Station Administration
- **Category**: Political
- **Maturity**: Refined
- **Purpose**: Simulates station or colony governance — leadership priorities, competence, budget constraints, corruption, policy decisions, legitimacy, and the limits of bureaucratic control. Administration can be overwhelmed, compromised, authoritarian, or absent. Covers emergency powers, martial law, cover-ups, the erosion of legitimacy under crisis, council factions, deadlock, and the station's own interests in outcomes that affect its neutral status or economic future.
- **Key State Variables**:
  - `leadership`: list (NPC refs) — Station administrators with competence ratings
  - `treasury`: float — Operating budget
  - `policies`: list — Active regulations and their enforcement level
  - `corruption_level`: float (0-1) — How corrupt the administration is
  - `complicity`: map (activity → bool) — Whether admin is complicit in specific crimes
  - `security_forces`: int — Number and capability of station security
  - `public_sentiment`: float (-1 to 1) — How the population feels about leadership
  - `legitimacy`: float (0-1) — Perceived right to govern
  - `emergency_powers`: bool — Whether emergency authority has been invoked
  - `docking_queue`: list — Ships waiting to dock, priority order
  - `pressure_threshold`: float — How much external pressure before admin caves
  - `chain_of_command`: list — Succession if leadership is removed
  - `council_composition`: map (faction → seats) — Voting alignment
  - `neutrality_policy`: enum — Station's stance on external conflicts
  - `economic_interest_in_outcome`: float — How much station governance is affected by events
- **Player-Facing Effects**:
  - Admin communications and policy announcements
  - Bureaucratic delays and access denials
  - Docking permission grants/denials
  - Security posture changes visible in NPC behavior
  - Official statements that contradict evidence
  - Bribery opportunities at corrupt stations
  - Public unrest events when sentiment drops
  - Legitimacy erosion indicators
  - Opportunities to influence or replace leadership
  - Council session broadcasts and voting
  - Emergency power declarations
  - Policy change consequences
- **Exercised By**: ice-miner-blockade, station-noir, colony-food-crisis, colony-overseer, double-dealing, labor-strike, refugee-flotilla

### Station Services & Infrastructure
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates the physical station as a place with areas, facilities, services, access controls, surveillance, and infrastructure. Covers repair bays, fuel depots, markets, medical facilities, bars, labor offices, docking bays, and also the hidden geography — maintenance crawlspaces, decommissioned sections, ventilation networks, converted mining tunnels — that can be leveraged or exploited. Infrastructure capacity determines whether a station can absorb population changes.
- **Key State Variables**:
  - `station_layout`: data — Rings, sectors, levels, areas, tunnel networks
  - `available_services`: map (service → status) — What's open and operational
  - `service_quality`: map (service → float 0-1) — How good each service is
  - `service_cost`: map (service → float) — Pricing for each service
  - `access_permissions`: map (area → requirements) — Who can go where
  - `surveillance_coverage`: map (area → float) — Camera/sensor coverage
  - `congestion`: float (0-1) — How busy/overloaded the station is
  - `black_market`: bool — Whether informal/illegal services exist
  - `black_market_access_points`: list — Where to find them
  - `maintenance_schedules`: list — When infrastructure work happens
  - `hidden_areas`: list — Crawlspaces, decommissioned sections, ventilation routes
  - `operating_hours`: map (service → schedule) — When services are available
  - `housing_capacity`: int — Maximum population with current infrastructure
  - `sanitation_load`: float (0-1) — Waste processing capacity usage
  - `power_distribution_capacity`: float — Infrastructure power limit
  - `crowd_density`: map (area → float) — People per area affecting movement
  - `docking_bay_capacity`: int — Total berths available
- **Player-Facing Effects**:
  - Station directory with service listings
  - Quality variation visible in environment (clean vs. run-down)
  - Locked doors and access terminals
  - Surveillance cameras to avoid or disable
  - Maintenance crawlspaces as alternate routes
  - Queue times for popular services
  - Black market accessible through specific NPCs/locations
  - Decommissioned sections where illegal activity hides
  - Service disruptions during crises
  - Infrastructure breakdowns creating opportunities or dangers
  - Crowd density affecting line-of-sight during tailing
  - Thin walls and ventilation grilles enabling eavesdropping
  - Docking bay traffic signaling arrivals vs. evacuations
- **Exercised By**: spaceport-crew-hiring, station-noir, port-surveillance, refugee-flotilla, black-market-bazaar

### Stealth & Detection
- **Category**: Technical
- **Maturity**: Draft
- **Purpose**: Simulates signature management, thermal masking, drive suppression, hidden compartments, scanner evasion techniques, and the cat-and-mouse dynamics between concealment and detection. Covers a ship's ability to run dark, reduce signatures, spoof mass readings, and hide — the offensive counterpart to Sensors & Scanning's detection capabilities.
- **Key State Variables**:
  - `thermal_signature`: float — Current heat emission level
  - `drive_emission_profile`: enum (active/suppressed/cold) — Engine visibility
  - `gravimetric_reading_actual`: float — True mass
  - `gravimetric_reading_spoofed`: float — Falsified mass reading
  - `radar_cross_section`: float — Reflectivity to active scanning
  - `compartment_shielding_integrity`: float (0-1) — Hidden cargo scan resistance
  - `evasion_mode`: enum (passive_drift/active_spoofing/compartment_masking) — Current stealth approach
  - `detection_probability`: map (scan_type → float) — Chance of being found per scan method
  - `time_since_signature_spike`: float — How long since last detectable emission
  - `hull_coating_degradation`: float — Stealth coating condition
  - `em_leakage`: float — Electromagnetic emissions from shielded cargo
  - `spoofing_believability`: float (0-1) — How convincing active spoofing is
- **Player-Facing Effects**:
  - Signature profile display showing emissions across thermal, EM, and gravimetric bands
  - Detection risk meter fluctuating with system activity
  - Compartment shielding status
  - Drive suppression toggle with speed vs. stealth tradeoff
  - Alert when scanned with detection probability outcome
  - Spoofing system controls with power draw and believability rating
  - "Going dark" consequences for navigation and speed
- **Exercised By**: smuggling-run

### Surface Environment
- **Category**: Physical
- **Maturity**: Developing
- **Purpose**: Simulates the conditions on a planetary or lunar surface as an active antagonist — electrostatic dust, radiation belts, temperature extremes, low gravity, subsurface geological hazards, atmospheric composition (if any), daylight/darkness cycles, and thermal cycling. Determines EVA windows, work speed, equipment fouling rates, route viability, and the physical cost of surface operations. The environment defines what paths are survivable and how fast suits deteriorate.
- **Key State Variables**:
  - `dust_accumulation_rate`: float — Rate at which regolith coats equipment
  - `dust_density`: float — Airborne/suspended dust concentration
  - `dust_charge`: float — Electrostatic charge on dust particles
  - `surface_temperature`: float (°C) — Current exterior temperature
  - `temperature_cycling`: data — Diurnal thermal variation profile
  - `radiation_level`: float (mSv/hr) — Surface radiation exposure rate
  - `daylight_cycle`: schedule — Light/dark periods
  - `dust_storm_probability`: float (0-1) — Chance of dust event
  - `gravity_level`: float (g) — Surface gravity
  - `traverse_time`: map (location pair → minutes) — Travel time between sites
  - `atmosphere`: data — Surface atmospheric composition and pressure (if any)
  - `terrain_stability`: map (grid → float) — Subsurface void probability and load-bearing
  - `visibility`: float (m) — Horizon distance affected by dust
  - `seismic_activity`: float — Micro-tremor frequency
- **Player-Facing Effects**:
  - Surface conditions panel showing temperature, radiation, dust status
  - EVA window availability indicator
  - Dust accumulation forecast for solar panels
  - Radiation warnings for prolonged surface work
  - Traverse time estimates between outdoor sites
  - "Conditions safe for EVA" / "EVA not recommended" status
  - Dust storm alerts
  - Terrain stability overlay (color-coded confidence)
  - Visibility range shrinking during dust events
  - Ground-penetrating scan results when available
- **Exercised By**: colony-overseer, surface-expedition

### Task & Workforce Management
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates the assignment, scheduling, and tracking of work tasks across a workforce with limited personnel, varying skills, and competing priorities. The core management system — the player's primary interface for running operations at any scale. Proven across colony operations, marine fire team coordination, labor dispute triage, small expedition crew management, and patrol ship duty scheduling. Tracks task queues, worker assignments, skill matching, progress, opportunity costs, and the cascading effects of pulling workers from one task to address another.
- **Key State Variables**:
  - `task_queue`: list — Prioritized tasks with urgency, required skills, estimated duration, personnel count
  - `worker_pool`: list — Available personnel with current assignment, fatigue, skill certifications, interpersonal flags
  - `task_progress`: map (task → float 0-1) — Per-task completion percentage
  - `quality_modifier`: map (task → float) — Quality of work based on skill match
  - `task_dependencies`: graph — Tasks that must finish before others can start
  - `opportunity_cost`: map (task → list) — What's degrading while resources are allocated elsewhere
  - `shift_schedule`: data — Work/rest rotation for all personnel
  - `overtime_accumulated`: map (NPC → float hours) — Hours worked beyond normal shifts
  - `abandonment_penalty`: map (task → effect) — Consequences of pulling workers mid-task
  - `coverage_gaps`: list — Unfilled positions and unstaffed departments
  - `task_conflict_matrix`: map — Tasks competing for the same qualified personnel
  - `reserve_pool`: list — Uncommitted personnel available for redeployment
- **Player-Facing Effects**:
  - Task board interface showing all active/pending tasks with urgency color coding
  - Drag-and-drop crew assignment with skill-match indicators
  - Estimated completion times updating based on who's assigned
  - Warning flags when unqualified personnel are assigned
  - Degradation alerts for unattended tasks
  - Shift schedule overview with overtime warnings
  - "What happens if I delay this" projection tooltips
  - Opportunity cost tracker
  - Task abandonment warnings when reassigning mid-work
  - Coverage gap warnings when critical stations are unmanned
  - Fire team positions on deck plan overlay (boarding)
  - Reserve pool status
  - "Cost of this assignment" projections showing what gets neglected
- **Exercised By**: colony-overseer, boarding-action, labor-strike, surface-expedition, patrol-captain

### Thermal Regulation
- **Category**: Physical
- **Maturity**: Refined
- **Purpose**: Simulates heat generation, retention, transfer, and loss within enclosed spaces and around massive bodies. Covers heaters, radiators, insulation, thermal bleed to vacuum, tidal heating, magnetospheric radiation heating, atmospheric friction, and the thermal consequences of power loss. In gravity-well scenarios, heat buildup from the environment becomes an active antagonist alongside the structural and navigational threats.
- **Key State Variables**:
  - `ambient_temperature`: map (compartment → float °C) — Temperature per area
  - `insulation_integrity`: map (section → float 0-1) — How well walls retain heat
  - `heat_source_output`: map (source → float W) — Active heat generation
  - `thermal_bleed_rate`: float (W) — Heat loss to exterior/vacuum
  - `radiator_status`: enum (online/offline/damaged) — Heat dissipation system state
  - `thermal_mass`: float — How quickly temperature changes
  - `tidal_heating_rate`: float (W) — Heat from gravitational flexing
  - `radiator_efficiency`: float (0-1) — Degraded by radiation environment
  - `atmospheric_friction_heating`: float (W) — Heat from aerobraking contact
  - `coolant_loop_status`: enum — Coolant circulation state
  - `thermal_capacity_remaining`: float — Margin before material failure
- **Player-Facing Effects**:
  - Visible breath fog in cold compartments
  - Frost forming on surfaces
  - Numbness and hypothermia effects on player
  - Thermostat/temperature displays on panels
  - Heat shimmer in overheated areas
  - Compartment heat map
  - Radiator status and efficiency readout
  - Thermal warnings escalating as orbit decays
  - Glowing hull sections at extreme temperatures
- **Exercised By**: cold-habitat-survival, colony-overseer, gravity-well-rescue

### Time Pressure
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates deadlines, ticking costs, countdowns, and the passage of time as a strategic resource. Creates urgency through accumulating fees, depleting supplies, expiring opportunities, NPC patience limits, faction ultimatums, resupply countdowns, converging deadlines, and the compounding risk of maintaining deceptions over time. Operates as a meta-system that adds tension to other systems.
- **Key State Variables**:
  - `current_datetime`: datetime — Simulation clock
  - `active_deadlines`: list — Events with expiration times
  - `cost_accumulation`: map (fee → float/hr) — Costs ticking up over time
  - `supply_depletion_dates`: map (resource → datetime) — When consumables run out
  - `opportunity_windows`: map (opportunity → time_remaining) — Expiring chances
  - `npc_patience`: map (NPC → float) — How long NPCs will wait
  - `faction_ultimatums`: map (faction → deadline) — When factions act unilaterally
  - `resupply_countdown`: float (days) — Time until external help arrives
  - `schedule_slippage`: float — How far behind plan the player is
  - `exposure_probability_curve`: float — Risk that increases with time (espionage)
  - `escape_windows`: list — Departure opportunities that close over time
  - `consumable_countdowns`: map (resource → hours) — Per-person supply timers
  - `point_of_no_return`: map (action → datetime) — When decisions become forced
- **Player-Facing Effects**:
  - Clock/calendar display
  - Mission day counter on long transits
  - Fee accumulation warnings
  - Supply countdown timers
  - "Time remaining" indicators on opportunities
  - NPCs leaving or changing behavior after waiting too long
  - Resupply ETA display
  - Faction ultimatum deadlines
  - Contract deadline indicators
  - Daily situation briefings in crisis scenarios
  - Multiple simultaneous countdown timers
  - Narrowing escape windows
  - "Hours until decision is forced" indicators
- **Exercised By**: spaceport-crew-hiring, ice-miner-blockade, deep-space-transit, colony-food-crisis, colony-overseer, gravity-well-rescue, double-dealing, labor-strike, surface-expedition, refugee-flotilla, patrol-captain

---

## Dependency Map

### Hard Dependencies
- Atmosphere Management --> Equipment & Repair: recyclers and scrubbers are mechanical systems that degrade and require maintenance
- Atmosphere Management --> Habitat Integrity: atmosphere cannot be maintained if hull is breached
- Atmosphere Management --> Power Grid: recyclers and scrubbers require electrical power
- Atmosphere Management --> Task & Workforce Management: life support maintenance requires assigned and available crews
- Attitude Control --> Power Grid: reaction control thrusters and gyroscopes require power
- Cargo & Trade --> Economy & Currency: all trade requires a functioning price and payment system
- Combat & Weapons --> Attitude Control: weapon firing arcs require correct ship facing
- Combat & Weapons --> Habitat Integrity: weapons fire and breaching charges damage pressurized structure
- Combat & Weapons --> Power Grid: weapons require power to charge, fire, and maintain locks
- Combat & Weapons --> Sensors & Scanning: targeting solutions require sensor data
- Combat & Weapons --> Task & Workforce Management: engagements depend on team assignments and assault plan
- Communications --> Power Grid: antenna and transmitter require power
- Communications --> Station Services & Infrastructure: communication systems are physical infrastructure
- Diplomacy & Negotiation --> Faction System: negotiations occur between factions with defined interests
- EVA & Spacewalk --> Navigation & Fuel: intercept and return trajectories require thrust
- EVA & Spacewalk --> Power Grid: airlock cycle requires station power
- EVA & Spacewalk --> Surface Environment: suit consumable burn rates driven by surface conditions (where applicable)
- Fleet & Ship Movement --> Navigation & Fuel: all maneuvers consume fuel and follow trajectory mechanics
- Fluid Dynamics --> EVA & Spacewalk: fluid behavior in/around suits governed by micro-g EVA environment
- Fluid Dynamics --> Rotational Gravity: fluid behavior determined by current gravity level
- Food & Water Supply --> Equipment & Repair: water recycler and food storage require functioning hardware
- Food & Water Supply --> Power Grid: greenhouses need powered lighting/climate; water rigs need powered pumps
- Food & Water Supply --> Station Administration: distribution policies set and enforced by governance
- Habitat Integrity --> Combat & Weapons: every breach, grenade, and hull-penetrating round creates structural damage
- Inventory & Personal Equipment --> Cargo & Trade: personal inventory is a subset of the broader cargo system
- Labor Market --> NPC Identity & Personality: candidates must exist as simulated NPCs
- Law & Jurisdiction --> Sensors & Scanning: legal authority to inspect requires sensor evidence establishing probable cause
- Law & Jurisdiction --> Station Administration: legal authority flows from governance charter
- Navigation & Fuel --> Equipment & Repair: escape requires a functioning drive (gravity-well scenarios)
- Navigation & Fuel --> Rotational Gravity: docking trajectories must account for station spin
- Navigation & Fuel --> Sensors & Scanning: route planning requires terrain scan data (surface scenarios)
- Navigation & Fuel --> Ship Crewing: course corrections and burns require a qualified pilot
- Power Grid --> Surface Environment: solar panel output depends on dust accumulation and daylight cycle
- Rotational Gravity --> Attitude Control: spin-up requires thruster compensation
- Rotational Gravity --> Power Grid: spin motor requires electrical power
- Security & Threat --> Law & Jurisdiction: ROE, detention authority, evidentiary standards defined by legal framework
- Security & Threat --> Station Administration: security operates under administrative authority
- Security & Threat --> Station Services & Infrastructure: security forces operate within physical infrastructure
- Ship Crewing --> NPC Identity & Personality: crew members are persistent NPCs
- Social Dynamics --> NPC Identity & Personality: interpersonal simulation requires personality data
- Station Administration --> Economy & Currency: governance constrained by budget
- Station Administration --> Security & Threat: governance requires enforcement capability
- Task & Workforce Management --> NPC Identity & Personality: task assignments require worker skills, certifications, fatigue, and interpersonal constraints
- Thermal Regulation --> Power Grid: heaters and radiators require electrical power

### Soft Dependencies
- Cargo & Trade ~~> Fleet & Ship Movement: blockades and fleet actions disrupt trade
- Cargo & Trade ~~> Inventory & Personal Equipment: what the player carries personally vs. stores on ship affects trade
- Cargo & Trade ~~> Law & Jurisdiction: item legality classification determines risk profile and price
- Cargo & Trade ~~> Navigation & Fuel: trade requires transport, which consumes fuel
- Communications ~~> Equipment & Repair: damaged comm arrays reduce range and clarity
- Communications ~~> Faction System: factions use comms for coordination and propaganda
- Communications ~~> Habitat Integrity: hull damage creates comms dead zones
- Communications ~~> Rotational Gravity: station rotation creates periodic line-of-sight dropout
- Communications ~~> Social Dynamics: rumor propagation speed depends on collective mood
- Communications ~~> Stealth & Detection: transmitting risks breaking stealth
- Economy & Currency ~~> Food & Water Supply: food scarcity drives price inflation and black market emergence
- Economy & Currency ~~> Security & Threat: prices spike and crash as raid threat fluctuates
- Economy & Currency ~~> Station Services & Infrastructure: black market operates within station infrastructure
- Equipment & Repair ~~> NPC Identity & Personality: repair quality depends on skill match of assigned worker
- Equipment & Repair ~~> Player Health: fatigued or injured player repairs more slowly
- Equipment & Repair ~~> Power Grid: repair tools and diagnostics need power
- Equipment & Repair ~~> Task & Workforce Management: repairs compete with operational tasks for crew time
- EVA & Spacewalk ~~> Sensors & Scanning: crossing between ships requires sensor data on gap conditions
- Faction System ~~> Economy & Currency: faction grievances often have economic roots
- Faction System ~~> Food & Water Supply: hunger and distribution unfairness drive faction formation
- Faction System ~~> Reputation & Trust: trust between factions affects negotiation willingness
- Faction System ~~> Social Dynamics: solidarity and scab stigma shape faction cohesion
- Fleet & Ship Movement ~~> Habitat Integrity: docking jury-rigged ships risks structural damage
- Fleet & Ship Movement ~~> Sensors & Scanning: tracking formations depends on sensor contact quality
- Fleet & Ship Movement ~~> Time Pressure: flotilla approach timeline drives decisions
- Food & Water Supply ~~> Thermal Regulation: greenhouse crops are temperature-sensitive
- Habitat Integrity ~~> Rotational Gravity: excessive spin stresses structure
- Habitat Integrity ~~> Thermal Regulation: unmanaged thermal expansion accelerates structural stress
- Inventory & Personal Equipment ~~> Reputation & Trust: visible loadout directly affects NPC perception
- Labor Market ~~> Economy & Currency: local conditions affect candidate availability and wages
- Labor Market ~~> Faction System: union organizing is collective political action driven by faction cohesion
- Labor Market ~~> Law & Jurisdiction: labor rights and contract law determine legal tactics
- Labor Market ~~> Reputation & Trust: player reputation affects candidate willingness
- Law & Jurisdiction ~~> Communications: legal filings and evidence transmission require comms
- Law & Jurisdiction ~~> Economy & Currency: blockade legality is economic; financial evidence can challenge it
- Law & Jurisdiction ~~> Reputation & Trust: credibility with legal bodies depends on reputation and prior record
- Law & Jurisdiction ~~> Station Administration: administrative authority determines which legal frameworks are invoked
- Medical & Injury ~~> Attitude Control: treating wounds during high-g maneuvers is extremely difficult
- Medical & Injury ~~> Equipment & Repair: medical equipment can be damaged and need repair
- Medical & Injury ~~> EVA & Spacewalk: treatment options severely limited while in pressurized suit
- Medical & Injury ~~> Fluid Dynamics: blood behavior in micro-gravity affects treatment
- Medical & Injury ~~> Rotational Gravity: treatment effectiveness varies with gravity level
- Medical & Injury ~~> Surface Environment: dust contamination increases infection risk
- Medical & Injury ~~> Task & Workforce Management: medical officer time split between crew health and other duties
- Navigation & Fuel ~~> Attitude Control: any burn requires correct orientation
- Navigation & Fuel ~~> Sensors & Scanning: orbital parameter accuracy depends on sensor quality
- Navigation & Fuel ~~> Time Pressure: diversions consume fuel and compress margins
- NPC Identity & Personality ~~> Atmosphere Management: poor air degrades NPC morale and sleep
- NPC Identity & Personality ~~> Food & Water Supply: hunger modifies NPC behavior, loyalty, and desperation
- NPC Identity & Personality ~~> Medical & Injury: health status modifies NPC behavior and desperation
- NPC Identity & Personality ~~> Player Health: crew morale erodes when they see the leader deteriorating
- NPC Identity & Personality ~~> Reputation & Trust: NPC willingness to talk gated by trust and perceived risk
- NPC Identity & Personality ~~> Security & Threat: NPC fear rises with security alert level
- NPC Identity & Personality ~~> Station Services & Infrastructure: NPC behavior influenced by local conditions
- NPC Identity & Personality ~~> Task & Workforce Management: fatigue and morale shift based on assignment load
- Player Health ~~> Atmosphere Management: low O2 / high CO2 degrades health
- Player Health ~~> EVA & Spacewalk: suit consumable depletion degrades player condition
- Player Health ~~> Food & Water Supply: player nutrition and hydration affect condition
- Player Health ~~> Medical & Injury: untreated wounds degrade health
- Player Health ~~> Ship Crewing: player taking extra shifts increases fatigue
- Player Health ~~> Task & Workforce Management: player doing field work loses oversight capability
- Player Health ~~> Thermal Regulation: prolonged cold/heat causes hypo/hyperthermia
- Reputation & Trust ~~> Communications: what the player transmits affects how factions perceive them
- Reputation & Trust ~~> Social Dynamics: collective dynamics amplify or dampen reputation effects
- Security & Threat ~~> Communications: checkpoint coordination and pursuit orders travel through comms
- Security & Threat ~~> Diplomacy & Negotiation: escalation level affects security posture
- Security & Threat ~~> Faction System: security loyalties may split across factions
- Security & Threat ~~> Reputation & Trust: security response scales with player heat level
- Security & Threat ~~> Social Dynamics: civil unrest and mob formation drive escalation
- Security & Threat ~~> Time Pressure: approaching threats increase urgency
- Sensors & Scanning ~~> Communications: biometric telemetry relies on radio link quality
- Sensors & Scanning ~~> Power Grid: active sensors draw significant power
- Sensors & Scanning ~~> Ship Crewing: sensor quality degrades when operator is fatigued
- Sensors & Scanning ~~> Stealth & Detection: evasion techniques defined relative to detection capabilities
- Ship Crewing ~~> Social Dynamics: crew compatibility affects ship efficiency
- Ship Crewing ~~> Task & Workforce Management: overtime from task system feeds back into crewing quality
- Social Dynamics ~~> Atmosphere Management: poor air quality increases irritability and conflict
- Social Dynamics ~~> Food & Water Supply: meal quality and rationing affect morale
- Social Dynamics ~~> Medical & Injury: visible suffering shifts public sentiment
- Social Dynamics ~~> Ship Crewing: overwork and unfair shifts breed resentment
- Social Dynamics ~~> Task & Workforce Management: perceived unfairness in assignments degrades morale
- Station Administration ~~> Economy & Currency: corruption motivated and evidenced by financial flows
- Station Administration ~~> Social Dynamics: leadership legitimacy depends on population confidence
- Station Services & Infrastructure ~~> Station Administration: access permissions set by administration
- Stealth & Detection ~~> Economy & Currency: signature suppression hardware quality scales with investment
- Stealth & Detection ~~> Navigation & Fuel: running dark constrains speed and trajectory
- Stealth & Detection ~~> Sensors & Scanning: evasion defined relative to detection capabilities
- Task & Workforce Management ~~> Communications: lost comms means lost control over teams
- Task & Workforce Management ~~> Medical & Injury: casualties reduce available personnel
- Task & Workforce Management ~~> Sensors & Scanning: better data enables smarter assignments
- Task & Workforce Management ~~> Social Dynamics: interpersonal conflicts constrain crew pairing
- Task & Workforce Management ~~> Time Pressure: task priority driven by degradation timers
- Thermal Regulation ~~> Habitat Integrity: poor insulation increases thermal bleed
- Time Pressure ~~> Economy & Currency: costs accumulate over time
- Time Pressure ~~> Food & Water Supply: reserve depletion rate sets urgency
- Time Pressure ~~> Navigation & Fuel: course deviations extend transit and compress margins

### Feedback Loops
- Atmosphere Management <-> Equipment & Repair <-> Ship Crewing: Degrading air systems need repair; repair pulls crew from other duties; understaffed shifts mean other systems get less attention
- Cargo & Trade <-> Economy & Currency: Blockades disrupt trade, worsening economy; economic pressure creates smuggling opportunities
- Combat & Weapons <-> Equipment & Repair: Weapons fire generates wear; taking hits damages components; damaged weapons reduce effectiveness
- Combat & Weapons <-> Habitat Integrity <-> Security & Threat: Breaching and firefights damage structure; damage creates decompression; decompression funnels movement into predictable routes for ambush
- Communications <-> Stealth & Detection <-> NPC Identity & Personality: Contacting contacts requires breaking radio silence, which risks detection; detection raises alert, making contacts afraid to act; frightened contacts may refuse or betray
- Communications <-> Task & Workforce Management <-> NPC Identity & Personality: Lost comms means teams operate on last orders guided by individual personality; aggressive marines push forward, cautious ones hold; the plan degrades into individual decisions the player can't override
- Diplomacy & Negotiation <-> Faction System <-> Station Administration: Admin policies drive demands; negotiation outcomes reshape policy; faction pressure forces concessions
- Economy & Currency <-> Faction System <-> Station Administration: Economic failures create grievances; faction actions worsen economy; admin responses affect both
- Economy & Currency <-> Food & Water Supply <-> Social Dynamics: Scarcity drives prices up; high prices increase desperation; black markets emerge but deepen inequality
- Economy & Currency <-> Security & Threat: Rising raid threat drives panic selling and price volatility; price crashes incentivize risk-taking; risk-taking draws security attention
- Economy & Currency <-> Time Pressure: Costs accumulate over time; time pressure forces economic compromises
- Equipment & Repair <-> Time Pressure <-> Navigation & Fuel: Hours spent repairing aren't spent traveling; but a working vehicle covers ground faster; the gamble is whether the repair succeeds
- EVA & Spacewalk <-> Player Health: Longer EVA depletes consumables and accumulates fatigue; declining health slows movement, extending EVA further
- Food & Water Supply <-> Faction System <-> Security & Threat: Unequal distribution creates grievances; faction raids reduce supply; crackdowns restore order but deepen resentment
- Food & Water Supply <-> Social Dynamics <-> NPC Identity & Personality: Rationing breeds resentment; resentful crew may hoard or steal; discovered hoarding escalates tension
- Food & Water Supply <-> Thermal Regulation <-> Power Grid: Crops need stable temperature; temperature needs power; power is failing; crop loss threatens everything downstream
- Habitat Integrity <-> Thermal Regulation <-> Sensors & Scanning: Tidal forces and thermal stress degrade hull; compromised sections lose insulation; rising heat degrades sensor electronics; worse sensors mean less ability to identify at-risk sections
- Inventory & Personal Equipment <-> Reputation & Trust <-> Security & Threat: Visible equipment shapes perception; perception determines threat assessment by arbiters; arbiter attention changes what can be safely carried
- Labor Market <-> Faction System <-> Law & Jurisdiction: Labor conditions drive faction formation; factions push for legal recognition; legal rulings reshape permissible labor actions
- Medical & Injury <-> Social Dynamics <-> Faction System: Visible suffering shifts public opinion; successful treatment builds goodwill; medical overload affecting residents fuels resentment
- Navigation & Fuel <-> Attitude Control <-> Equipment & Repair: Without main drive, attitude thrusters become only thrust; using them for braking depletes orientation fuel; poor orientation makes burns inefficient
- Navigation & Fuel <-> EVA & Spacewalk: Aggressive intercept burns leave less fuel for return; cautious burns extend time outside, consuming suit consumables
- Navigation & Fuel <-> Fleet & Ship Movement <-> Combat & Weapons: Escape burns consume fuel; less fuel means fewer evasion options; staying in range consumes more fuel
- Navigation & Fuel <-> Time Pressure <-> Task & Workforce Management: Every diversion costs fuel and time; less fuel means fewer future diversions; diversions extend crew time on station, increasing fatigue
- NPC Identity & Personality <-> Reputation & Trust: Talking to NPCs changes trust; trust determines what's revealed; revealed information reshapes reputation with others
- Player Health <-> Equipment & Repair: Worse health means worse repairs; systems stay offline longer; prolonged exposure degrades health further
- Player Health <-> Medical & Injury: Declining health reduces treatment ability; untreated injury accelerates decline
- Player Health <-> Task & Workforce Management <-> Social Dynamics: Captain skipping sleep maintains oversight but visibly deteriorates; tired captain makes worse decisions; worse decisions erode trust; eroded trust means more pushback requiring more energy
- Power Grid <-> Equipment & Repair <-> Combat & Weapons: Reactor damage reduces power; less power means weaker weapons/sensors; weaker sensors mean more hits; more hits damage reactor
- Power Grid <-> Thermal Regulation <-> Atmosphere Management: All three compete for limited energy; restoring one reduces availability for others
- Reputation & Trust <-> Diplomacy & Negotiation <-> Communications: Player advice shapes negotiation positions; suspiciously accurate advice erodes trust; tightened comms security reduces intelligence access
- Reputation & Trust <-> Labor Market: Good reputation attracts better candidates; treating crew well builds reputation
- Reputation & Trust <-> NPC Identity & Personality <-> Economy & Currency: Reputation determines contact reliability; reliable contacts cost more but deliver; unreliable contacts fold under pressure exposing the player
- Reputation & Trust <-> Security & Threat: Drawing attention raises heat; high heat makes NPCs afraid to help; lack of allies forces riskier moves drawing more attention
- Rotational Gravity <-> Habitat Integrity: Spin creates gravity but stresses structure; structural limits constrain maximum spin
- Rotational Gravity <-> Navigation & Fuel: Station spin dictates approach windows; missing a window costs fuel and time
- Security & Threat <-> Diplomacy & Negotiation: Failed negotiations escalate threat; high threat makes negotiation harder but more urgent
- Security & Threat <-> Social Dynamics: Rising tension triggers security response; heavy-handed security deepens breakdown
- Sensors & Scanning <-> Security & Threat <-> Fleet & Ship Movement: Better data improves threat assessment; accurate threats inform evasion; evasion changes sensor geometry
- Sensors & Scanning <-> Security & Threat <-> Task & Workforce Management: Sensor data informs threat assessment; threat drives team assignments; team positions change sensor picture; fog of war lifts only where forces are committed
- Sensors & Scanning <-> Ship Crewing: Fatigued operator misses contacts or generates false positives; missed contacts mean undetected threats; false positives waste fuel on unnecessary intercepts
- Ship Crewing <-> Social Dynamics: Overworked crew become hostile; hostile crew perform worse; others pick up slack increasing everyone's load
- Social Dynamics <-> NPC Identity & Personality <-> Reputation & Trust: NPCs observe player movements and share observations; gossip reaches faction security; a single witnessed encounter can unravel careful positioning
- Station Administration <-> Faction System <-> Diplomacy & Negotiation: Council deadlock paralyzes governance; paralysis increases faction pressure; pressure forces snap decisions or emergency powers; emergency powers erode legitimacy
- Stealth & Detection <-> Sensors & Scanning <-> Security & Threat: Suppressing signature reduces detection probability; lower detection means less scrutiny; but scanning adapts to evasion — forcing constant adaptation
- Surface Environment <-> EVA & Spacewalk: Worsening dust accelerates filter clogging and seal wear; degraded suits force slower travel; slower travel extends exposure to worsening conditions
- Task & Workforce Management <-> Atmosphere Management <-> Time Pressure: Striking workers mean unmaintained life support; degrading atmosphere creates urgency; emergency maintenance requires workers to return, giving them leverage
- Task & Workforce Management <-> Combat & Weapons <-> Medical & Injury: Assault plan determines firefight locations; firefights produce casualties; casualties reduce marines; fewer marines means compressed plan with more danger per engagement
- Task & Workforce Management <-> NPC Identity & Personality <-> Social Dynamics: Overtime increases fatigue and lowers morale; low morale reduces work quality; lower quality means longer tasks means more overtime
- Task & Workforce Management <-> Ship Crewing <-> Social Dynamics: Understaffing forces overtime; overtime increases fatigue; fatigue degrades performance; degraded performance creates new urgent work; unfair assignments breed resentment; the staffing deficit makes everything harder
- Task & Workforce Management <-> Time Pressure <-> Equipment & Repair: Multiple systems degrade on independent timers; fixing one pauses its timer but others keep ticking; pulling workers mid-repair wastes progress
- Time Pressure <-> Faction System <-> Diplomacy & Negotiation: Shrinking reserves increase urgency; urgent factions make harder demands; failed negotiations waste time
- Time Pressure <-> Food & Water Supply <-> Player Health: Dwindling supplies force rationing; rationing degrades health; degraded crew works slower; slower work extends timelines
- Time Pressure <-> Reputation & Trust <-> Economy & Currency: Each passing cycle raises payout but compounds exposure risk; the player must decide whether next milestone is worth narrowing safety margin

---

## Analysis & Recommendations

### Under-Tested Systems
The following systems appear in only 1–2 scenarios:
- **Inventory & Personal Equipment** (1 scenario: black-market-bazaar) — Currently only covers personal loadout in a bazaar. Needs stress-testing in EVA (what you can carry in a suit), combat (weapon selection and ammo), and survival (what you grabbed when you evacuated) contexts.
- **Stealth & Detection** (1 scenario: smuggling-run) — Only exercised as a smuggler. Needs stress-testing from the detection side (playing a customs inspector or patrol captain who must find hidden ships) and in military/espionage contexts.
- **Combat & Weapons** (2 scenarios: pirate-ambush, boarding-action) — Needs a scenario with sustained ship-to-ship combat (fleet engagement) and another with ground/surface combat to prove the system works across scales.
- **Fluid Dynamics** (2 scenarios: zero-g-wound, eva-rescue) — Narrow application. May need a scenario with large-scale fluid management (propellant transfer, coolant breach in a station, flooding in a rotating habitat).
- **Rotational Gravity** (2 scenarios: zero-g-wound, eva-rescue) — Only tested in medical and rescue contexts. Needs a scenario where rotation management is the primary challenge (station spin-up, centrifuge failure, rotating habitat construction).

### Potential Missing Systems
Systems implied by the scenarios but not yet explicitly defined:
- **Orbital Mechanics / Astrodynamics** — Navigation & Fuel covers route planning, but the underlying orbital mechanics (transfer windows, gravity assists, orbital periods, planetary positions) that determine what routes are even possible are not modeled as a separate system. May be subsumed into Navigation & Fuel or warrant its own system at the solar-system scale.
- **AI & Automation** — No scenario has explored automated systems, drones, or AI crew substitutes — which would stress Ship Crewing, Task & Workforce Management, Equipment & Repair, and raise ethical/trust questions.
- **Terraforming / Environmental Engineering** — Colony-overseer mentions a terraforming colony, but no system models the long-term environmental transformation process (atmospheric processing, soil creation, biome establishment).
- **Morale & Psychology** — Currently distributed across Player Health (stress, decision fatigue), NPC Identity & Personality (morale, breaking point), and Social Dynamics (group tension). A dedicated psychological system might be warranted for scenarios focusing on long-duration isolation, PTSD, or institutional morale.
- **Salvage & Scavenging** — Multiple scenarios involve stripping components, recovering cargo, or scavenging from wrecks. Currently handled ad-hoc within Equipment & Repair and Cargo & Trade.

### Incomplete Dependency Chains
- **Medical & Injury → Inventory & Personal Equipment**: Treatment requires medical supplies tracked at the personal level — bandages, analgesics, stimulants — but Inventory is only exercised in one scenario
- **Stealth & Detection ↔ Sensors & Scanning**: These are explicitly two sides of the same coin, but Stealth is only tested from the evader's perspective. A patrol/customs scenario already exists (patrol-captain) but doesn't explicitly reference stealth systems
- **Combat & Weapons → Habitat Integrity**: This bidirectional dependency is now captured in boarding-action, but not yet tested in a ship-vs-ship engagement where hull damage from weapons fire is the primary structural concern
- **Task & Workforce Management ↔ Ship Crewing**: Both manage personnel assignment at different scales. Patrol-captain exercises both simultaneously — this bridge is established but could use further testing
- **Surface Environment → Equipment & Repair**: Dust fouling, thermal cycling, and radiation all degrade equipment on surfaces, but this cross-link could be more explicitly formalized

### Recommended Next Scenarios
To stress-test remaining gaps:

1. **Fleet engagement / convoy defense** — Commanding multiple ships in a sustained battle. Would stress: Combat & Weapons at fleet scale, Fleet & Ship Movement, Sensors & Scanning, Communications, Habitat Integrity (from weapons fire), Power Grid. Would promote Combat & Weapons to Refined.

2. **Derelict salvage operation** — Boarding an abandoned ship or station to recover valuable components. Would stress: Inventory & Personal Equipment (what to grab and carry), EVA & Spacewalk, Equipment & Repair, Sensors & Scanning, Stealth & Detection (avoiding automated defenses or other salvagers), Habitat Integrity. Would surface a **Salvage & Scavenging** system and stress-test Inventory.

3. **Rotating habitat emergency** — A centrifuge failure or spin anomaly threatening a populated habitat. Would stress: Rotational Gravity as primary challenge, Fluid Dynamics (behavior changes as gravity shifts), Habitat Integrity, Atmosphere Management, Medical & Injury, Social Dynamics. Would promote Rotational Gravity and Fluid Dynamics.

4. **Automated station malfunction** — A highly automated facility whose AI/drone systems begin failing or acting erratically. Would stress: AI & Automation (new system), Equipment & Repair, Power Grid, Security & Threat, Communications. Would surface the AI & Automation system.

5. **Customs inspector shift** — Playing from the enforcement side of smuggling-run. Would stress: Stealth & Detection (from detection perspective), Sensors & Scanning, Law & Jurisdiction, Cargo & Trade, NPC Identity & Personality, Security & Threat. Would promote Stealth & Detection and provide the mirror perspective.
