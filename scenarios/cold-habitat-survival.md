# Scenario: Cold Habitat Survival

## Narrative
You wake in darkness. The air is thin and biting cold — your breath fogs in front of you, lit only by the faint amber pulse of an emergency beacon. The habitat is dead. Power cells drained, life support offline, thermal regulators silent. The walls are already frosting over.

You're alone in a small orbital habitat, and the cold is your most immediate enemy. Your extremities are going numb. You need to find a way to generate heat before hypothermia sets in — burning insulation foam, overloading a battery cell, anything. But warmth without oxygen is just a slower death. You need to triage: what comes back online first, what can wait, and what you can jury-rig from whatever's lying around.

Every system you restore draws from the same depleted reserves. Restart the heaters and you might not have enough charge to spin up the air recyclers. Get the air flowing but the thermal bleed through the hull might drain it faster than you can produce it. This habitat was never meant to run on fumes — but here you are.

## Setting
- **Location type**: habitat
- **Scale**: personal
- **Tone**: survival

## Player Agency
- Decide which systems to prioritize restoring (heat vs. air vs. power)
- Scavenge components from non-essential modules to jury-rig repairs
- Choose between safe, slow restoration or risky shortcuts (overloading cells, bypassing safeties)
- Decide whether to attempt signaling for help or focus entirely on self-sufficiency
- Manage personal condition — keep moving to stay warm, or conserve energy

## Resolution Paths
- **Best**: Methodically restore core systems, stabilize the habitat, signal for rescue or achieve self-sufficiency
- **Good**: Get life support barely functional — uncomfortable but alive, awaiting rescue
- **Mixed**: Survive by cannibalizing the habitat to the point it's no longer viable long-term — you live but the habitat is scrap
- **Bad**: Restore one system at the expense of another critical one — cascading failure
- **Worst**: Hypothermia or asphyxiation before any systems come online

## Required Simulation Systems

### Power Grid
- **Purpose**: Simulates electrical power generation, storage, distribution, and consumption across a habitat or vessel
- **Key State**: Total stored energy (kWh), generation rate, consumption rate per subsystem, distribution bus status, cell health/degradation
- **Player-facing**: Power readouts on panels, lights flickering or dead, systems refusing to start, battery indicators

### Thermal Regulation
- **Purpose**: Simulates heat generation, retention, and loss within enclosed spaces
- **Key State**: Ambient temperature per compartment, insulation integrity, heat source output, thermal bleed rate (to vacuum or exterior), radiator status
- **Player-facing**: Visible breath fog, frost on surfaces, numbness/hypothermia effects on player, thermostat displays

### Atmosphere Management
- **Purpose**: Simulates breathable air composition, recycling, and pressure within enclosed spaces
- **Key State**: O2 level, CO2 level, total pressure, recycler status, scrubber filter condition, leak rate
- **Player-facing**: Breathing difficulty, drowsiness (high CO2), pressure warnings, audible hissing from leaks

### Player Health
- **Purpose**: Tracks the player's physical condition and its effects on capability
- **Key State**: Core body temperature, blood oxygenation, fatigue, injury status, caloric reserves, hydration
- **Player-facing**: Visual effects (blurring, tunnel vision), movement speed changes, stamina limits, status indicators

### Equipment & Repair
- **Purpose**: Simulates the state of mechanical and electrical components and the ability to repair or jury-rig them
- **Key State**: Component health/wear, required parts for repair, tool availability, bypass feasibility, repair skill modifier
- **Player-facing**: Inspection results, repair interface, component scavenging, jury-rig success/failure

### Habitat Integrity
- **Purpose**: Simulates the structural condition of the habitat — hull, seals, compartments
- **Key State**: Hull integrity per section, seal status (doors, hatches, viewports), micrometeorite damage, structural stress
- **Player-facing**: Visible damage, breach warnings, compartment isolation options

### Communications
- **Purpose**: Simulates the ability to send and receive signals — distress calls, data, etc.
- **Key State**: Antenna status, power allocation, signal range, nearby receivers, interference
- **Player-facing**: Comms panel interface, static, signal strength indicator, response delays

## System Dependencies

### Hard Dependencies
- `Thermal Regulation` --depends on--> `Power Grid`: heaters and radiators require electrical power
- `Atmosphere Management` --depends on--> `Power Grid`: recyclers and scrubbers are powered systems
- `Communications` --depends on--> `Power Grid`: antenna and transmitter require power
- `Atmosphere Management` --depends on--> `Habitat Integrity`: atmosphere cannot be maintained if hull is breached

### Soft Dependencies
- `Player Health` ~~depends on~~> `Thermal Regulation`: prolonged cold degrades health but player can mitigate temporarily
- `Player Health` ~~depends on~~> `Atmosphere Management`: low O2 or high CO2 degrades health over time
- `Equipment & Repair` ~~depends on~~> `Player Health`: injured or hypothermic player repairs more slowly and makes more mistakes
- `Thermal Regulation` ~~depends on~~> `Habitat Integrity`: poor insulation increases thermal bleed but system still functions

### Feedback Loops
- `Player Health` <-> `Equipment & Repair`: Worse health means worse repairs, which means systems stay offline longer, which means health degrades further
- `Power Grid` <-> `Thermal Regulation` <-> `Atmosphere Management`: All three compete for the same limited energy — restoring one reduces availability for others

## Emergent Possibilities
- The player strips insulation from one compartment to patch another, unknowingly creating a thermal dead zone that later causes pipes to freeze and burst — cascading failure from a reasonable decision
- A jury-rigged battery overcharge generates enough heat to warm a small compartment, becoming an improvised heater at the cost of fire risk
- The player seals off damaged sections to conserve atmosphere, only to discover a critical tool or component was in the sealed area — forcing a risky depressurization retrieval

## Inspiration
- *The Martian* (Andy Weir) — methodical survival problem-solving
- *Gravity* (film) — isolation and cascading system failures in orbit
- *Barotrauma* (game) — submarine habitat management under pressure
