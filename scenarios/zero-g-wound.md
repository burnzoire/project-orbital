# Scenario: Zero-G Wound

## Narrative
You're bleeding. A jagged piece of hull shrapnel caught your side during a decompression event, and now globules of your own blood are drifting lazily through the compartment. In gravity, this would be bad. In zero-g, it's a death sentence of a different kind — blood doesn't pool and clot the same way when it has nowhere to settle. It drifts into your airways. It coats instruments. It's everywhere and nowhere at the same time.

The habitat's spin drum is offline. Without centripetal gravity, you can't get the blood to behave — can't keep your airway clear, can't apply pressure effectively, can't stop the slow crimson cloud growing around you. You need spin gravity back. The drum motor is functional but the spin-up sequence requires the attitude control system to compensate, and that needs thruster fuel you may or may not have.

Every second you spend working the problem, you're losing blood. Every drop that finds your lungs makes breathing harder. You're in a race between mechanical engineering and biology, and biology doesn't wait.

## Setting
- **Location type**: habitat
- **Scale**: personal
- **Tone**: survival

## Player Agency
- Prioritize: attempt wound treatment in zero-g or focus entirely on restoring spin
- Choose spin-up approach: full proper sequence (slower, safer) or emergency spin (faster, risks structural damage)
- Manage blood aspiration — positioning, improvised airway clearing
- Decide whether to use limited medical supplies now in zero-g (less effective) or save them for when gravity returns
- Attempt to seal the wound with available materials vs. proper medical treatment

## Resolution Paths
- **Best**: Restore spin gravity quickly, treat wound properly under gravity, full recovery
- **Good**: Emergency spin-up with minor structural consequences, wound treated adequately
- **Mixed**: Spin restored but wound treatment delayed — survive with lasting injury or reduced capacity
- **Bad**: Spin-up fails, forced to manage wound in zero-g with improvised solutions — survive but severely compromised
- **Worst**: Blood aspiration causes loss of consciousness before spin is restored

## Required Simulation Systems

### Rotational Gravity
- **Purpose**: Simulates centripetal artificial gravity via spin drums or rotating habitat sections
- **Key State**: Spin rate (RPM), effective gravity (fraction of g), spin-up/spin-down time, structural stress from rotation, balance/wobble
- **Player-facing**: Gradual weight return during spin-up, Coriolis effects at partial spin, objects settling, blood/fluid behavior changes

### Attitude Control
- **Purpose**: Simulates the orientation and stabilization of a habitat or vessel in space
- **Key State**: Angular momentum, thruster fuel reserves, gyroscope status, compensation requirements during spin changes, pointing accuracy
- **Player-facing**: Habitat drift or wobble, thruster firing sounds/vibrations, fuel gauge warnings

### Medical / Injury
- **Purpose**: Simulates wound types, bleeding, treatment, and recovery
- **Key State**: Wound location, severity, bleed rate, blood volume, clotting status, infection risk, treatment applied, consciousness threshold
- **Player-facing**: Blood loss visual effects, pain indicators, reduced capability, wound inspection interface, treatment options

### Fluid Dynamics (Micro-gravity)
- **Purpose**: Simulates how liquids (blood, water, fuel) behave in varying gravity conditions
- **Key State**: Gravity level, fluid volume and location, surface tension behavior, containment status, aspiration risk
- **Player-facing**: Floating blood globules, fluid behaving differently as gravity changes, splashing vs. drifting

### Player Health
- **Purpose**: Tracks the player's physical condition including blood volume, consciousness, and capability
- **Key State**: Blood volume/pressure, oxygen saturation, consciousness level, pain, stamina, respiratory status
- **Player-facing**: Screen darkening at low blood volume, labored breathing sounds, reduced movement speed, tunnel vision

### Power Grid
- **Purpose**: Electrical power generation, storage, and distribution
- **Key State**: Stored energy, generation rate, distribution status, load per subsystem
- **Player-facing**: System availability indicators, power allocation interface

### Habitat Integrity
- **Purpose**: Structural condition of habitat sections, especially under rotational stress
- **Key State**: Hull integrity, structural stress tolerance, seal status, spin-rated maximum RPM, damage from emergency procedures
- **Player-facing**: Creaking sounds during spin-up, structural warnings, visible deformation

## System Dependencies

### Hard Dependencies
- `Rotational Gravity` --depends on--> `Attitude Control`: spin-up requires thruster compensation to prevent tumbling
- `Rotational Gravity` --depends on--> `Power Grid`: spin motor requires electrical power
- `Attitude Control` --depends on--> `Power Grid`: thrusters and gyroscopes need power to operate
- `Fluid Dynamics` --depends on--> `Rotational Gravity`: fluid behavior is determined by current gravity level

### Soft Dependencies
- `Medical / Injury` ~~depends on~~> `Rotational Gravity`: treatment effectiveness varies dramatically with gravity level
- `Medical / Injury` ~~depends on~~> `Fluid Dynamics`: blood behavior affects wound management
- `Player Health` ~~depends on~~> `Medical / Injury`: untreated wounds degrade health over time
- `Habitat Integrity` ~~depends on~~> `Rotational Gravity`: excessive spin rate or emergency spin-up stresses structure

### Feedback Loops
- `Player Health` <-> `Medical / Injury`: Declining health reduces ability to perform treatment; untreated injury accelerates health decline
- `Player Health` <-> `Rotational Gravity`: Player needs gravity to treat wound, but must be conscious and capable enough to restore it
- `Rotational Gravity` <-> `Habitat Integrity`: Spin creates gravity but stresses structure; structural limits constrain maximum spin

## Emergent Possibilities
- The player begins spin-up but realizes at partial gravity that blood is now pooling dangerously on one side due to Coriolis effects — they must choose a specific position in the drum to let gravity help rather than hurt
- An emergency spin-up at maximum RPM restores gravity fast but causes a micro-fracture in a viewport seal — now they have gravity but a slow pressure leak to deal with
- Blood that drifted into electrical panels during zero-g causes a short circuit when gravity returns and it settles into the wiring — a delayed consequence of the initial crisis

## Inspiration
- *The Expanse* (James S.A. Corey) — realistic depiction of spin gravity and zero-g medical emergencies
- *Planetes* (manga/anime) — daily life and danger in orbital environments
- *Ad Astra* (film) — spinning station sequences
