# Scenario: Gravity Well Rescue

## Narrative
Your main drive is dead. The last thing you remember before the alarms started screaming was a hard vibration through the deck plates, then silence where the engine hum should be. Now the nav computer is painting your trajectory in red — a long, lazy curve bending toward the ochre bands of the gas giant below. You're already inside its sphere of influence, and without thrust, Newtonian mechanics has one opinion about where you're headed. The periapsis estimate keeps ticking downward. At current drift, you'll graze the upper atmosphere in just under four hours. That's not a landing. That's cremation.

You pull yourself to the engineering bay and find the damage: the main drive coupling has sheared, venting reaction mass into space before the emergency shutoffs kicked in. The fuel you have left might be enough — if you can fix the coupling or bypass it entirely. Your attitude thrusters can slow the descent marginally, but they weren't designed for this. Every minute spent diagnosing is a minute closer to the point of no return, and the deeper you fall into the gravity well, the more delta-v you'll need to climb back out. The math is brutal and it only gets worse. You can feel it in the subtle increase of weight on your boots as tidal forces begin to assert themselves.

The ship is heating up. The gas giant's magnetosphere is flooding your hull with charged particles, and the residual tidal flexing is generating heat faster than your radiators can shed it. Sensors are picking up intermittent static from the radiation belts. Your comms are degraded. If you can't fix the drive, you might be able to cobble together enough thrust from attitude jets and a controlled venting of remaining propellant — an ugly, dangerous maneuver that trades precision for raw survival. Or you get the distress call out now, while the antenna can still cut through the interference, and hope someone is close enough to reach you before the atmosphere does.

## Setting
- **Location type**: deep space (decaying orbit around gas giant)
- **Scale**: personal
- **Tone**: survival, tension

## Player Agency
- Diagnose the drive failure and attempt repair with available tools and parts
- Bypass the damaged coupling through jury-rigging — faster but unreliable
- Ration attitude thruster fuel between orientation corrections and emergency braking burns
- Decide when to commit to a burn — too early wastes fuel on an inefficient trajectory, too late and there isn't enough delta-v to escape
- Route power between thermal management, sensors, comms, and repair systems
- Attempt a distress broadcast while comms can still penetrate the magnetosphere
- Use the gas giant's own physics — a calculated aerobraking pass to alter trajectory instead of fighting it head-on
- Manage rising hull temperature and radiation exposure as the orbit decays
- Seal or vent compartments to manage thermal load across the ship

## Resolution Paths
- **Best**: Repair the drive, execute a precisely timed escape burn near periapsis to exploit the Oberth effect, and climb out of the gravity well with fuel to spare
- **Good**: Jury-rig enough thrust to achieve a stable orbit — not escaping, but buying time for rescue to arrive
- **Mixed**: Survive a harrowing aerobraking pass through the upper atmosphere, shedding velocity and hull material in equal measure — alive but ship severely damaged, drifting in a decaying orbit
- **Bad**: Partial repair fails mid-burn, leaving the ship in a lower orbit with no fuel, systems overheating, waiting for a rescue that may not come in time
- **Worst**: Drive unrecoverable, attitude fuel exhausted on failed corrections, ship crosses the atmospheric interface and breaks apart under thermal and pressure loads

## Required Simulation Systems

### Navigation & Fuel
- **Purpose**: Simulates orbital trajectory, fuel reserves, delta-v budgets, and the constantly shifting math of escape velocity within a gravity well
- **Key State**: Current orbital parameters (periapsis, apoapsis, inclination, time-to-periapsis), delta-v remaining, fuel mass, burn efficiency at current thrust level, escape velocity threshold at current altitude, Oberth effect multiplier near periapsis, trajectory projection under current conditions
- **Player-facing**: Nav display showing decaying orbit in red, periapsis countdown timer, delta-v gauge with escape threshold marker, trajectory projections for different burn timings, fuel remaining with burn-time estimates

### Power Grid
- **Purpose**: Simulates reactor output and power distribution under competing demands from repair, thermal, comms, and sensor systems
- **Key State**: Reactor output, power allocation per subsystem, total draw vs. capacity, brownout thresholds, power rerouting options, reactor thermal state under increased ambient heat
- **Player-facing**: Power distribution panel, system priority toggles, brownout flicker effects, reactor temperature warning, system shutdown notifications when power is diverted

### Equipment & Repair
- **Purpose**: Simulates drive diagnostics, component state, repair complexity, and the feasibility of jury-rigging a bypass under time pressure
- **Key State**: Drive coupling integrity, diagnostic progress, required parts and tools, spare parts inventory, bypass feasibility and reliability estimate, repair time vs. time-to-periapsis ratio, jury-rig failure probability
- **Player-facing**: Engineering diagnostic interface, repair progress bar, component condition readouts, parts inventory, bypass wiring schematic, failure risk indicator

### Attitude Control
- **Purpose**: Simulates ship orientation and the dual-use tension of attitude thrusters being the only backup for propulsion
- **Key State**: Ship facing vs. velocity vector, rotation rate, attitude thruster fuel remaining, thruster allocation (orientation vs. braking), gimbal status, tidal torque from gravity gradient
- **Player-facing**: Attitude indicator showing facing vs. prograde, thruster fuel gauge with dual allocation slider, tidal torque warnings, tumble recovery alerts, orientation lock status

### Thermal Regulation
- **Purpose**: Simulates heat buildup from tidal flexing, magnetospheric radiation, atmospheric friction, and the challenge of shedding heat while falling deeper into a gravity well
- **Key State**: Hull temperature per section, internal ambient temperature, radiator efficiency (degraded by radiation environment), tidal heating rate, atmospheric friction heating (near periapsis), coolant loop status, thermal capacity remaining before material failure
- **Player-facing**: Hull temperature display with danger thresholds, compartment heat map, radiator status and efficiency readout, thermal warnings escalating as orbit decays, visible heat distortion and glowing hull sections

### Player Health
- **Purpose**: Tracks physical condition as heat, radiation, and stress degrade the player's ability to work
- **Key State**: Core body temperature, radiation dose accumulated, fatigue, hydration, cognitive function under heat stress, burn risk from hot surfaces, g-force tolerance
- **Player-facing**: Rising ambient heat effects (sweat, blur), radiation dosimeter, fatigue indicators, reaction time degradation, heat exhaustion warnings, countdown to incapacitation at current exposure

### Time Pressure
- **Purpose**: Simulates the shrinking window of survivability as orbital decay progresses — the core tension driver of the scenario
- **Key State**: Time to periapsis, time to atmospheric interface, time to point-of-no-return (insufficient delta-v for escape), repair time estimates vs. available time, decision windows for burn timing
- **Player-facing**: Multiple countdown timers (periapsis, atmospheric entry, point of no return), urgency escalation through audio and visual warnings, narrowing decision windows displayed on nav computer

### Communications
- **Purpose**: Simulates degraded comms through the gas giant's magnetosphere and the narrowing window to get a signal out
- **Key State**: Antenna status, broadcast power, signal attenuation from magnetosphere, radiation interference level, distress beacon status, signal window remaining before interference becomes total, nearby vessel contacts
- **Player-facing**: Comms panel with signal strength meter dropping over time, static overlay increasing, distress beacon toggle, interference warning, estimated time until comms blackout

### Sensors & Scanning
- **Purpose**: Simulates environmental awareness — tracking orbital parameters, atmospheric density, radiation flux, and identifying safe aerobraking corridors
- **Key State**: Sensor mode, orbital parameter accuracy, atmospheric density readings at projected periapsis, radiation belt mapping, magnetosphere intensity, sensor degradation from radiation, aerobraking corridor identification
- **Player-facing**: Sensor board with atmospheric density overlay, radiation heat map, orbital parameter readouts, aerobraking corridor projections (if attempted), sensor static increasing with depth

### Atmosphere Management
- **Purpose**: Simulates internal air quality as rising heat stresses life support and potential hull compromise threatens pressure
- **Key State**: O2 level, CO2 level, internal pressure, recycler status, scrubber efficiency (degraded by heat), coolant leak risk, compartment seal status
- **Player-facing**: Air quality indicators, rising temperature warnings from life support, pressure alerts if hull integrity is compromised, compartment isolation options

### Habitat Integrity
- **Purpose**: Simulates structural stress on the hull from tidal forces, thermal expansion, and potential atmospheric contact
- **Key State**: Hull integrity per section, thermal stress accumulation, tidal flexing stress, seal status, microcrack propagation rate, structural failure thresholds, atmospheric friction ablation (if aerobraking)
- **Player-facing**: Hull stress diagram with color-coded sections, structural groaning audio cues, seal failure warnings, visible hull deformation near periapsis, ablation effects during atmospheric contact

## System Dependencies

### Hard Dependencies
- `Navigation & Fuel` --depends on--> `Equipment & Repair`: escape requires a functioning drive — the core repair-or-die dependency
- `Navigation & Fuel` --depends on--> `Attitude Control`: any burn requires correct ship orientation; attitude failure means uncontrolled thrust vector
- `Attitude Control` --depends on--> `Power Grid`: reaction control systems and gyroscopes require electrical power
- `Thermal Regulation` --depends on--> `Power Grid`: radiators and coolant pumps require power to operate
- `Atmosphere Management` --depends on--> `Power Grid`: recyclers and scrubbers are powered systems
- `Atmosphere Management` --depends on--> `Habitat Integrity`: atmosphere cannot be maintained if hull is breached
- `Communications` --depends on--> `Power Grid`: antenna and transmitter require power to broadcast

### Soft Dependencies
- `Equipment & Repair` ~~depends on~~> `Player Health`: heat-stressed and irradiated player works slower and makes more mistakes
- `Equipment & Repair` ~~depends on~~> `Sensors & Scanning`: drive diagnostics benefit from sensor data about component state
- `Player Health` ~~depends on~~> `Thermal Regulation`: rising heat degrades cognitive and physical function over time
- `Player Health` ~~depends on~~> `Atmosphere Management`: degraded air quality compounds heat stress effects
- `Sensors & Scanning` ~~depends on~~> `Power Grid`: sensor fidelity scales with allocated power, critical for aerobraking corridor identification
- `Communications` ~~depends on~~> `Sensors & Scanning`: knowing the magnetosphere density helps optimize transmission windows
- `Habitat Integrity` ~~depends on~~> `Thermal Regulation`: unmanaged thermal expansion accelerates structural stress and microcrack propagation
- `Navigation & Fuel` ~~depends on~~> `Sensors & Scanning`: orbital parameter accuracy depends on sensor quality; poor data means imprecise burn timing
- `Time Pressure` ~~depends on~~> `Navigation & Fuel`: all countdown timers derive from current trajectory and delta-v calculations

### Feedback Loops
- `Equipment & Repair` <-> `Time Pressure` <-> `Player Health`: Failed repairs consume time, shrinking the survival window. The shrinking window increases stress and heat exposure, degrading the player's ability to perform repairs — each failed attempt makes the next one harder
- `Thermal Regulation` <-> `Power Grid` <-> `Atmosphere Management`: Rising heat forces more power to radiators, starving life support. Degraded air quality compounds heat stress. All three systems compete for the same dwindling power budget as the reactor itself runs hotter
- `Navigation & Fuel` <-> `Attitude Control` <-> `Equipment & Repair`: Without the main drive, attitude thrusters become the only thrust source. Using them for braking depletes fuel needed for orientation. Poor orientation makes any future burn less efficient, demanding more fuel that no longer exists
- `Habitat Integrity` <-> `Thermal Regulation` <-> `Sensors & Scanning`: Tidal forces and thermal stress degrade hull integrity. Compromised hull sections lose insulation, increasing thermal load. Rising heat degrades sensor electronics, reducing the player's ability to identify which hull sections are most at risk

## Emergent Possibilities
- The player attempts a jury-rigged bypass of the drive coupling, and it holds — but the vibration from the damaged mount shakes loose a coolant line, flooding the engineering bay with superheated fluid and forcing a compartment evacuation mid-burn
- Desperate for thrust, the player vents remaining reaction mass through attitude jets in an uncontrolled emergency burn, only to realize the asymmetric thrust has induced a slow tumble that the depleted attitude system cannot correct — now they must repair the drive while the ship spins, the gas giant wheeling past the viewport every thirty seconds
- The player deliberately aims for a shallow aerobraking pass, using the atmosphere to slow down instead of fighting it, but misjudges the density profile — the ship skips off the upper atmosphere like a stone on water, buying time but flinging them into an elliptical orbit that will bring them back for a second, deeper pass they may not survive

## Inspiration
- *The Expanse* (James S.A. Corey) — realistic orbital mechanics, the Rocinante's emergency maneuvers, the terror of uncontrolled descent
- *Apollo 13* (film) — improvised repairs under impossible time pressure, jury-rigging with what you have
- *Gravity* (film) — the visceral dread of orbital decay and dwindling options
- *Kerbal Space Program* — the unforgiving math of delta-v budgets, the Oberth effect, and aerobraking gone wrong
