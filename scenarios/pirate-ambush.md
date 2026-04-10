# Scenario: Pirate Ambush

## Narrative
You're three days into a quiet transit burn between Callisto and Ganymede when your sensor board lights up like a Christmas tree. Three contacts, emerging from the radar shadow of a tumbling carbonaceous asteroid — they were running dark, engines cold, waiting for someone like you to drift into the kill box. Their drives are already hot. They're on intercept vectors, spreading into a triangular formation that cuts off your easiest escape trajectories. A targeting radar paints your hull. Then the comm crackles: "Cut your drive and open your cargo locks. You've got thirty seconds."

You're alone, outgunned, and your ship isn't built for this. You have a point-defense turret meant for micro-meteorites, not combat. Your engines can outrun one of them, maybe, but not three on converging vectors. Your reactor is running at cruise output — combat power means overclocking it past safety margins. Every second you spend thinking, they're closing the distance and tightening the noose. The good news is that pirates want cargo, not corpses — dead crews mean investigation, and investigations are bad for business. The bad news is they'll kill you anyway if you make them work for it.

Your ship's damage control board is green across the board. That won't last. Whether you fight, run, or try something clever, pieces of your ship are about to start failing in ways the manufacturer's warranty definitely doesn't cover. Whatever you decide, decide now — thirty seconds was generous, and you've already burned ten of them.

## Setting
- **Location type**: deep space (transit corridor)
- **Scale**: tactical
- **Tone**: combat, survival

## Player Agency
- **Fight**: Power up weapons, overclock the reactor, and engage — try to disable or destroy at least one attacker to break the formation
- **Flee**: Dump excess mass, burn hard on a single escape vector, and pray your engine holds together at emergency thrust
- **Surrender**: Cut engines, open cargo locks, and hope they take what they want and leave you alive
- **Deceive**: Fake a reactor overload signature, broadcast a distress call on military frequencies, or spoof additional transponder contacts to bluff reinforcements
- **Negotiate**: Open comms and offer specific high-value cargo in exchange for safe passage — give them what they want without giving them everything
- **Ram / kamikaze bluff**: Aim directly at the lead ship on a collision course — pirates don't profit from mutual destruction
- **Use the asteroid field**: Maneuver into the nearby debris for cover, forcing close-quarters engagement where numbers matter less
- **Delay and distract**: Stall on comms while maneuvering for a better position or charging weapons

## Resolution Paths
- **Best**: Disable the lead ship, scatter the others, escape with minor damage and salvageable pirate components
- **Good**: Bluff or outmaneuver the pirates — escape without serious engagement, ship intact, cargo mostly retained
- **Mixed**: Surrender partial cargo or take moderate damage but survive and remain mobile
- **Bad**: Ship crippled in the engagement — alive but drifting, systems failing, waiting for rescue that may not come
- **Worst**: Hull breach, catastrophic system failure, crew casualties — loss of ship or death

## Required Simulation Systems

### Combat & Weapons
- **Purpose**: Simulates offensive and defensive armaments, targeting, firing solutions, ammunition, and weapon state
- **Key State**: Weapon type and mount, ammunition/charge count, firing arcs, lock-on status, rate of fire, heat buildup, accuracy at range, weapon damage output, point-defense mode vs. manual targeting
- **Player-facing**: Targeting reticle and lock indicators, weapon heat gauge, ammo counter, firing arc overlay on nav display, hit/miss feedback, point-defense interception alerts

### Sensors & Scanning
- **Purpose**: Simulates detection, identification, and tracking of objects and ships — both active and passive
- **Key State**: Sensor mode (active/passive), detection range, contact list with bearing/range/velocity, radar cross-section of targets, electronic countermeasures active, sensor resolution, false contact generation, stealth detection threshold
- **Player-facing**: Sensor board with contacts, IFF tags, target detail panel (mass, drive signature, weapons profile), ECM/ECCM indicators, detection warnings when scanned by hostiles

### Security & Threat
- **Purpose**: Simulates threat assessment, escalation dynamics, hostile intent evaluation, and rules of engagement
- **Key State**: Threat level per contact, escalation state (standoff/engaged/lethal), hostile intent confidence, incoming weapons lock detection, evasion priority queue, surrender protocol status
- **Player-facing**: Threat indicators per contact (color-coded), incoming lock warnings, escalation status display, surrender/negotiation state on HUD

### Fleet & Ship Movement
- **Purpose**: Simulates the positions, velocities, accelerations, and formation tactics of multiple ships in 3D space
- **Key State**: Ship positions and velocity vectors, formation geometry, intercept trajectories, relative closure rates, engine thrust output, maneuvering fuel cost, pursuit/evasion calculations, formation break conditions
- **Player-facing**: Nav display with vector lines, intercept countdown timers, formation overlay, pursuit cone visualization, relative velocity readouts

### Attitude Control
- **Purpose**: Simulates the orientation, rotation, and stabilization of the player's vessel during combat maneuvers
- **Key State**: Ship facing vs. travel vector, rotation rate, thruster fuel for attitude adjustments, gimbal status, spin stabilization, tumble state, facing lock for weapon alignment
- **Player-facing**: Attitude indicator (ball or navball), rotation warnings, thruster fuel gauge, tumble recovery alerts, facing-vs-velocity divergence display

### Equipment & Repair
- **Purpose**: Simulates damage to ship components, repair priority, spare parts, and degradation under stress
- **Key State**: Component health per system (reactor, engines, weapons, sensors, life support, comms), damage queue, repair time estimates, spare parts inventory, jury-rig effectiveness, cascading failure risk
- **Player-facing**: Damage control board with system status lights, repair priority interface, sparks/smoke/venting visual cues, component failure notifications, repair time countdown

### Medical & Injury
- **Purpose**: Simulates crew injuries from combat — shrapnel, burns, acceleration trauma, decompression
- **Key State**: Injury type and severity, bleed rate, burn degree, g-force trauma accumulation, consciousness threshold, treatment applied, medical supplies remaining, injury-to-capability mapping
- **Player-facing**: Injury alerts, blood loss indicators, high-g warning overlays, medical supply inventory, treatment interface, reduced capability notifications when injured

### Power Grid
- **Purpose**: Simulates reactor output, power distribution, and the hard tradeoffs of routing limited energy to competing systems
- **Key State**: Reactor output (cruise/combat/emergency), power allocation per system, overclock status and heat, total draw vs. capacity, brownout thresholds, reactor damage risk at overload
- **Player-facing**: Power distribution panel, reactor heat gauge, overclock warning, brownout flicker effects, system shutdown notifications when power is pulled

### Navigation & Fuel
- **Purpose**: Simulates course plotting, fuel reserves, and escape trajectory calculations under combat conditions
- **Key State**: Current trajectory, fuel reserves, burn rate at current thrust, escape vector options, time-to-intercept per hostile, delta-v remaining, emergency burn fuel cost, drift trajectory if engines fail
- **Player-facing**: Nav computer with escape routes highlighted, fuel gauge with burn-time estimates, intercept countdown per threat, drift projection line

### Communications
- **Purpose**: Simulates comms channels for negotiation, deception, distress calls, and electronic warfare
- **Key State**: Channel (open/encrypted/military), broadcast power, signal range, jamming status, message queue, distress beacon active, spoofed signal status, comm array damage
- **Player-facing**: Comm panel with channel selector, incoming hails, distress beacon toggle, jamming indicator, signal strength meter

### Player Health
- **Purpose**: Tracks the player's physical and cognitive state under combat stress and potential injury
- **Key State**: Consciousness, blood pressure, g-force tolerance, pain level, adrenaline, focus/clarity, stamina, respiratory status
- **Player-facing**: Screen effects (tunnel vision, blur, blackout at high g), pain indicators, reaction time degradation, stamina bar

## System Dependencies

### Hard Dependencies
- `Combat & Weapons` --depends on--> `Power Grid`: weapons require power to charge, fire, and maintain targeting locks
- `Combat & Weapons` --depends on--> `Attitude Control`: weapon firing arcs require correct ship facing; turrets need stable platform
- `Combat & Weapons` --depends on--> `Sensors & Scanning`: targeting solutions require sensor data on enemy position and velocity
- `Sensors & Scanning` --depends on--> `Power Grid`: active sensors draw significant power; passive sensors need processing power
- `Fleet & Ship Movement` --depends on--> `Navigation & Fuel`: all maneuvers consume fuel and follow trajectory mechanics
- `Attitude Control` --depends on--> `Power Grid`: reaction control thrusters and gyroscopes require power

### Soft Dependencies
- `Security & Threat` ~~depends on~~> `Sensors & Scanning`: threat assessment quality scales with sensor data fidelity
- `Security & Threat` ~~depends on~~> `Communications`: surrender and negotiation require functional comms
- `Fleet & Ship Movement` ~~depends on~~> `Sensors & Scanning`: tracking enemy formations depends on sensor contact quality
- `Equipment & Repair` ~~depends on~~> `Power Grid`: repair tools and diagnostics need power; prioritizing repair means diverting power from combat
- `Medical & Injury` ~~depends on~~> `Attitude Control`: treating wounds during high-g maneuvers or tumble is extremely difficult
- `Medical & Injury` ~~depends on~~> `Equipment & Repair`: medical equipment can be damaged and require repair before use
- `Communications` ~~depends on~~> `Power Grid`: broadcast power and signal strength scale with allocated energy
- `Communications` ~~depends on~~> `Equipment & Repair`: damaged comm arrays reduce range and clarity
- `Player Health` ~~depends on~~> `Attitude Control`: sustained high-g maneuvers degrade player consciousness and physical state
- `Player Health` ~~depends on~~> `Medical & Injury`: untreated injuries compound health degradation under combat stress

### Feedback Loops
- `Combat & Weapons` <-> `Equipment & Repair`: Weapons fire generates heat and wear; taking hits damages components. Damaged weapons reduce combat effectiveness; repair restores it but costs time under fire
- `Power Grid` <-> `Equipment & Repair` <-> `Combat & Weapons`: Reactor damage reduces available power; less power means weaker weapons and sensors; weaker sensors mean more hits taken; more hits mean more reactor damage
- `Sensors & Scanning` <-> `Security & Threat` <-> `Fleet & Ship Movement`: Better sensor data improves threat assessment; accurate threats inform evasion priorities; evasion maneuvers change sensor geometry which may reveal or lose contacts
- `Player Health` <-> `Medical & Injury` <-> `Attitude Control`: High-g evasion maneuvers cause acceleration injuries; injuries degrade the player's ability to pilot; degraded piloting leads to worse maneuvers and more incoming fire
- `Navigation & Fuel` <-> `Fleet & Ship Movement` <-> `Combat & Weapons`: Escape burns consume fuel; less fuel means fewer evasion options; fewer options mean staying in weapons range longer; sustained combat consumes more fuel for maneuvering

## Emergent Possibilities
- The player overclock the reactor for combat power, but a lucky pirate hit damages the reactor cooling system — now every second at combat output risks a meltdown, forcing impossible choices between firepower and survival
- A point-defense turret set to automatic intercepts an incoming missile but the debris shower damages the sensor array — the player is now fighting half-blind, relying on passive sensors and guesswork to track the remaining attackers
- The player's distress call on military frequencies actually reaches a patrol vessel, but it's forty minutes out — survival becomes a siege, every system degrading, every decision about buying one more minute

## Inspiration
- *The Expanse* (James S.A. Corey) — realistic space combat, the Rocinante's engagements, torpedo and PDC mechanics
- *Elite Dangerous* — ship power management, hardpoint deployment, interdiction encounters
- *FTL: Faster Than Light* — system management under fire, power allocation, cascading failures
- *Firefly / Serenity* — outgunned crews relying on cunning over firepower, Reavers
