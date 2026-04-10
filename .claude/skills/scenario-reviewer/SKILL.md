---
name: scenario-reviewer
description: Review all scenarios and synthesize their system requirements into a unified systems definition. Run repeatedly to refine the simulation specification.
---

# Scenario Reviewer

## Purpose
Review all scenarios in `/scenarios/` and synthesize their system requirements into a unified, canonical systems definition in `/simulation/systems.md`. Each invocation refines the definition — merging duplicates, resolving naming conflicts, discovering missing dependencies, and tracking which scenarios exercise each system.

## When to use
Use this skill after generating new scenarios, or at any time to refine the systems definition. Designed to be run repeatedly — it is idempotent and converges toward a complete simulation specification.

## Instructions

When invoked, follow these steps:

### 1. Read All Scenarios
Read every `.md` file in `/scenarios/`. Extract all referenced simulation systems, their descriptions, state variables, and dependency relationships.

### 2. Read Current Systems Definition
Read `/simulation/systems.md` if it exists. This is your baseline to refine.

### 3. Cross-Reference and Reconcile
For each system found across all scenarios:
- **Merge duplicates**: If two scenarios name the same concept differently (e.g., "Thermal Regulation" vs "Heat Management"), unify under one canonical name
- **Resolve conflicts**: If scenarios describe a system differently, synthesize the broader definition that satisfies all scenarios
- **Fill gaps**: If a system is implied but never explicitly named (e.g., scenarios mention "oxygen" but no one called out an "Atmosphere Composition" system), add it
- **Validate dependencies**: Ensure all dependency arrows point to systems that actually exist in the definition
- **Track coverage**: Note which scenarios exercise each system

### 4. Assess Maturity
Rate each system's definition maturity:
- **Draft**: Mentioned in 1 scenario, loosely defined
- **Developing**: Mentioned in 2+ scenarios, core purpose clear but details incomplete
- **Refined**: Well-defined across multiple scenarios, dependencies mapped, state variables enumerated
- **Final**: User has approved this system definition as complete

### 5. Identify Gaps and Recommendations
At the bottom of the systems definition, maintain a section noting:
- Systems that appear in only one scenario (may need more stress-testing)
- Dependency chains that seem incomplete
- Potential systems not yet surfaced by any scenario
- Recommended next scenarios to generate (to exercise under-tested systems)

## Output Format

Update `/simulation/systems.md` using this structure:

```markdown
# Simulation Systems Definition
> Last reviewed: <date>
> Scenarios analyzed: <count>

## Systems Overview
| System | Category | Maturity | Scenario Coverage |
|--------|----------|----------|-------------------|
| <name> | <category> | <Draft/Developing/Refined/Final> | <scenario slugs> |

---

## System Definitions

### <System Name>
- **Category**: <Physical | Biological | Social | Economic | Political | Technical>
- **Maturity**: <Draft | Developing | Refined | Final>
- **Purpose**: <what this system simulates>
- **Key State Variables**:
  - `<variable>`: <type> — <description>
- **Player-Facing Effects**:
  - <how the player observes or interacts with this system>
- **Exercised By**: <list of scenario slugs>

<repeat for each system, alphabetically>

---

## Dependency Map

### Hard Dependencies
<System A> --> <System B>: <reason>

### Soft Dependencies
<System A> ~~> <System B>: <reason>

### Feedback Loops
<System A> <-> <System B>: <description>

---

## Analysis & Recommendations

### Under-Tested Systems
<Systems appearing in only 1 scenario>

### Potential Missing Systems
<Systems implied but not yet defined>

### Incomplete Dependency Chains
<Dependency paths that seem to have gaps>

### Recommended Next Scenarios
<Scenario concepts that would exercise under-tested or missing systems>
```

## Important Notes
- Preserve any system marked as **Final** — do not modify its definition unless the user explicitly asks
- When merging systems, prefer the more specific and detailed definition
- Always update the "Last reviewed" date and scenario count
- Keep system names concise but descriptive — these become the vocabulary for the entire project
- The dependency map should be the UNION of all dependencies found across all scenarios
- If you notice a system that no scenario actually needs, flag it for potential removal rather than silently dropping it
- The recommendations section is critical — it drives the iterative loop of generating more scenarios to refine the systems
