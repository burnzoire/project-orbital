# Simulation Systems Definition
> Last reviewed: 2026-04-10
> Scenarios analyzed: 10

## Systems Overview
| System | Category | Maturity | Scenario Coverage |
|--------|----------|----------|-------------------|
| Atmosphere Management | Physical | Refined | cold-habitat-survival, deep-space-transit, colony-overseer |
| Attitude Control | Technical | Developing | zero-g-wound, pirate-ambush |
| Cargo & Trade | Economic | Draft | ice-miner-blockade |
| Combat & Weapons | Technical | Draft | pirate-ambush |
| Communications | Technical | Refined | cold-habitat-survival, ice-miner-blockade, pirate-ambush, station-noir, eva-rescue |
| Diplomacy & Negotiation | Political | Developing | ice-miner-blockade, colony-food-crisis |
| Economy & Currency | Economic | Refined | spaceport-crew-hiring, ice-miner-blockade, station-noir, colony-food-crisis |
| Equipment & Repair | Technical | Refined | cold-habitat-survival, deep-space-transit, pirate-ambush, eva-rescue, colony-overseer |
| EVA & Spacewalk | Technical | Draft | eva-rescue |
| Faction System | Political | Developing | ice-miner-blockade, colony-food-crisis |
| Fleet & Ship Movement | Physical | Developing | ice-miner-blockade, pirate-ambush |
| Fluid Dynamics | Physical | Developing | zero-g-wound, eva-rescue |
| Food & Water Supply | Biological | Refined | deep-space-transit, colony-food-crisis, colony-overseer |
| Habitat Integrity | Physical | Refined | cold-habitat-survival, zero-g-wound, colony-overseer |
| Labor Market | Economic | Draft | spaceport-crew-hiring |
| Law & Jurisdiction | Political | Draft | station-noir |
| Medical & Injury | Biological | Refined | zero-g-wound, pirate-ambush, eva-rescue |
| Navigation & Fuel | Technical | Refined | ice-miner-blockade, deep-space-transit, pirate-ambush, eva-rescue |
| NPC Identity & Personality | Social | Refined | spaceport-crew-hiring, deep-space-transit, station-noir, colony-food-crisis, colony-overseer |
| Player Health | Biological | Refined | cold-habitat-survival, zero-g-wound, deep-space-transit, pirate-ambush, eva-rescue, colony-food-crisis, colony-overseer |
| Power Grid | Technical | Refined | cold-habitat-survival, zero-g-wound, pirate-ambush, eva-rescue, colony-overseer |
| Reputation & Trust | Social | Refined | spaceport-crew-hiring, ice-miner-blockade, station-noir, colony-food-crisis |
| Rotational Gravity | Physical | Developing | zero-g-wound, eva-rescue |
| Security & Threat | Political | Refined | ice-miner-blockade, pirate-ambush, station-noir, colony-food-crisis |
| Sensors & Scanning | Technical | Developing | deep-space-transit, pirate-ambush, eva-rescue |
| Ship Crewing | Social | Developing | spaceport-crew-hiring, deep-space-transit |
| Social Dynamics | Social | Refined | spaceport-crew-hiring, deep-space-transit, colony-food-crisis, colony-overseer |
| Station Administration | Political | Refined | ice-miner-blockade, station-noir, colony-food-crisis, colony-overseer |
| Station Services & Infrastructure | Technical | Developing | spaceport-crew-hiring, station-noir |
| Surface Environment | Physical | Draft | colony-overseer |
| Task & Workforce Management | Technical | Draft | colony-overseer |
| Thermal Regulation | Physical | Developing | cold-habitat-survival, colony-overseer |
| Time Pressure | Technical | Refined | spaceport-crew-hiring, ice-miner-blockade, deep-space-transit, colony-food-crisis, colony-overseer |

**Summary**: 33 systems — 7 Draft, 9 Developing, 17 Refined, 0 Final

---

## System Definitions

### Atmosphere Management
- **Category**: Physical
- **Maturity**: Refined
- **Purpose**: Simulates breathable air composition, recycling, scrubbing, and environmental quality within enclosed spaces. Covers O2/CO2 balance, pressure maintenance, humidity, trace contaminant buildup, leak management, and long-duration air quality degradation.
- **Key State Variables**:
  - `o2_level`: float (%) — Oxygen concentration per compartment
  - `co2_level`: float (ppm) — Carbon dioxide concentration (toxic above threshold)
  - `pressure`: float (kPa) — Total atmospheric pressure
  - `humidity`: float (%) — Relative humidity level
  - `trace_contaminants`: float — Accumulated volatile organic compounds, off-gassing
  - `recycler_status`: enum (online/offline/degraded) — Air recycler operational state
  - `scrubber_condition`: float (0-1) — CO2 scrubber filter remaining life
  - `air_quality_index`: float (0-1) — Composite air quality score
  - `leak_rate`: float (kPa/hr) — Rate of atmosphere loss through breaches
  - `odor_accumulation`: float — Long-duration staleness factor
- **Player-Facing Effects**:
  - Breathing difficulty at low O2 or high CO2
  - Drowsiness and cognitive impairment from CO2 buildup
  - Headaches from poor air quality on long transits
  - Audible hissing from pressure leaks
  - Stale air complaints from crew NPCs
  - Condensation on surfaces from humidity issues
  - Filter replacement maintenance prompts
- **Exercised By**: cold-habitat-survival, deep-space-transit, colony-overseer

### Attitude Control
- **Category**: Technical
- **Maturity**: Developing
- **Purpose**: Simulates orientation, rotation, and stabilization of vessels and habitats in space. Manages angular momentum, thruster compensation during spin changes, weapon alignment, and tumble recovery. Critical for both habitat spin-up sequences and combat maneuvering.
- **Key State Variables**:
  - `angular_momentum`: vec3 — Current rotational state
  - `ship_facing`: quaternion — Current orientation vs. travel vector
  - `rotation_rate`: float (deg/s) — Current rotation speed
  - `thruster_fuel`: float (kg) — Remaining reaction mass for attitude thrusters
  - `gyroscope_status`: enum (online/offline/degraded) — Gyroscope operational state
  - `compensation_load`: float — Current demand for stabilization thrust
  - `tumble_state`: bool — Whether vessel is in uncontrolled tumble
  - `gimbal_status`: enum — Thruster gimbal condition
  - `facing_lock`: bool — Whether orientation is locked for weapon alignment
- **Player-Facing Effects**:
  - Habitat drift or wobble felt/seen by player
  - Thruster firing sounds and vibrations
  - Fuel gauge warnings on HUD
  - Attitude indicator (navball) showing facing vs. velocity
  - Tumble recovery alerts
  - Rotation warnings during maneuvers
- **Exercised By**: zero-g-wound, pirate-ambush

### Cargo & Trade
- **Category**: Economic
- **Maturity**: Draft
- **Purpose**: Simulates goods being transported, their value over time, market dynamics, and trade route economics. Covers cargo condition, spoilage, contraband status, and demand fluctuation.
- **Key State Variables**:
  - `manifest`: list — Cargo items with type, quantity, and origin
  - `unit_value`: float — Current market value per unit, fluctuates with supply/demand
  - `depreciation_rate`: float (/hr) — Rate at which perishable cargo loses value
  - `demand_at_destination`: float — How badly the destination needs this cargo
  - `contraband_status`: bool — Whether goods are illegal at destination
  - `condition`: float (0-1) — Cargo physical condition (spoilage, damage)
- **Player-Facing Effects**:
  - Cargo hold inventory display
  - Value tracker showing depreciation in real time
  - Market price comparisons between stations
  - Spoilage/damage warnings
  - Contraband scan risk at stations
- **Exercised By**: ice-miner-blockade

### Combat & Weapons
- **Category**: Technical
- **Maturity**: Draft
- **Purpose**: Simulates offensive and defensive armaments, targeting, firing solutions, ammunition, weapon state, and damage output. Covers point-defense systems, turrets, missiles, and the heat/wear costs of sustained fire.
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
- **Player-Facing Effects**:
  - Targeting reticle and lock indicators
  - Weapon heat gauge
  - Ammo/charge counter
  - Firing arc overlay on nav display
  - Hit/miss feedback with visual and audio cues
  - Point-defense interception alerts
- **Exercised By**: pirate-ambush

### Communications
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates all forms of signal transmission and reception — distress calls, open broadcasts, private channels, encrypted messages, propaganda, electronic warfare, and information flow. Ranges from simple suit-to-suit radio to complex multi-party station communications with surveillance, interception, and jamming.
- **Key State Variables**:
  - `antenna_status`: enum (online/offline/damaged) — Physical antenna condition
  - `power_allocation`: float (W) — Power dedicated to comms
  - `signal_range`: float (km) — Effective broadcast/receive range
  - `channels`: list — Active channels (open/encrypted/military) with content
  - `encryption_level`: int — Security of private communications
  - `jamming_status`: bool — Whether signals are being jammed
  - `nearby_receivers`: list — Entities in range that can hear broadcasts
  - `spoofed_signals`: list — Fake transponder or distress signals active
  - `message_logs`: list — Recorded communications history
  - `line_of_sight`: bool — Whether direct signal path exists (affected by rotation, obstacles)
  - `rumor_propagation`: float — Rate at which information spreads through NPC network
- **Player-Facing Effects**:
  - Comms panel with open and private channel tabs
  - Static and signal degradation at range limits or during rotation dropout
  - Ability to broadcast, jam, intercept, or spoof
  - Distress beacon toggle
  - Intercepted messages as investigation clues
  - Anonymous tip capability
  - Suit radio with breathing audio in EVA
  - Response delay based on distance
- **Exercised By**: cold-habitat-survival, ice-miner-blockade, pirate-ambush, station-noir, eva-rescue

### Diplomacy & Negotiation
- **Category**: Political
- **Maturity**: Developing
- **Purpose**: Simulates multi-party negotiation between factions, groups, or individuals. Tracks demands, concessions, red lines, leverage, trust, and deal-making. The player can act as participant, mediator, or spoiler.
- **Key State Variables**:
  - `parties`: list — Entities involved in negotiation
  - `demands`: map (party → list) — What each party wants
  - `red_lines`: map (party → list) — Non-negotiable positions
  - `willingness`: map (party → float) — How open each party is to compromise
  - `trust_between`: map (pair → float) — Bilateral trust levels
  - `leverage`: map (party → list) — Resources or threats each party controls
  - `proposed_deals`: list — Terms on the table
  - `mediator_credibility`: float — Player's standing as a neutral broker
- **Player-Facing Effects**:
  - Negotiation dialogue with visible faction stances
  - Demand/offer proposal interface
  - Trust indicators shifting based on actions
  - Leverage assessment display
  - Deal acceptance/rejection with consequences
  - Faction ultimatum deadlines
- **Exercised By**: ice-miner-blockade, colony-food-crisis

### Economy & Currency
- **Category**: Economic
- **Maturity**: Refined
- **Purpose**: Simulates money flows, pricing, wages, debts, black markets, and economic pressure across the simulation. Covers personal finances, institutional budgets, commodity markets, and the financial evidence trails that link to corruption and crime. Economic conditions drive faction grievances, labor availability, black market emergence, and player urgency.
- **Key State Variables**:
  - `player_balance`: float — Player's available funds
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
- **Player-Facing Effects**:
  - Account balance display with transaction history
  - Price tags on goods and services
  - Wage negotiation during hiring
  - Fee timers showing accumulating costs
  - Black market contacts and inflated prices
  - Financial records as investigation evidence
  - Economic impact of policy decisions
  - Inflation warnings
- **Exercised By**: spaceport-crew-hiring, ice-miner-blockade, station-noir, colony-food-crisis

### Equipment & Repair
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates the state of mechanical and electrical components and the ability to maintain, repair, or jury-rig them. Covers tool requirements, spare parts, skill modifiers, bypass feasibility, cascading failure risk, and the severe dexterity penalties of working in EVA suits or under combat conditions.
- **Key State Variables**:
  - `component_health`: map (component → float 0-1) — Condition of each component
  - `wear_rate`: map (component → float/hr) — How fast components degrade under use
  - `required_parts`: map (repair → list) — Parts needed for each repair job
  - `spare_parts_inventory`: list — Available replacement parts
  - `available_tools`: list — Tools currently accessible
  - `bypass_feasibility`: map (system → bool) — Whether safety bypasses are possible
  - `repair_skill`: float — Competence modifier (player or assigned crew)
  - `repair_difficulty`: float — Environmental modifier (gloves, zero-g, combat, darkness)
  - `cascading_failure_risk`: map (component → float) — Probability of failure spreading
  - `maintenance_backlog`: list — Queued repairs with priority
  - `jury_rig_effectiveness`: float — How well improvised repairs hold
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
- **Exercised By**: cold-habitat-survival, deep-space-transit, pirate-ambush, eva-rescue, colony-overseer

### EVA & Spacewalk
- **Category**: Technical
- **Maturity**: Draft
- **Purpose**: Simulates extravehicular activity — suit integrity, consumable budgets (oxygen, battery, propellant, thermal), tether management, and the extreme physical toll of working in vacuum. EVA exertion is 3-5x habitat baseline, and every system interaction is penalized by gloves, restricted vision, and micro-gravity.
- **Key State Variables**:
  - `suit_o2_reserve`: float (minutes) — Remaining breathable oxygen
  - `suit_battery`: float (0-1) — Suit power level
  - `thruster_propellant`: float (kg) — Maneuvering fuel mass
  - `thermal_balance`: float — Heat state (sun exposure vs. shadow)
  - `suit_integrity`: float (0-1) — Seal and hull condition
  - `tether_status`: enum (attached/detached/broken) — Tether state
  - `visor_condition`: enum (clear/fogged/damaged) — Visibility state
  - `fatigue_rate_multiplier`: float — EVA exertion factor (3-5x normal)
  - `radiation_exposure`: float (mSv) — Accumulated dose outside shielding
- **Player-Facing Effects**:
  - HUD overlay with consumable gauges ticking down in real time
  - Fogging visor at high exertion
  - Glove dexterity penalties on all manual interactions
  - Audio limited to suit radio and own breathing
  - Tether tension/snap warnings
  - Radiation dosimeter ticking in unshielded zones
  - Movement is slow, deliberate, and exhausting
- **Exercised By**: eva-rescue

### Faction System
- **Category**: Political
- **Maturity**: Developing
- **Purpose**: Simulates organized groups with shared interests, hierarchies, resources, grievances, and agendas. Factions have internal cohesion that can fracture, relationships with other factions, and the ability to take collective action (blockades, strikes, raids, protests). Faction formation can be emergent — occupational groups, ethnic groups, or ad-hoc alliances forming under pressure.
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
- **Player-Facing Effects**:
  - Faction reputation display
  - Dialogue reflecting faction stance toward player
  - Access granted/denied based on faction relations
  - Faction actions visible in the world (blockades, patrols, strikes, raids)
  - Splinter events when cohesion drops
  - Faction formation visible as tensions rise
- **Exercised By**: ice-miner-blockade, colony-food-crisis

### Fleet & Ship Movement
- **Category**: Physical
- **Maturity**: Developing
- **Purpose**: Simulates positions, velocities, accelerations, and formation tactics of multiple ships in 3D space. Covers patrol routes, blockade formations, intercept trajectories, pursuit/evasion calculations, and the tactical geometry of multi-ship encounters.
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
- **Player-Facing Effects**:
  - Nav display with ship contacts and vector lines
  - Transponder IDs and formation patterns visible
  - Intercept countdown timers
  - Pursuit cone visualization
  - Relative velocity readouts
  - Formation overlay on tactical display
- **Exercised By**: ice-miner-blockade, pirate-ambush

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
- **Purpose**: Simulates production, storage, distribution, and consumption of food and water. Covers individual production sources (hydroponics, protein vats, greenhouses), total reserves as calorie/day countdowns, rationing, spoilage, contamination, nutritional quality, and the physiological and social effects of scarcity.
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
- **Player-Facing Effects**:
  - Food reserve countdown display
  - Pantry/stores inventory
  - Production status dashboards
  - Rationing controls and tier displays
  - Meal quality and variety indicators
  - Hunger indicators on NPCs
  - Spoilage and contamination alerts
  - Water reserves and recycler status
  - Crew complaints about food quality
  - Black market food price tracking
- **Exercised By**: deep-space-transit, colony-food-crisis, colony-overseer

### Habitat Integrity
- **Category**: Physical
- **Maturity**: Refined
- **Purpose**: Simulates the structural condition of habitats, stations, and ship hulls — including seals, compartments, radiation shielding, and stress tolerance. Covers both static damage (micrometeorites, debris) and dynamic stress (spin loads, impacts, emergency maneuvers).
- **Key State Variables**:
  - `hull_integrity`: map (section → float 0-1) — Structural health per section
  - `seal_status`: map (seal → enum) — Door, hatch, and viewport seal condition
  - `structural_stress`: map (section → float) — Current stress load vs. tolerance
  - `spin_rated_rpm`: float — Maximum safe rotation speed
  - `breach_status`: map (section → bool) — Active hull breaches
  - `radiation_shielding`: map (section → float) — Shielding effectiveness
- **Player-Facing Effects**:
  - Visible hull damage, frost on interior surfaces, cracks
  - Creaking/groaning sounds under structural stress
  - Breach alarms and compartment isolation prompts
  - Structural warnings during spin-up or maneuvers
  - Deformation visible at extreme stress
- **Exercised By**: cold-habitat-survival, zero-g-wound, colony-overseer

### Labor Market
- **Category**: Economic
- **Maturity**: Draft
- **Purpose**: Simulates the availability, quality, and cost of hireable personnel at a given location. Driven by local economic conditions, population demographics, and competing demand from other employers.
- **Key State Variables**:
  - `available_candidates`: list (NPC refs) — Pool of hireable NPCs at this location
  - `skill_distribution`: map (skill → distribution) — Statistical spread of skills
  - `wage_floor`: float — Minimum wage anyone will accept locally
  - `desperation_index`: float (0-1) — How desperate the local labor pool is
  - `unemployment_rate`: float — Fraction of population seeking work
  - `competing_demand`: int — How many other employers are hiring
- **Player-Facing Effects**:
  - Job board listings with varying quality
  - Bar/cantina conversations revealing available talent
  - Candidate availability changing over time
  - Competition from other captains visibly hiring
  - Desperation-driven candidates approaching the player
- **Exercised By**: spaceport-crew-hiring

### Law & Jurisdiction
- **Category**: Political
- **Maturity**: Draft
- **Purpose**: Simulates legal frameworks, jurisdictional boundaries, and enforcement mechanisms that govern stations, ships, and territories — and the gaps between them. Covers corporate charters, transit compacts, sovereign claims, evidentiary standards, warrants, extradition, and the ability to forum-shop between authorities with different motivations.
- **Key State Variables**:
  - `governing_authority`: enum — Legal basis (corporate charter, transit compact, sovereign claim)
  - `applicable_laws`: list — Laws in effect at current location
  - `jurisdictional_overlaps`: list — Areas where multiple authorities claim jurisdiction
  - `enforcement_bodies`: list — Local security, corporate compliance, transit court, guild arbitration
  - `evidentiary_standards`: map (body → enum) — What each authority considers proof
  - `active_warrants`: list — Warrants issued for/against entities
  - `legal_proceedings`: list — Active cases and their status
  - `corruption_index`: map (body → float) — How compromised each authority is
  - `extradition_agreements`: map (pair → bool) — Which authorities cooperate
  - `detention_authority`: map (body → enum) — Who can hold whom and for how long
- **Player-Facing Effects**:
  - Ability to file complaints or charges with different authorities
  - Jurisdictional conflicts that block or enable action
  - Legal threats from NPCs
  - Warrants issued for or against the player
  - Option to forum-shop for a sympathetic jurisdiction
  - Different evidentiary standards at different authorities
  - Extradition risks when moving between jurisdictions
- **Exercised By**: station-noir

### Medical & Injury
- **Category**: Biological
- **Maturity**: Refined
- **Purpose**: Simulates wound types, bleeding, infection, treatment options, and recovery. Treatment effectiveness varies dramatically with available equipment, gravity conditions, EVA suit constraints, and medical skill. Covers everything from minor cuts to combat trauma (shrapnel, burns, g-force injuries, decompression).
- **Key State Variables**:
  - `wound_location`: enum (body part) — Where the injury is
  - `wound_type`: enum (laceration/fracture/burn/shrapnel/g-force/decompression) — Injury classification
  - `severity`: float (0-1) — How life-threatening the wound is
  - `bleed_rate`: float (mL/min) — Current rate of blood loss
  - `blood_volume`: float (L) — Remaining blood volume
  - `clotting_status`: enum (normal/impaired/impossible) — Affected by gravity
  - `infection_risk`: float (0-1) — Probability of wound infection over time
  - `treatment_applied`: list — Medical interventions performed
  - `medical_supplies_remaining`: int — Available treatment resources
  - `consciousness_threshold`: float — Blood volume at which patient loses consciousness
  - `in_suit_treatment_limitation`: bool — Whether patient is in EVA suit (severely limits treatment)
- **Player-Facing Effects**:
  - Wound inspection interface showing severity and options
  - Blood loss visual effects (screen darkening, tunnel vision)
  - Pain indicators affecting movement and actions
  - Treatment options varying by supplies, gravity, and suit status
  - Casualty biometric readout on HUD
  - Recovery timeline after treatment
  - Injury alerts with severity classification
  - High-g warning overlays during combat
- **Exercised By**: zero-g-wound, pirate-ambush, eva-rescue

### Navigation & Fuel
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates route planning, fuel consumption, trajectory management, and travel time. Covers delta-v budgets, burn calculations, intercept windows, diversion costs, escape trajectories, and the critical "point of no return" calculations where fuel becomes insufficient for safe options. Applies at scales from EVA maneuvering to interplanetary transit.
- **Key State Variables**:
  - `position`: vec3 — Current location
  - `velocity`: vec3 — Current velocity vector
  - `destination_options`: list — Reachable destinations with costs
  - `fuel_reserves`: float (kg) — Remaining propellant mass
  - `burn_rate`: float (kg/s) — Fuel consumption during thrust
  - `delta_v_budget`: float (m/s) — Remaining velocity change capacity
  - `travel_time`: map (destination → hours) — ETA to each option
  - `route_hazards`: list — Debris fields, radiation zones, etc.
  - `intercept_windows`: list — Time-critical approach opportunities
  - `escape_vectors`: list — Available flee trajectories with fuel costs
  - `drift_trajectory`: path — Where the ship goes if engines fail
- **Player-Facing Effects**:
  - Nav computer interface with route planner
  - Fuel gauge with remaining delta-v
  - ETA calculations and diversion cost comparisons
  - Intercept countdown timers
  - Escape route highlights during combat
  - "Point of no return" indicators for fuel-critical decisions
  - Hazard warnings on planned routes
  - Burn schedule display for long transits
- **Exercised By**: ice-miner-blockade, deep-space-transit, pirate-ambush, eva-rescue

### NPC Identity & Personality
- **Category**: Social
- **Maturity**: Refined
- **Purpose**: Gives non-player characters persistent identities, skills, personalities, motivations, histories, secrets, and behavioral patterns. NPCs are simulated entities with their own agendas and needs — not quest dispensers. Under sustained stress, hidden traits emerge: coping mechanisms, breaking points, vices, loyalties, and fears. NPCs lie, hoard, form alliances, betray trust, and surprise the player based on their internal state.
- **Key State Variables**:
  - `name`: string — NPC identifier
  - `background`: text — History, origin, experience
  - `skills`: map (skill → float) — Rated competencies
  - `personality_traits`: list — Core personality descriptors (introvert/extrovert, confrontational/avoidant, etc.)
  - `motivation`: enum/text — What this NPC currently wants most
  - `trust`: map (entity → float) — Trust toward player and other NPCs
  - `loyalty`: float (0-1) — Commitment to current employer/group/faction
  - `morale`: float (0-1) — Current emotional/mental state
  - `fear_level`: float (0-1) — How afraid the NPC currently is
  - `secrets`: list — Information the NPC is hiding
  - `breaking_point`: float — Stress threshold beyond which behavior changes dramatically
  - `stress_tolerance`: float — How much pressure the NPC can absorb
  - `coping_mechanisms`: list — How the NPC deals with stress (drinking, isolation, aggression, etc.)
  - `hunger_level`: float (0-1) — Current nutritional state
  - `faction_affiliation`: ref — Which faction this NPC belongs to
  - `relationships`: map (NPC → relationship) — Connections to other NPCs
  - `alibi_consistency`: float — How well their story holds up under questioning
- **Player-Facing Effects**:
  - Dialogue reflecting personality, trust, fear, and current state
  - Observable behavior patterns (nervous, aggressive, helpful, evasive)
  - Performance variation based on morale, skill, and stress
  - Relationship-driven events (alliances, conflicts, betrayals)
  - Witnesses who clam up or open up based on approach
  - NPCs contradicting each other's stories
  - Stress responses emerging over sustained scenarios
  - Background revealed through conversation and observation
- **Exercised By**: spaceport-crew-hiring, deep-space-transit, station-noir, colony-food-crisis, colony-overseer

### Player Health
- **Category**: Biological
- **Maturity**: Refined
- **Purpose**: Tracks the player's physical and cognitive condition and its cascading effects on capability. Synthesized across survival (temperature, oxygen, fatigue), trauma (blood loss, consciousness), endurance (nutrition, sleep debt), combat (g-force, adrenaline), and EVA (radiation, exertion) scenarios. The player is subject to the same environmental pressures as NPCs.
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
  - `immune_function`: float (0-1) — Resistance to illness, degrades with malnutrition
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
- **Exercised By**: cold-habitat-survival, zero-g-wound, deep-space-transit, pirate-ambush, eva-rescue, colony-food-crisis, colony-overseer

### Power Grid
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates electrical power generation, storage, distribution, and consumption. The foundational technical system — most other technical systems depend on it. Covers reactor/solar/battery sources, distribution buses, load balancing, overclock capability, and the hard tradeoffs of routing limited energy to competing systems under crisis.
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
- **Player-Facing Effects**:
  - Power distribution panel with allocation controls
  - Reactor heat gauge and overclock warnings
  - Lights flickering or dead when power is low
  - Systems refusing to start without sufficient power
  - Battery health indicators
  - Brownout flicker effects
  - System shutdown notifications when power is pulled
  - Load management interface for prioritizing subsystems
- **Exercised By**: cold-habitat-survival, zero-g-wound, pirate-ambush, eva-rescue, colony-overseer

### Reputation & Trust
- **Category**: Social
- **Maturity**: Refined
- **Purpose**: Tracks how factions, organizations, and individuals perceive the player and each other. Reputation is public (what people have heard), trust is personal (direct experience). Both affect access to opportunities, dialogue, pricing, willingness to cooperate, and the player's credibility as mediator, investigator, or leader. Information about whom the player associates with propagates through social networks.
- **Key State Variables**:
  - `reputation`: map (faction/entity → float) — Public standing with each group
  - `trust`: map (individual → float) — Personal trust from direct interactions
  - `interaction_history`: list — Log of significant actions and their witnesses
  - `promises`: list — Commitments made, with kept/broken status
  - `public_perception`: float — Aggregate reputation across all factions
  - `known_associations`: list — Who the player has been seen with
  - `heat_level`: float — How much unwanted attention the player is drawing
  - `perceived_fairness`: float — How fair the player's decisions appear to the public
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
- **Exercised By**: spaceport-crew-hiring, ice-miner-blockade, station-noir, colony-food-crisis

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
- **Purpose**: Simulates armed forces, threat assessment, rules of engagement, escalation dynamics, civil unrest, and the loyalty splits within security forces. Covers station security patrols, military vessels, pirate threats, riot control, and the escalation ladder from posturing through warning to lethal engagement. Security forces may be compromised, sympathetic to different factions, or overwhelmed.
- **Key State Variables**:
  - `force_disposition`: map (unit → position/status) — Where security forces are and what they're doing
  - `officer_roster`: list — Individual security personnel with loyalty flags
  - `loyalty_split`: map (faction → float) — How security loyalties divide
  - `rules_of_engagement`: enum (hold/warn/engage) — Current ROE
  - `escalation_level`: int (0-5) — How close to violence the situation is
  - `weapons_status`: map (unit → enum) — Armed/unarmed/weapons-hot
  - `threat_assessment`: map (entity → level) — Perceived threat from each entity
  - `alert_level`: enum — Station/fleet alert status
  - `patrol_routes`: list — Security patrol patterns and schedules
  - `crime_rate`: float — Current crime level
  - `riot_probability`: float — How likely civil unrest is
  - `evidence_locker`: list — Seized evidence (can be tampered with)
  - `informant_network`: list — Security intelligence sources
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
- **Exercised By**: ice-miner-blockade, pirate-ambush, station-noir, colony-food-crisis

### Sensors & Scanning
- **Category**: Technical
- **Maturity**: Developing
- **Purpose**: Simulates detection, identification, and tracking of objects, ships, hazards, and conditions. Covers both ship-scale sensors (active/passive radar, contact tracking, ECM/ECCM) and personal-scale (suit sensors, biometric telemetry, debris proximity). Sensor quality directly affects threat assessment, navigation safety, and rescue operations.
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
- **Player-Facing Effects**:
  - Sensor board with contact markers and IFF tags
  - Target detail panel (mass, drive signature, weapons profile)
  - ECM/ECCM indicators
  - Detection warnings when scanned by hostiles
  - Hazard warnings (debris, radiation)
  - Long-range scan results
  - Casualty vitals feed (intermittent if signal is poor)
  - "Something on sensors" ambiguous alerts
- **Exercised By**: deep-space-transit, pirate-ambush, eva-rescue

### Ship Crewing
- **Category**: Social
- **Maturity**: Developing
- **Purpose**: Simulates crew positions, role requirements, minimum competency thresholds, shift scheduling, fatigue, and the effects of staffing quality on ship operations. Bridges NPC simulation and ship capability — an unfilled role or exhausted crew member degrades the systems they operate.
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
- **Player-Facing Effects**:
  - Crew roster interface showing filled/vacant positions
  - Shift calendar and scheduling controls
  - Ship capability ratings changing with crew quality
  - Vacancy warnings (e.g., "No engineer — repair capability disabled")
  - Fatigue warnings and overtime notifications
  - Crew compatibility events (arguments, cooperation bonuses)
  - Performance degradation indicators
- **Exercised By**: spaceport-crew-hiring, deep-space-transit

### Social Dynamics
- **Category**: Social
- **Maturity**: Refined
- **Purpose**: Simulates interpersonal relationships, tensions, group morale, mob psychology, and community cohesion. Covers personality compatibility, grudges, alliances, cabin fever in confined spaces, rumor propagation, and the emergence of group culture or faction formation under pressure. Operates at scales from a five-person crew to a four-thousand-person colony.
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
  - `mob_formation_threshold`: float — How close the population is to collective action
  - `altruism_index`: float (0-1) — Community cooperation vs. selfishness
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
- **Exercised By**: spaceport-crew-hiring, deep-space-transit, colony-food-crisis, colony-overseer

### Station Administration
- **Category**: Political
- **Maturity**: Refined
- **Purpose**: Simulates station or colony governance — leadership priorities, competence, budget constraints, corruption, policy decisions, legitimacy, and the limits of bureaucratic control. Administration can be overwhelmed, compromised, authoritarian, or absent. Covers emergency powers, martial law, cover-ups, and the erosion of legitimacy under crisis.
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
- **Exercised By**: ice-miner-blockade, station-noir, colony-food-crisis, colony-overseer

### Station Services & Infrastructure
- **Category**: Technical
- **Maturity**: Developing
- **Purpose**: Simulates the physical station as a place with areas, facilities, services, access controls, surveillance, and infrastructure. Covers repair bays, fuel depots, markets, medical facilities, bars, labor offices, and also the hidden geography — maintenance crawlspaces, decommissioned sections, ventilation networks — that can be leveraged or exploited.
- **Key State Variables**:
  - `station_layout`: data — Rings, sectors, levels, areas
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
- **Exercised By**: spaceport-crew-hiring, station-noir

### Surface Environment
- **Category**: Physical
- **Maturity**: Draft
- **Purpose**: Simulates the conditions on a planetary or lunar surface that affect outdoor work — regolith dust, radiation, temperature extremes, low gravity, atmospheric composition (if any), and daylight/darkness cycles. Determines EVA windows, work speed, equipment fouling rates, and the physical cost of surface operations.
- **Key State Variables**:
  - `dust_accumulation_rate`: float — Rate at which regolith coats equipment (esp. solar panels)
  - `surface_temperature`: float (°C) — Current exterior temperature
  - `radiation_level`: float (mSv/hr) — Surface radiation exposure rate
  - `daylight_cycle`: schedule — Light/dark periods affecting solar power and EVA safety
  - `dust_storm_probability`: float (0-1) — Chance of dust event degrading visibility and equipment
  - `gravity_level`: float (g) — Surface gravity affecting work speed, fatigue, and equipment
  - `traverse_time`: map (location pair → minutes) — Travel time between outdoor work sites
  - `atmosphere`: data — Surface atmospheric composition and pressure (if any)
- **Player-Facing Effects**:
  - Surface conditions panel showing temperature, radiation, dust status
  - EVA window availability indicator
  - Dust accumulation forecast for solar panels
  - Radiation warnings for prolonged surface work
  - Traverse time estimates between outdoor sites
  - "Conditions safe for EVA" / "EVA not recommended" status
  - Dust storm alerts
- **Exercised By**: colony-overseer

### Task & Workforce Management
- **Category**: Technical
- **Maturity**: Draft
- **Purpose**: Simulates the assignment, scheduling, and tracking of work tasks across a population with limited personnel, varying skills, and competing priorities. The core management system — the player's primary interface for running a colony, station, or ship as an overseer. Tracks task queues, worker assignments, skill matching, progress, opportunity costs, and the cascading effects of pulling workers from one task to address another.
- **Key State Variables**:
  - `task_queue`: list — Prioritized tasks with urgency, required skills, estimated duration, personnel count
  - `worker_pool`: list — Available personnel with current assignment, fatigue, skill certifications, interpersonal flags
  - `task_progress`: map (task → float 0-1) — Per-task completion percentage
  - `quality_modifier`: map (task → float) — Quality of work based on skill match of assigned worker
  - `task_dependencies`: graph — Tasks that must finish before others can start
  - `opportunity_cost`: map (task → list) — What's degrading while resources are allocated elsewhere
  - `shift_schedule`: data — Work/rest rotation for all personnel
  - `overtime_accumulated`: map (NPC → float hours) — Hours worked beyond normal shifts
  - `abandonment_penalty`: map (task → effect) — Consequences of pulling workers mid-task
- **Player-Facing Effects**:
  - Task board interface showing all active/pending tasks with urgency color coding
  - Drag-and-drop crew assignment with skill-match indicators
  - Estimated completion times updating based on who's assigned
  - Warning flags when unqualified personnel are assigned
  - Degradation alerts for unattended tasks
  - Shift schedule overview with overtime warnings
  - "What happens if I delay this" projection tooltips
  - Opportunity cost tracker showing what's getting worse while you fix something else
  - Task abandonment warnings when reassigning mid-repair
- **Exercised By**: colony-overseer

### Thermal Regulation
- **Category**: Physical
- **Maturity**: Developing
- **Purpose**: Simulates heat generation, retention, transfer, and loss within enclosed spaces. Covers heaters, radiators, insulation, thermal bleed to vacuum, and the thermal consequences of power loss.
- **Key State Variables**:
  - `ambient_temperature`: map (compartment → float °C) — Temperature per area
  - `insulation_integrity`: map (section → float 0-1) — How well walls retain heat
  - `heat_source_output`: map (source → float W) — Active heat generation
  - `thermal_bleed_rate`: float (W) — Heat loss to exterior/vacuum
  - `radiator_status`: enum (online/offline/damaged) — Heat dissipation system state
  - `thermal_mass`: float — How quickly temperature changes
- **Player-Facing Effects**:
  - Visible breath fog in cold compartments
  - Frost forming on surfaces
  - Numbness and hypothermia effects on player
  - Thermostat/temperature displays on panels
  - Heat shimmer in overheated areas
- **Exercised By**: cold-habitat-survival, colony-overseer

### Time Pressure
- **Category**: Technical
- **Maturity**: Refined
- **Purpose**: Simulates deadlines, ticking costs, countdowns, and the passage of time as a strategic resource. Creates urgency through accumulating fees, depleting supplies, expiring opportunities, NPC patience limits, faction ultimatums, and resupply countdowns. Operates as a meta-system that adds tension to other systems.
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
- **Exercised By**: spaceport-crew-hiring, ice-miner-blockade, deep-space-transit, colony-food-crisis, colony-overseer

---

## Dependency Map

### Hard Dependencies
- Atmosphere Management --> Equipment & Repair: recyclers and scrubbers are mechanical systems that degrade and require maintenance
- Atmosphere Management --> Habitat Integrity: atmosphere cannot be maintained if hull is breached
- Atmosphere Management --> Power Grid: recyclers and scrubbers require electrical power
- Attitude Control --> Power Grid: reaction control thrusters and gyroscopes require power
- Combat & Weapons --> Attitude Control: weapon firing arcs require correct ship facing
- Combat & Weapons --> Power Grid: weapons require power to charge, fire, and maintain locks
- Combat & Weapons --> Sensors & Scanning: targeting solutions require sensor data on enemy position
- Communications --> Power Grid: antenna and transmitter require power
- Communications --> Station Services & Infrastructure: communication systems are physical infrastructure
- Diplomacy & Negotiation --> Faction System: negotiations occur between factions with defined interests
- EVA & Spacewalk --> Navigation & Fuel: intercept and return trajectories require thrust
- EVA & Spacewalk --> Power Grid: airlock cycle requires station power
- Fleet & Ship Movement --> Navigation & Fuel: all maneuvers consume fuel and follow trajectory mechanics
- Fluid Dynamics --> EVA & Spacewalk: fluid behavior in/around suits governed by micro-g EVA environment
- Fluid Dynamics --> Rotational Gravity: fluid behavior determined by current gravity level
- Food & Water Supply --> Equipment & Repair: water recycler and food storage require functioning hardware
- Food & Water Supply --> Power Grid: greenhouses need powered lighting/climate; water rigs need powered pumps
- Food & Water Supply --> Station Administration: distribution policies set and enforced by governance
- Labor Market --> NPC Identity & Personality: candidates must exist as simulated NPCs
- Law & Jurisdiction --> Station Administration: legal authority flows from governance charter
- Navigation & Fuel --> Rotational Gravity: docking trajectories must account for station spin
- Navigation & Fuel --> Ship Crewing: course corrections and burns require a qualified pilot
- Power Grid --> Surface Environment: solar panel output depends on dust accumulation and daylight cycle
- Rotational Gravity --> Attitude Control: spin-up requires thruster compensation
- Rotational Gravity --> Power Grid: spin motor requires electrical power
- Security & Threat --> Law & Jurisdiction: ROE, detention authority, evidentiary standards defined by legal framework
- Security & Threat --> Station Administration: security operates under administrative authority
- Ship Crewing --> NPC Identity & Personality: crew members are persistent NPCs
- Social Dynamics --> NPC Identity & Personality: interpersonal simulation requires personality data
- Task & Workforce Management --> NPC Identity & Personality: task assignments require worker skills, certifications, fatigue, and interpersonal constraints
- Station Administration --> Economy & Currency: governance constrained by budget
- Station Administration --> Security & Threat: governance requires enforcement capability
- Thermal Regulation --> Power Grid: heaters and radiators require electrical power

### Soft Dependencies
- Cargo & Trade ~~> Fleet & Ship Movement: blockades and fleet actions disrupt trade
- Cargo & Trade ~~> Navigation & Fuel: trade requires transport, which consumes fuel
- Communications ~~> Equipment & Repair: damaged comm arrays reduce range and clarity
- Communications ~~> Faction System: factions use comms for coordination and propaganda
- Communications ~~> Rotational Gravity: station rotation creates periodic line-of-sight dropout
- Economy & Currency ~~> Food & Water Supply: food scarcity drives price inflation and black market emergence
- Economy & Currency ~~> Station Services & Infrastructure: black market operates within station infrastructure
- Equipment & Repair ~~> NPC Identity & Personality: repair quality depends on skill match of assigned worker
- Equipment & Repair ~~> Player Health: fatigued or injured player repairs more slowly
- Equipment & Repair ~~> Power Grid: repair tools and diagnostics need power
- Food & Water Supply ~~> Thermal Regulation: greenhouse crops are temperature-sensitive; thermal loss causes crop stress
- Faction System ~~> Economy & Currency: faction grievances often have economic roots
- Faction System ~~> Food & Water Supply: hunger and distribution unfairness drive faction formation
- Faction System ~~> Reputation & Trust: trust between factions affects negotiation willingness
- Fleet & Ship Movement ~~> Sensors & Scanning: tracking formations depends on sensor contact quality
- Habitat Integrity ~~> Rotational Gravity: excessive spin stresses structure
- Labor Market ~~> Economy & Currency: local conditions affect candidate availability and wages
- Labor Market ~~> Reputation & Trust: player reputation affects candidate willingness
- Law & Jurisdiction ~~> Communications: filing complaints and transmitting evidence require comms
- Law & Jurisdiction ~~> Reputation & Trust: credibility with legal bodies depends on reputation
- Medical & Injury ~~> Attitude Control: treating wounds during high-g maneuvers is extremely difficult
- Medical & Injury ~~> Equipment & Repair: medical equipment can be damaged and need repair
- Medical & Injury ~~> EVA & Spacewalk: treatment options severely limited while in pressurized suit
- Medical & Injury ~~> Fluid Dynamics: blood behavior in micro-gravity affects treatment
- Medical & Injury ~~> Rotational Gravity: treatment effectiveness varies with gravity level
- NPC Identity & Personality ~~> Atmosphere Management: poor air degrades NPC morale and sleep
- NPC Identity & Personality ~~> Food & Water Supply: hunger modifies NPC behavior, loyalty, and desperation
- NPC Identity & Personality ~~> Reputation & Trust: NPC willingness to talk gated by trust and perceived risk
- NPC Identity & Personality ~~> Security & Threat: NPC fear rises with security alert level
- NPC Identity & Personality ~~> Station Services & Infrastructure: NPC behavior influenced by local conditions
- Player Health ~~> Atmosphere Management: low O2 / high CO2 degrades health
- Player Health ~~> EVA & Spacewalk: suit consumable depletion degrades player condition
- Player Health ~~> Food & Water Supply: player nutrition and hydration affect condition
- Player Health ~~> Medical & Injury: untreated wounds degrade health
- Player Health ~~> Ship Crewing: player taking extra shifts increases fatigue
- Player Health ~~> Task & Workforce Management: player doing field work accumulates fatigue and loses oversight capability
- Player Health ~~> Thermal Regulation: prolonged cold causes hypothermia
- Security & Threat ~~> Diplomacy & Negotiation: escalation level affects security posture
- Security & Threat ~~> Faction System: security loyalties may split across factions
- Security & Threat ~~> Reputation & Trust: security response scales with player heat level
- Security & Threat ~~> Social Dynamics: civil unrest and mob formation drive escalation
- Sensors & Scanning ~~> Communications: biometric telemetry relies on radio link quality
- Sensors & Scanning ~~> Power Grid: active sensors draw significant power
- Sensors & Scanning ~~> Ship Crewing: sensor monitoring requires a crew member on watch
- Ship Crewing ~~> Social Dynamics: crew compatibility affects ship efficiency
- Social Dynamics ~~> Atmosphere Management: poor air quality increases irritability and conflict
- Social Dynamics ~~> Food & Water Supply: meal quality and rationing affect morale and tension
- Social Dynamics ~~> Ship Crewing: overwork and unfair shifts breed resentment
- Station Administration ~~> Economy & Currency: corruption motivated and evidenced by financial flows
- Social Dynamics ~~> Task & Workforce Management: interpersonal conflicts constrain crew pairing; morale affects task acceptance
- Station Administration ~~> Social Dynamics: leadership legitimacy depends on crew confidence
- Station Services & Infrastructure ~~> Station Administration: access permissions set by administration
- Task & Workforce Management ~~> Social Dynamics: perceived unfairness in assignments degrades morale; overtime breeds resentment
- Task & Workforce Management ~~> Time Pressure: task priority is driven by degradation timers
- Thermal Regulation ~~> Habitat Integrity: poor insulation increases thermal bleed
- Time Pressure ~~> Economy & Currency: costs accumulate over time
- Time Pressure ~~> Food & Water Supply: reserve depletion rate sets urgency
- Time Pressure ~~> Navigation & Fuel: course deviations extend transit and compress margins

### Feedback Loops
- Atmosphere Management <-> Equipment & Repair <-> Ship Crewing: Degrading air systems need repair; repair pulls crew from other duties; understaffed shifts mean other systems get less attention
- Cargo & Trade <-> Economy & Currency: Blockades disrupt trade, worsening economy; economic pressure creates smuggling opportunities
- Combat & Weapons <-> Equipment & Repair: Weapons fire generates wear; taking hits damages components; damaged weapons reduce effectiveness; repair restores capability but costs time under fire
- Diplomacy & Negotiation <-> Faction System <-> Station Administration: Admin policies drive demands; negotiation outcomes reshape policy; faction pressure forces concessions or authoritarian response
- Economy & Currency <-> Faction System <-> Station Administration: Economic failures create grievances; faction actions worsen economy; admin responses affect both
- Economy & Currency <-> Food & Water Supply <-> Social Dynamics: Scarcity drives prices up; high prices increase desperation; black markets emerge but deepen inequality; inequality fuels tension
- Economy & Currency <-> Time Pressure: Costs accumulate over time; time pressure forces economic compromises; running out of money creates new deadlines
- EVA & Spacewalk <-> Player Health: Longer EVA depletes consumables and accumulates fatigue; declining health slows movement, extending EVA further
- Food & Water Supply <-> Faction System <-> Security & Threat: Unequal distribution creates grievances; faction raids reduce supply; security crackdowns restore order but deepen resentment
- Food & Water Supply <-> Social Dynamics <-> NPC Identity & Personality: Rationing breeds resentment; resentful crew may hoard or steal; discovered hoarding escalates tension
- Navigation & Fuel <-> EVA & Spacewalk: Aggressive intercept burns leave less fuel for return; cautious burns extend time outside, consuming more suit consumables
- Navigation & Fuel <-> Fleet & Ship Movement <-> Combat & Weapons: Escape burns consume fuel; less fuel means fewer evasion options; staying in weapons range consumes more fuel for maneuvering
- NPC Identity & Personality <-> Reputation & Trust: Talking to NPCs changes trust; trust determines what's revealed; revealed information reshapes reputation with others
- Player Health <-> Equipment & Repair: Worse health means worse repairs; systems stay offline longer; prolonged environmental exposure degrades health further
- Player Health <-> Medical & Injury: Declining health reduces treatment ability; untreated injury accelerates decline
- Player Health <-> Medical & Injury <-> Attitude Control: High-g evasion causes injuries; injuries degrade piloting; worse piloting leads to more incoming fire
- Player Health <-> Rotational Gravity: Player needs gravity to treat wound but must be capable enough to restore it
- Power Grid <-> Equipment & Repair <-> Combat & Weapons: Reactor damage reduces power; less power means weaker weapons/sensors; weaker sensors mean more hits; more hits damage reactor
- Power Grid <-> Thermal Regulation <-> Atmosphere Management: All three compete for limited energy; restoring one reduces availability for others
- Reputation & Trust <-> Labor Market: Good reputation attracts better candidates; treating crew well builds reputation
- Reputation & Trust <-> Security & Threat: Drawing attention raises heat; high heat makes NPCs afraid to help; lack of allies forces riskier moves drawing more attention
- Rotational Gravity <-> Habitat Integrity: Spin creates gravity but stresses structure; structural limits constrain maximum spin
- Rotational Gravity <-> Navigation & Fuel: Station spin dictates approach windows; missing a window costs fuel and time
- Security & Threat <-> Diplomacy & Negotiation: Failed negotiations escalate threat; high threat makes negotiation harder but more urgent
- Security & Threat <-> Social Dynamics: Rising tension triggers security response; heavy-handed security deepens breakdown; cohesion reduces need for intervention
- Sensors & Scanning <-> Security & Threat <-> Fleet & Ship Movement: Better data improves threat assessment; accurate threats inform evasion; evasion changes sensor geometry
- Ship Crewing <-> Social Dynamics: Overworked crew become hostile; hostile crew perform worse; others pick up slack; everyone's workload increases
- Time Pressure <-> Faction System <-> Diplomacy & Negotiation: Shrinking reserves increase urgency; urgent factions make harder demands; failed negotiations waste time
- Task & Workforce Management <-> NPC Identity & Personality <-> Social Dynamics: Overtime/unfamiliar tasks increase fatigue and lower morale; low morale reduces work quality; lower quality means longer tasks; longer tasks mean more overtime
- Task & Workforce Management <-> Time Pressure <-> Equipment & Repair: Multiple systems degrade on independent timers; fixing one pauses its timer but others keep ticking; pulling workers mid-repair wastes progress and may worsen the abandoned system
- Player Health <-> Task & Workforce Management <-> Station Administration: Player doing field work is effective at one task but loses oversight; colony runs worse without coordination; staying at desk means one fewer pair of hands on critical tasks
- Food & Water Supply <-> Thermal Regulation <-> Power Grid: Crops need stable temperature; temperature needs power; power is failing; crop loss threatens food and morale; low morale threatens workforce; workforce determines if power gets fixed
- Time Pressure <-> Food & Water Supply <-> Player Health: Dwindling supplies force rationing; rationing degrades health; degraded crew works slower; slower work extends timelines

---

## Analysis & Recommendations

### Under-Tested Systems
The following systems appear in only 1 scenario:
- **Cargo & Trade** — only ice-miner-blockade
- **Combat & Weapons** — only pirate-ambush
- **EVA & Spacewalk** — only eva-rescue
- **Labor Market** — only spaceport-crew-hiring
- **Law & Jurisdiction** — only station-noir
- **Surface Environment** — only colony-overseer
- **Task & Workforce Management** — only colony-overseer (but this is arguably the most important new system — it needs stress-testing across ship, station, and colony scales)

### Potential Missing Systems
Systems implied by the scenarios but not yet explicitly defined:
- **Inventory & Personal Equipment** — Players carry tools, medical supplies, weapons, EVA suits, data slates. Multiple scenarios reference "available tools" or "medical supplies remaining" but no system tracks personal inventory as a whole.
- **Orbital Mechanics / Astrodynamics** — Navigation & Fuel covers route planning, but the underlying orbital mechanics (transfer windows, gravity assists, orbital periods, planetary positions) that determine what routes are even possible are not modeled.
- **Stealth & Detection** — Sensors & Scanning covers detection, but no system explicitly models a ship's ability to run dark, reduce signatures, or hide — the pirate ambush scenario implies this strongly.
- **AI & Automation** — No scenario has yet explored automated systems, drones, or AI crew substitutes — which would stress Ship Crewing, Task & Workforce Management, Equipment & Repair, and raise ethical/trust questions.
- **Terraforming / Environmental Engineering** — Colony-overseer mentions a terraforming colony, but no system yet models the long-term environmental transformation process (atmospheric processing, soil creation, biome establishment).

### Incomplete Dependency Chains
- **Medical & Injury → ??? → Inventory**: Treatment requires medical supplies, but no inventory system tracks what's available beyond scenario-specific mentions
- **Task & Workforce Management → ??? → Ship Crewing**: Both systems manage personnel assignment, but at different scales (colony-wide vs. ship roles). They likely need a shared abstraction or explicit bridge.
- **Faction System → NPC Identity & Personality**: Factions have members but the link between individual NPC loyalty shifts and faction cohesion changes isn't fully formalized
- **Law & Jurisdiction → ??? → other scenarios**: Currently only exercised in station-noir; needs to connect to trade law (Cargo & Trade), salvage law (EVA), and labor law (Labor Market)
- **Combat & Weapons → ??? → Habitat Integrity**: Ship combat should damage habitat structure, but this dependency isn't captured since no scenario combines both systems yet
- **Surface Environment → ??? → other physical systems**: Dust, radiation, and temperature affect many systems (Equipment & Repair, Player Health, EVA & Spacewalk) but these cross-links aren't formalized yet

### Recommended Next Scenarios
To stress-test remaining gaps:

1. **Smuggling run / contraband trade** — Transporting illegal goods past inspections. Would stress: Cargo & Trade, Law & Jurisdiction, Sensors & Scanning (stealth/detection), Economy & Currency, Security & Threat, Communications. Would surface **Stealth & Detection** and connect Law & Jurisdiction to trade.

2. **Ship-to-ship boarding action** — Pirates or military board your vessel (or you board theirs). Would stress: Combat & Weapons, EVA & Spacewalk, Habitat Integrity, Medical & Injury, Equipment & Repair, Security & Threat. Would connect Combat → Habitat Integrity and stress EVA in a combat context.

3. **Station commander's day** — Running a busy station with competing docking requests, maintenance schedules, and diplomatic visitors. Would stress: Task & Workforce Management at station scale, Station Administration, Station Services & Infrastructure, Economy & Currency, Diplomacy & Negotiation. Critical for proving Task & Workforce Management works beyond the colony context.

4. **Ship captain managing a long patrol** — Commanding a crewed vessel on an extended patrol route. Would stress: Task & Workforce Management at ship scale, Ship Crewing, Navigation & Fuel, Sensors & Scanning, Equipment & Repair, Social Dynamics. Bridges Task & Workforce Management with Ship Crewing.

5. **Mining colony labor dispute** — Workers organizing, striking, negotiating. Would stress: Labor Market, Faction System, Law & Jurisdiction, Economy & Currency, Diplomacy & Negotiation, Task & Workforce Management. Would connect Labor Market to political systems and test workforce management under political constraints.
