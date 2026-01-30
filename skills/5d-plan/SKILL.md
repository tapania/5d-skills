---
name: 5d-plan
description: "Convert expanded thinking into a concrete, multi-perspective plan. Use when: (1) After SPAR phase in 5D-SDD workflow, (2) User is ready to define what will be built, (3) User asks to 'write up the plan' or 'document what we're building,' (4) Transitioning from exploration to commitment. This phase creates the authoritative description of intent before technical specification."
user-invocable: true
---

# PLAN Phase

Crystallize sparring outcomes into a concrete plan.

## Plan Structure

### 1. Problem Statement

One paragraph. What problem does this solve? For whom? Why now?

Avoid: Solution-focused framing. This section is about the problem, not the answer.

### 2. Proposed Solution

Describe what will exist that doesn't exist now. Use plain language—no technical jargon yet.

Include:
- Core functionality (what it does)
- Key behaviors (how it works from user perspective)
- Boundaries (what it explicitly won't do)

### 3. Assumptions & Bets

Make implicit assumptions explicit:

```
We assume:
- [assumption about users]
- [assumption about technical feasibility]
- [assumption about business value]

We are betting that:
- [bet 1 - what we're gambling on]
- [bet 2]

Identity attachment risk:
- [what we might be defending rather than evaluating]
```

### 4. Thinking Level Declaration (Depth)

Acknowledge current thinking level:
- Are we at Level 2 (dogmatic—"this is the right way")?
- Can we articulate why alternative approaches might be valid (Level 3)?
- What novel insight does this plan contain (Level 4)?

### 5. Skill Dependencies (Height)

Document what capabilities the plan requires:
- What skills must the team have or acquire?
- What domain knowledge unlocks implementation?
- What's blocking progress that's outside this plan's scope?

### 6. Alternatives Considered

Document what was rejected and why:

| Alternative | Why Rejected |
|-------------|--------------|
| [option A] | [reason] |
| [option B] | [reason] |

This prevents re-litigating decisions later.

### 7. Quadrant Coverage

Ensure plan addresses all four:

| Quadrant | Plan Element |
|----------|--------------|
| Individual Outer | What artifacts will be created |
| Individual Inner | What understanding/skills are required |
| Collective Outer | How this fits existing systems |
| Collective Inner | What alignment is needed across stakeholders |

### 8. Time Horizons

- **V1 (this iteration):** [scope]
- **V2 (next iteration):** [deferred scope]
- **Explicitly not planned:** [out of scope]

## Output Format

Produce a standalone document titled `PLAN.md` with the sections above.

Keep it under 500 words. Plans that require more are actually multiple plans.

## Exit Criteria

Proceed to REFINE when:
- All sections are complete
- User confirms plan matches their intent
- No major gaps in quadrant coverage
