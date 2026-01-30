---
name: 5d-orient
description: "Pre-development orientation and assumption mapping for spec-driven development. Use when: (1) Starting a new feature or project, (2) User says 'let's build X' without prior analysis, (3) Beginning any 5D-SDD workflow, (4) User wants to 'think through' an idea before planning. This phase prevents wasted effort by surfacing hidden assumptions and identifying all relevant domains before committing to a direction."
---

# ORIENT Phase

Map the problem space before committing to a direction.

## Process

### 1. Domain Mapping (Width)

Ask: "What domains does this touch?"

Always consider:
- Technical (obvious)
- Business (value, stakeholders, ROI)
- Users (behavior, needs, friction)
- Operations (deployment, maintenance, monitoring)
- Design (interaction, experience)

Output a simple domain list with relevance notes.

### 2. Thinking Level Check (Depth)

Assess current thinking level:

| Level | Signs | Risk |
|-------|-------|------|
| Level 1 (Conformist) | "This is how it's always done" | Following patterns blindly |
| Level 2 (Individualist) | "My approach is right" | Dogmatic, closed to alternatives |
| Level 3 (Synthesist) | "Multiple approaches could work" | Can hold contradictions |

If stuck at Level 1-2, ask: "What would make a different approach correct?"

### 3. Skill Dependencies (Height)

Ask: "What capabilities must exist for this to succeed?"
- What skills does this require that we may lack?
- What domain knowledge unlocks other capabilities?
- Is progress blocked by underdevelopment elsewhere?

### 4. Quadrant Check

For each quadrant, surface one key question:

| Quadrant | Question to Answer |
|----------|-------------------|
| Individual Inner | What assumptions am I making? |
| Collective Inner | Who else has stakes? Do we share understanding? |
| Individual Outer | What concrete output will exist? |
| Collective Outer | What systems/constraints already exist? |

### 5. Time Context

Determine:
- Is this greenfield or evolution of existing?
- What must we "transcend and include" from current state?
- What's the trajectory—V1, V2, long-term vision?

### 6. Identity Check

Ask the user: "What are you most attached to about this idea?"

Flag this for later—attachment points become blind spots.

## Output Format

```
## Orientation Summary

**Domains involved:** [list]

**Key assumptions to validate:**
- [assumption 1]
- [assumption 2]

**Stakeholder alignment needed:** [yes/no, with whom]

**Existing constraints:** [systems, processes, dependencies]

**Attachment risk:** [what the user seems attached to]

**Ready for SPAR phase:** [yes/no]
```

## Exit Criteria

Proceed to SPAR when:
- At least 3 domains are mapped
- Key assumptions are explicit (not hidden)
- User acknowledges what they're attached to
