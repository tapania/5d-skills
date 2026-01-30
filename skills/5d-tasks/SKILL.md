---
name: 5d-tasks
description: "Break gap analysis into sequenced, actionable tasks. Use when: (1) After GAP ANALYSIS phase in 5D-SDD workflow, (2) User is ready to start implementation, (3) Gaps are identified but not yet organized into work items, (4) User asks for 'task list,' 'breakdown,' or 'what to do first.' This phase creates the implementation roadmap."
---

# TASKS Phase

Convert gaps into sequenced, executable tasks.

## Task Design Principles

### Right-Sized Tasks

Each task should be:
- Completable in one session
- Independently verifiable
- Clear in scope (no ambiguity about "done")

If you can't tell whether a task succeeded, it's too big or poorly defined.

### Task Types

Include all types, not just code:
- **Code tasks:** Implementation work
- **Research tasks:** Learning/investigation
- **Infrastructure tasks:** Environment/tooling setup
- **Alignment tasks:** Communication/review

### Dependency Ordering (Height + Time)

Sequence by:
1. Blockers first (tasks that unblock others)
2. Foundation before features (transcend and include)
3. Risky/unknown tasks early (fail fast)
4. Skill-building tasks before skill-requiring tasks
5. Independent tasks can parallelize

### Quadrant Balance

Ensure tasks cover all quadrants:
- **Code tasks** (Individual Outer)
- **Research tasks** (Individual Inner)
- **Infrastructure tasks** (Collective Outer)
- **Alignment tasks** (Collective Inner)

Don't over-index on code tasks while ignoring alignment needs.

### Thinking Level Check (Depth)

For complex tasks, note the thinking level required:
- Can this be solved with existing patterns (Level 1-2)?
- Does this require synthesizing contradictions (Level 3)?
- Does this require novel insight (Level 4)?

Flag Level 3-4 tasks as higher risk.

### Identity Trap Check

Watch for:
- Tasks being avoided because they challenge assumptions
- Tasks scoped to protect rather than solve
- Missing tasks that would reveal problems

## Task Format

For each task:

```
### Task [N]: [Title]

**Type:** code / research / infrastructure / alignment
**Depends on:** [task numbers or "none"]
**Complexity:** trivial / moderate / complex

**Description:**
[What to do - specific enough to execute]

**Done when:**
[Verification criteria - how to know it's complete]
```

## Sequencing Process

1. List all gaps from gap analysis
2. Convert each gap to one or more tasks
3. Identify dependencies between tasks
4. Order by dependency graph
5. Flag parallel tracks

## Output Format

```
## Task List

**Total tasks:** [count]
**Estimated sessions:** [rough count]

### Critical Path
[Tasks that must be sequential]

### Parallel Tracks
[Tasks that can happen simultaneously]

---

[Individual task entries in order]
```

## Exit Criteria

Proceed to BUILD when:
- All gaps map to tasks
- Dependencies are explicit
- First task is unblocked and ready
- User agrees with sequencing
