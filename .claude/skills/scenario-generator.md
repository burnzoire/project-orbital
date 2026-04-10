# Scenario Generator

## Purpose
Generate rich, detailed player experience scenarios for the Project Orbital space life simulation. Each scenario describes a situation a player might find themselves in, then decomposes it into the simulation systems and dependencies required to make that scenario emerge naturally — without bespoke scripting.

## When to use
Use this skill when the user wants to create a new scenario, either from a prompt they provide or by drawing inspiration from sci-fi literature, film, and games.

## Instructions

When invoked, follow these steps:

### 1. Develop the Scenario
Take the user's prompt (or generate an original concept if none provided) and expand it into a vivid, grounded scenario. Consider:
- **Setting**: Where does this take place? (habitat, ship, station, planet surface, deep space...)
- **Stakes**: What does the player stand to gain or lose?
- **Agency**: What meaningful choices can the player make?
- **Escalation**: How can the situation evolve or worsen?
- **Resolution paths**: Multiple ways this could end (not just success/failure)

Draw from hard sci-fi principles. Favor scenarios that feel emergent rather than scripted — things that could happen because systems interact, not because a quest trigger fired.

### 2. Decompose into Required Systems
Identify every simulation system that must exist for this scenario to occur naturally. For each system, describe:
- **What it simulates**: Core purpose and scope
- **Key state variables**: What data does it track?
- **Player-facing effects**: How does the player observe or interact with it?

### 3. Map Dependencies
Show how systems connect. Use the format:
```
[System A] --depends on--> [System B]: reason
```
Identify:
- **Hard dependencies**: System cannot function without the other
- **Soft dependencies**: System is influenced by but can operate without the other
- **Feedback loops**: Systems that mutually influence each other

### 4. Identify Emergent Behaviors
Describe 2-3 situations that could arise from the interaction of these systems that weren't explicitly designed — emergent gameplay moments.

## Output Format

Write the output as a markdown file saved to `/scenarios/<slug>.md` using this structure:

```markdown
# Scenario: <Title>

## Narrative
<2-3 paragraphs describing the scenario from the player's perspective, present tense, second person>

## Setting
- **Location type**: <habitat | ship | station | surface | deep space | port>
- **Scale**: <personal | local | regional | system-wide>
- **Tone**: <survival | social | political | economic | exploration | combat>

## Player Agency
<Bulleted list of meaningful choices the player can make>

## Resolution Paths
<Bulleted list of possible outcomes, from best to worst>

## Required Simulation Systems

### <System Name>
- **Purpose**: <what it simulates>
- **Key State**: <variables tracked>
- **Player-facing**: <how player sees/interacts with it>

<repeat for each system>

## System Dependencies

### Hard Dependencies
<list using arrow notation>

### Soft Dependencies
<list using arrow notation>

### Feedback Loops
<list with description>

## Emergent Possibilities
<2-3 unscripted moments that could arise from system interactions>

## Inspiration
<Optional: sci-fi works that inspired this scenario>
```

## Important Notes
- Be thorough in system decomposition — err on the side of identifying too many systems rather than too few
- Think about what must be true about the simulation's background processes for this moment to arise organically
- Name systems consistently across scenarios (check existing scenarios in /scenarios/ first for naming conventions)
- Every scenario should stress-test at least one system that other scenarios don't
