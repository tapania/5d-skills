---
name: 5d-gap-analysis
description: "Analyze the gap between current state and specification to identify all required changes. Use when: (1) After SPEC phase in 5D-SDD workflow, (2) Spec exists and implementation is about to begin, (3) User asks 'what needs to change' or 'what's the delta,' (4) Assessing scope of work. This phase prevents surprise discoveries during implementation."
user-invocable: true
---

# GAP ANALYSIS Phase

Identify everything that must change to implement the spec.

## Multi-Quadrant Gap Analysis

### 1. Code Gaps (Individual Outer)

Compare spec to current implementation:
- New components needed
- Existing components requiring modification
- Components to deprecate/remove
- New dependencies to add

Output: List of concrete code changes.

### 2. Knowledge Gaps (Individual Inner)

Identify what must be learned:
- Unfamiliar technologies in spec
- Domain knowledge needed
- Patterns/approaches to research

Output: Learning tasks before or during implementation.

### 3. System Gaps (Collective Outer)

Identify infrastructure/tooling needs:
- New services or environments
- CI/CD changes
- Monitoring/observability additions
- Database migrations

Output: Infrastructure tasks.

### 4. Alignment Gaps (Collective Inner)

Identify communication needs:
- Stakeholders who need to review spec
- Teams affected by changes
- Documentation updates needed
- Training or handoff required

Output: Alignment tasks.

## Gap Assessment Process

1. **Read the spec thoroughly**
2. **Examine current codebase** (if exists)
3. **For each spec item:** Does current state satisfy it? If no, document the gap.
4. **Categorize gaps** by quadrant
5. **Estimate complexity** for each gap: trivial / moderate / complex / unknown

## Additional 5D Checks

### Thinking Level Gaps (Depth)

- Are any gaps caused by Level 2 (dogmatic) thinking in the spec?
- Do gaps require Level 3+ thinking to resolve (holding contradictions)?
- Where might we be defending assumptions rather than solving problems?

### Skill Dependency Gaps (Height)

- What capabilities are missing that block multiple gaps?
- Which gap, if resolved, would unlock others?
- What learning is prerequisite to implementation?

### Time Pattern Gaps

- What historical patterns predict where gaps will appear?
- Are we repeating mistakes from past projects?
- What must we "transcend and include" from current approaches?

### Identity Trap Gaps

- Are any gaps being minimized because they threaten core assumptions?
- What gaps are we avoiding looking at closely?

## Output Format

```
## Gap Analysis

### Code Gaps
| Gap | Spec Item | Complexity | Notes |
|-----|-----------|------------|-------|
| [gap] | [ref] | [level] | [notes] |

### Knowledge Gaps
- [topic]: [why needed] - [how to address]

### System Gaps
- [gap]: [what's needed]

### Alignment Gaps
- [gap]: [who/what]

### Unknowns
- [unknown]: [how to resolve]

**Total gaps:** [count]
**High-complexity gaps:** [count]
**Blockers:** [any gaps that block others]
```

## Exit Criteria

Proceed to TASKS when:
- All spec items have been assessed
- No "unknown" complexity items remain unaddressed
- Blockers are identified
- User has reviewed gap scope
