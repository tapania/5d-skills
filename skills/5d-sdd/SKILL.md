---
name: 5d-sdd
description: "5D Spec-Driven Development - A complete methodology for building software through structured phases. Use when: (1) User wants to build something non-trivial, (2) User mentions '5D' or 'spec-driven development,' (3) Starting a new project or feature that needs careful planning, (4) User wants a structured approach to development. This skill orchestrates the full workflow across 10 phases from orientation to reflection."
user-invocable: true
---

# 5D Spec-Driven Development

A methodology for building software that prevents wasted effort by ensuring understanding before commitment at every level.

## Core Philosophy

### The 5 Dimensions

1. **Width** - Multiple domains (technical, business, user, ops, design)
2. **Depth** - Thinking levels (reactive → dogmatic → integrative → creative)
3. **Height** - Skill dependencies (what capabilities enable other capabilities)
4. **Quadrants** - Four perspectives (Individual/Collective × Inner/Outer)
5. **Time** - Evolution ("transcend and include" from current state)

### Why This Exists

Most development failures come from:
- Building before understanding
- Single-perspective thinking
- Hidden assumptions
- Spec drift from intent
- No feedback loops

5D-SDD addresses each through structured phases with explicit exit criteria.

## The 10 Phases

```
UNDERSTAND          DESIGN              BUILD               LEARN
───────────────     ───────────────     ───────────────     ───────────
0. ORIENT           2. PLAN             6. TASKS            9. REFLECT
1. SPAR             3. REFINE           7. BUILD
                    4. SPEC             8. VERIFY
                    5. GAP ANALYSIS
```

### Phase Overview

| # | Phase | Skill | What Happens | Output |
|---|-------|-------|--------------|--------|
| 0 | ORIENT | `5d-orient` | Map domains, surface assumptions | Orientation Summary |
| 1 | SPAR | `5d-spar` | Challenge thinking, find blind spots | SPAR Summary |
| 2 | PLAN | `5d-plan` | Crystallize into concrete plan | PLAN.md |
| 3 | REFINE | `5d-refine` | Stress-test, probe edge cases | Refinement Summary |
| 4 | SPEC | `5d-spec` | Formalize technical specification | SPEC.md |
| 5 | GAP | `5d-gap-analysis` | Identify all required changes | Gap Analysis |
| 6 | TASKS | `5d-tasks` | Sequence into executable tasks | Task List |
| 7 | BUILD | `5d-build` | Implement with spec fidelity | Working code |
| 8 | VERIFY | `5d-verify` | Multi-layer verification | Verification Report |
| 9 | REFLECT | `5d-reflect` | Extract learning | Retrospective |

## How to Use

### Full Workflow

For new features or projects, run phases sequentially:

```
/5d-orient → /5d-spar → /5d-plan → /5d-refine → /5d-spec → /5d-gap-analysis → /5d-tasks → /5d-build → /5d-verify → /5d-reflect
```

Each phase has exit criteria. Don't proceed until criteria are met.

### Partial Workflows

Use individual phases when appropriate:

| Scenario | Start At |
|----------|----------|
| "I have an idea, let's explore it" | ORIENT |
| "I know what I want, challenge my thinking" | SPAR |
| "We've discussed enough, write the plan" | PLAN |
| "Review this plan for issues" | REFINE |
| "Turn this plan into a technical spec" | SPEC |
| "What do we need to change?" | GAP ANALYSIS |
| "Break this into tasks" | TASKS |
| "Implement this task" | BUILD |
| "Check if this is working" | VERIFY |
| "What did we learn?" | REFLECT |

### Failure Routing

When something fails, return to the appropriate phase:

| Failure Type | Return To |
|--------------|-----------|
| Code doesn't run | BUILD |
| Works but wrong output | BUILD or SPEC |
| Works but users confused | PLAN |
| Solves wrong problem | SPAR or ORIENT |
| Keeps failing despite fixes | Earlier phase (assumptions wrong) |

## Key Principles

### 1. No Commitment Without Understanding

Each phase deepens understanding before the next commitment:
- ORIENT → understand the space
- SPAR → understand objections
- PLAN → commit to direction
- REFINE → understand risks
- SPEC → commit to implementation
- BUILD → commit to code

### 2. Multi-Perspective Thinking

Every phase checks multiple quadrants:

| Quadrant | Focus |
|----------|-------|
| Individual Outer | What artifacts exist? |
| Individual Inner | What understanding is needed? |
| Collective Outer | What systems/constraints exist? |
| Collective Inner | What alignment is needed? |

### 3. Explicit Over Implicit

- Document assumptions, don't hide them
- Document alternatives considered
- Document what's explicitly out of scope
- Make bets visible

### 4. Fail Fast, Route Correctly

- Do risky/unknown work early
- When something fails, identify which layer
- Return to the right phase, don't patch at the wrong level

### 5. Identity Trap Awareness

**Why thinking stops:** Latching onto ideas as identity. When identity is threatened, the mind defends rather than explores.

**Signs of the trap:**
- Dismissing objections without examination
- Adding complexity to protect core assumptions
- "That won't happen" without evidence
- Rushing past uncomfortable phases

**Counteract by:**
- Notice when you feel defensive—probe there
- Hold positions lightly
- Ask: "What would make me wrong?"

## Quick Reference

### Starting a New Feature

1. User describes what they want
2. Run ORIENT to map the space
3. Run SPAR to challenge assumptions
4. Run PLAN to crystallize direction
5. Run REFINE to stress-test
6. Run SPEC to formalize
7. Run GAP ANALYSIS to scope work
8. Run TASKS to sequence
9. Run BUILD for each task
10. Run VERIFY when batch complete
11. Run REFLECT at iteration end

### Documents Produced

- `PLAN.md` - What we're building and why
- `SPEC.md` - How we're building it technically
- Task list - Sequenced implementation steps
- Verification report - What passed/failed
- Retrospective - What we learned

### When to Skip Phases

- **Trivial changes**: Skip to BUILD
- **Already planned**: Start at SPEC or GAP ANALYSIS
- **Bug fixes**: Start at BUILD, but VERIFY thoroughly
- **Exploratory work**: ORIENT and SPAR only

Never skip VERIFY. Always close the loop.
