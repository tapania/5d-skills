---
name: 5d-refine
description: "Stress-test the plan through adversarial review and edge case analysis. Use when: (1) After PLAN phase in 5D-SDD workflow, (2) User wants to 'validate,' 'review,' or 'check' a plan, (3) Before committing significant resources to implementation, (4) Plan exists but hasn't been challenged. This phase catches plan-level errors before they become code-level errors."
---

# REFINE Phase

Stress-test the plan before committing to specification.

## Stress Test Methods

### 1. Inversion Attack

Argue against the plan:
- "Here's why this will fail: [reasons]"
- "The hidden dependencies are: [list]"
- "This assumes X, but what if X is false?"

Force the user to defend or amend.

### 2. Edge Case Probing

For each core behavior, ask:
- "What happens when [unusual input]?"
- "What if [dependency] is unavailable?"
- "How does this behave at [scale extreme]?"

Document answers or flag as "needs resolution."

### 3. Stakeholder Simulation

Roleplay different perspectives:

**Skeptical Engineer:** "This seems over-engineered. Why not just [simpler approach]?"

**Impatient PM:** "When will this ship? What's the MVP?"

**Confused User:** "I don't understand how to [core action]."

**Ops On-Call:** "How do I debug this at 3am?"

### 4. Dependency Audit (Height)

List everything the plan depends on:
- External services
- Team knowledge/skills (what capabilities must exist?)
- User behaviors
- Business conditions
- Adjacent domain skills that might block progress

Rate each: stable / risky / unknown

### 5. Quadrant Stress Test

Probe each quadrant for weaknesses:

| Quadrant | Stress Question |
|----------|-----------------|
| Individual Inner | "What understanding gaps exist?" |
| Collective Inner | "Where might stakeholders disagree?" |
| Individual Outer | "What artifacts are under-specified?" |
| Collective Outer | "What system constraints are ignored?" |

### 6. Time Trajectory Check

- "How have similar plans failed historically?"
- "What's changing in this domain that affects the plan?"
- "Does this plan transcend and include current approaches, or just replace them?"

### 7. Level Check (Depth)

Ask yourself: Is refinement improving the plan, or is the user defending their original idea with better words?

Signs of defensive refinement:
- Adding complexity to protect core assumptions
- Dismissing objections rather than addressing them
- "That won't happen" without evidence

If defensive: return to SPAR.

## Output Format

```
## Refinement Summary

**Stress tests passed:**
- [test]: [how addressed]

**Edge cases documented:**
- [case]: [planned handling]

**Dependency risks:**
- [dependency]: [risk level] - [mitigation]

**Plan amendments:**
- [change made based on refinement]

**Unresolved issues:**
- [issue]: [why deferred / needs more info]

**Ready for SPEC phase:** [yes/no]
```

## Exit Criteria

Proceed to SPEC when:
- Major objections have responses (not dismissals)
- Edge cases are documented (even if handling is "error out")
- No high-risk dependencies without mitigation
- Plan text has been updated with refinements
