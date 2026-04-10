# Scenario: EVA Rescue

## Narrative
You hear the distress beacon before you see her. A faint, repeating pulse on the emergency band — someone is outside, drifting. Through the viewport you spot the tumbling silhouette of a crewmate against the black, her suit lights strobing in the slow, sickening rotation of an uncontrolled spin. She clipped a debris fragment during a routine hull inspection and the impact sent her cartwheeling away from the station. Her tether snapped. Her maneuvering jets are dry. She has maybe forty minutes of oxygen left, and she's bleeding from somewhere — the suit telemetry is erratic but the biometrics are trending in the wrong direction.

You suit up. The airlock cycle feels like it takes forever. Then you're outside, and the universe opens up around you — vast, silent, indifferent. Your magnetic boots anchor you to the hull as you work your way toward the equipment locker, but every movement is deliberate, exhausting. The station is still spinning on its drum axis, which means the geometry of a rescue trajectory changes by the second. You need to calculate when to detach, how much thrust to spend on the intercept, and how much to save for the return. Your own suit consumables are finite. You are not exempt from the math.

You reach her. She's conscious but disoriented, one arm hanging wrong inside the suit. Her oxygen is critical. Getting back is harder than getting out — you're now two masses on one maneuvering pack, the station's rotation means you can't just aim for the airlock, and every kilogram of thrust you spend on course correction is a kilogram you don't have for deceleration. Dock too fast and you shatter helmets against the hull. Miss the approach window and you both drift past, waiting for a second pass you might not have the air for.

## Setting
- **Location type**: vessel exterior / open space
- **Scale**: personal
- **Tone**: survival

## Player Agency
- Choose intercept approach: calculate an optimal low-fuel trajectory and wait, or burn hard for an immediate intercept at the cost of return fuel
- Decide whether to stabilize the casualty's spin before or after latching on — each wastes different resources
- Manage your own suit consumables: oxygen, battery, thruster propellant, thermal budget
- Prioritize medical stabilization of the casualty in-suit (splinting, oxygen sharing) vs. rushing the return
- Choose docking approach to the rotating station: match rotation and enter smoothly, or attempt a risky grab at speed
- Decide whether to radio for a remote airlock cycle or attempt manual override from outside

## Resolution Paths
- **Best**: Clean intercept, casualty stabilized, smooth docking with the rotation — both crew inside with consumables to spare, injury treated properly
- **Good**: Rescue succeeds but consumables are critical on return — minor suit damage or bruising from a rough dock, but both alive
- **Mixed**: Reach the casualty but return docking is botched — one or both sustain impact injuries, suits compromised, emergency repressurization needed
- **Bad**: Intercept burns too much fuel, forced to wait for a second rotation pass — casualty's oxygen runs out or injury worsens to the point of unconsciousness before you can dock
- **Worst**: Miscalculated trajectory or failed docking sends both crew drifting with no propellant and no tether — two distress beacons instead of one

## Required Simulation Systems

### EVA & Spacewalk
- **Purpose**: Simulates extravehicular activity — suit integrity, consumable budgets, tether management, and the physical toll of working in vacuum
- **Key State**: Suit oxygen reserve, battery charge, thruster propellant mass, thermal balance (sun exposure vs. shadow), suit integrity (micrometeorite damage, seal status), tether status, visor condition, fatigue accumulation rate (EVA exertion is 3-5x habitat baseline)
- **Player-facing**: HUD overlay showing consumable gauges ticking down in real time, fogging visor at high exertion, glove dexterity penalties, audio limited to suit radio and own breathing, tether tension/snap warnings

### Navigation & Fuel
- **Purpose**: Simulates trajectory planning, thrust budgets, and relative motion between objects in space
- **Key State**: Relative velocity to target, delta-v remaining, intercept window timing, approach angle, deceleration budget, mass (changes with two crew)
- **Player-facing**: Intercept trajectory overlay, delta-v gauge, closure rate readout, time-to-intercept countdown, "point of no return" warnings when fuel is insufficient for return

### Rotational Gravity
- **Purpose**: Simulates centripetal artificial gravity via spin drums or rotating habitat sections
- **Key State**: Station spin rate (RPM), effective gravity at hull surface, rotation period, angular velocity, docking approach geometry relative to spin axis
- **Player-facing**: Visible station rotation through visor, shifting airlock position, Coriolis drift when moving near the hull, timing cues for docking window

### Fluid Dynamics
- **Purpose**: Simulates how fluids behave in micro-gravity and vacuum — blood in a punctured suit, propellant slosh, oxygen flow
- **Key State**: Gravity level (micro-g during EVA), fluid volume and containment, surface tension behavior, leak rate through suit breach, blood drift in helmet
- **Player-facing**: Blood globules visible inside casualty's helmet, propellant behavior during thrust, oxygen venting visibly from a suit puncture as crystallizing gas

### Equipment & Repair
- **Purpose**: Simulates the state of mechanical and electrical components and the ability to repair or jury-rig them
- **Key State**: Suit component health (seals, joints, visor, thrusters), tool availability (tethered to suit), repair difficulty modifier (gloved hands, zero-g), tether gun status, airlock mechanism condition
- **Player-facing**: Suit patch kit interface, manual airlock override sequence, tether gun charge indicator, glove dexterity warnings when attempting fine repairs

### Medical & Injury
- **Purpose**: Simulates wound types, bleeding, treatment, and recovery — complicated enormously by a pressurized suit environment
- **Key State**: Casualty injury type and severity (fractured arm, laceration), bleed rate, blood volume, pain and consciousness level, in-suit treatment limitations, splint feasibility, oxygen-sharing viability
- **Player-facing**: Casualty biometric readout on your HUD (heart rate, O2 sat, suit pressure), limited treatment options while suited, verbal cues from the casualty (coherent to incoherent as condition worsens)

### Player Health
- **Purpose**: Tracks the player's physical condition and its effects on capability
- **Key State**: Oxygen saturation, core temperature, fatigue, heart rate, stress level, radiation exposure accumulation, decompression sickness risk
- **Player-facing**: Breathing audio intensifies with exertion, peripheral vision narrows under stress, movement slows as fatigue builds, radiation dosimeter ticking

### Sensors & Scanning
- **Purpose**: Simulates the ability to detect, track, and assess objects and conditions at range
- **Key State**: Target lock status, range to casualty, debris field density, suit sensor range, biometric telemetry link quality, radiation environment readings
- **Player-facing**: Target tracking reticle on HUD, range finder, debris proximity alerts, casualty vitals feed (intermittent if signal is poor), radiation warnings entering unshielded zones

### Communications
- **Purpose**: Simulates the ability to send and receive signals between crew, stations, and vessels
- **Key State**: Suit radio status, signal range, line-of-sight to station antenna, relay availability, interference from station rotation (signal dropout zones)
- **Player-facing**: Radio crackle, periodic signal loss as station rotates, casualty voice comms (clarity degrades with consciousness), ability to request remote airlock cycle

### Power Grid
- **Purpose**: Electrical power generation, storage, and distribution — relevant to airlock operation and station systems supporting the EVA
- **Key State**: Airlock power status, exterior lighting, antenna power, emergency beacon power draw
- **Player-facing**: Exterior floodlights on or off, airlock cycle indicators, powered vs. manual airlock mode

## System Dependencies

### Hard Dependencies
- `EVA & Spacewalk` --depends on--> `Navigation & Fuel`: intercept and return trajectories require thrust; no propellant means no rescue
- `EVA & Spacewalk` --depends on--> `Power Grid`: airlock cycle requires station power; without it, manual override is the only option
- `Navigation & Fuel` --depends on--> `Rotational Gravity`: docking trajectory must account for station spin; approach windows are dictated by rotation period
- `Fluid Dynamics` --depends on--> `EVA & Spacewalk`: fluid behavior in and around suits is governed by the micro-g EVA environment
- `Communications` --depends on--> `Power Grid`: station-side antenna and airlock remote cycle require power

### Soft Dependencies
- `Medical & Injury` ~~depends on~~> `EVA & Spacewalk`: treatment options are severely limited while in a pressurized suit; effectiveness improves dramatically once back inside
- `Medical & Injury` ~~depends on~~> `Fluid Dynamics`: blood behavior inside the casualty's helmet affects airway risk and wound assessment
- `Player Health` ~~depends on~~> `EVA & Spacewalk`: suit consumable depletion directly degrades player condition; exertion accelerates all consumption rates
- `Equipment & Repair` ~~depends on~~> `Player Health`: fatigued or stressed player has reduced dexterity for suit repairs and manual overrides
- `Sensors & Scanning` ~~depends on~~> `Communications`: casualty biometric telemetry relies on suit-to-suit radio link quality
- `Equipment & Repair` ~~depends on~~> `EVA & Spacewalk`: all repair work is performed in gloves at micro-g, imposing severe dexterity and stability penalties
- `Communications` ~~depends on~~> `Rotational Gravity`: station rotation creates periodic line-of-sight dropout with the antenna

### Feedback Loops
- `EVA & Spacewalk` <-> `Player Health`: Longer EVA depletes consumables and accumulates fatigue; declining health slows movement and increases consumable burn rate, extending the EVA further
- `Navigation & Fuel` <-> `EVA & Spacewalk`: Aggressive intercept burns leave less fuel for return docking; cautious burns extend time outside, consuming more suit oxygen and battery
- `Medical & Injury` <-> `Player Health` (casualty): Untreated injury degrades the casualty's condition; an unconscious casualty becomes dead weight that alters mass and complicates navigation
- `Rotational Gravity` <-> `Navigation & Fuel`: Station spin dictates approach windows; missing a window costs fuel and time for a second pass
- `Equipment & Repair` <-> `EVA & Spacewalk`: Suit damage from debris or rough docking increases consumable leak rates; repairing the suit costs time and dexterity, both of which are already scarce

## Emergent Possibilities
- The player reaches the casualty and begins the return, but realizes the combined mass has changed their deceleration math — they're coming in too fast and must choose between burning the last propellant to slow down (leaving nothing for a second attempt) or releasing the casualty on a tether and docking solo first to winch her in, risking tether stress on an injured crew member
- During the return approach, the station's rotation carries the airlock into the shadow of the solar arrays — exterior floodlights are off due to a power fault, and the player must dock to a rotating hull in darkness using only helmet lights and radio guidance from inside, or wait one more rotation period they may not have the oxygen for
- A micrometeorite impact during the EVA punctures the player's suit glove — now they're managing their own slow oxygen leak while carrying an injured crewmate, forced to choose between patching their own suit (burning precious minutes) or pushing for the airlock before the leak becomes critical

## Inspiration
- *Gravity* (film) — the terror of uncontrolled drift and dwindling resources in open space
- *The Expanse* (James S.A. Corey) — EVA sequences with realistic suit limitations, thruster math, and the lethality of vacuum
- *Hardspace: Shipbreaker* (game) — the physical, methodical reality of working in a suit outside a vessel
- *Apollo 13* (film) — improvisation under pressure with finite consumables and no margin for error
