---
name: 5d-build
description: "Execute implementation tasks with quality and awareness. Use when: (1) After TASKS phase in 5D-SDD workflow, (2) Tasks are defined and sequenced, (3) User is ready to write code, (4) User asks to 'implement,' 'build,' or 'code' a task. This phase produces working code while maintaining connection to spec intent."
---

# BUILD Phase

Execute tasks while maintaining spec alignment and code quality.

## Build Principles

### Spec Fidelity

Before writing code, re-read the relevant spec section. After writing code, verify it matches spec.

Common drift patterns:
- Adding features not in spec ("while I'm here...")
- Simplifying away spec requirements
- Changing interfaces without updating spec

If drift is intentional: update spec first, then code.

### Level 3 Awareness

The implementation is one solution, not the only solution. Stay open to:
- Better approaches discovered during coding
- Spec errors revealed by implementation reality
- Edge cases the spec didn't anticipate

Flag these for VERIFY phase rather than silently changing.

### Domain Connection (Width)

While building, ask: "Does this still serve the business/user intent?"

Technical correctness ≠ solving the right problem.

### Quadrant Awareness

During implementation, check all perspectives:
- **Individual Outer:** Is the code artifact correct?
- **Individual Inner:** Do I understand what I'm building?
- **Collective Outer:** Does this integrate with existing systems?
- **Collective Inner:** Am I aligned with team/stakeholder expectations?

### Skill Dependencies (Height)

If blocked:
- Is this a code problem or a knowledge problem?
- What adjacent skill would unblock this?
- Should I pause to learn, or flag for help?

### Time Awareness

- Am I building on existing patterns (transcend and include)?
- Am I replacing something? Is deprecation handled?
- Am I creating future technical debt?

### Identity Trap

Watch for defensive coding:
- Adding complexity to avoid admitting spec issues
- Protecting assumptions rather than solving problems
- "It works" vs "it's right"

## Build Process

For each task:

1. **Read** the task description and done criteria
2. **Read** the relevant spec section
3. **Implement** the code
4. **Self-verify** against done criteria
5. **Note** any spec drift, discoveries, or concerns

## Quality Checks During Build

- Does it compile/run?
- Does it match the spec interface?
- Are error cases handled?
- Is it testable?
- Would you be comfortable debugging this at 3am?

## Output Per Task

```
## Task [N] Complete

**Status:** done / blocked / needs-spec-update

**Implementation notes:**
[Brief description of approach taken]

**Spec drift:**
[Any deviations from spec - intentional or discovered]

**Discoveries:**
[Edge cases, issues, or insights found during implementation]

**Ready for verify:** [yes/no]
```

## When to Pause

Stop building and escalate if:
- Spec is ambiguous or contradictory
- Implementation reveals spec error
- Complexity far exceeds estimate
- Blocked by unresolved dependency

Return to appropriate earlier phase rather than guessing.

## Exit Criteria

Proceed to VERIFY when:
- All tasks in current batch are complete
- Code runs without errors
- Self-verification passes
- Discoveries are documented
