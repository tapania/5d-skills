# 5D Spec-Driven Development Skills

A comprehensive suite of [Claude Code skills](https://docs.anthropic.com/en/docs/claude-code/skills) that implement the **5D Spec-Driven Development** methodology—a structured approach to building software that prevents wasted effort by ensuring understanding before commitment at every level.

## What Are Claude Code Skills?

Skills are extensions that teach Claude how to complete specific tasks in a repeatable, structured way. They consist of `SKILL.md` files containing instructions and workflows that Claude follows when invoked via `/skill-name` commands.

## The 5D Framework

The methodology is built on **five dimensions of thinking**:

| Dimension | Description |
|-----------|-------------|
| **Width** | Multiple domains (technical, business, user, ops, design) |
| **Depth** | Thinking levels (reactive → dogmatic → integrative → creative) |
| **Height** | Skill dependencies (what capabilities enable other capabilities) |
| **Quadrants** | Four perspectives (Individual/Collective × Inner/Outer) |
| **Time** | Evolution ("transcend and include" from current state) |

## Skills Overview

### Main Orchestrator

| Skill | Command | Description |
|-------|---------|-------------|
| **5d-sdd** | `/5d-sdd` | The complete methodology. Orchestrates the full workflow across all 10 phases from orientation to reflection. Use when starting a new project or feature that needs careful planning. |

### Foundational Thinking

| Skill | Command | Description |
|-------|---------|-------------|
| **5d-thinking** | `/5d-thinking` | Strategic multi-dimensional thinking framework for analysis and problem-solving. Apply 5D thinking to analyze problems, generate insights, and avoid cognitive blind spots. |

### The 10 Development Phases

```
UNDERSTAND          DESIGN              BUILD               LEARN
───────────────     ───────────────     ───────────────     ───────────
0. ORIENT           2. PLAN             6. TASKS            9. REFLECT
1. SPAR             3. REFINE           7. BUILD
                    4. SPEC             8. VERIFY
                    5. GAP ANALYSIS
```

| # | Phase | Command | What Happens | Output |
|---|-------|---------|--------------|--------|
| 0 | Orient | `/5d-orient` | Map domains, surface assumptions, identify stakeholders | Orientation Summary |
| 1 | Spar | `/5d-spar` | Challenge thinking through structured dialogue, find blind spots | SPAR Summary |
| 2 | Plan | `/5d-plan` | Crystallize into concrete plan with assumptions made explicit | `PLAN.md` |
| 3 | Refine | `/5d-refine` | Stress-test plan through adversarial review and edge cases | Refinement Summary |
| 4 | Spec | `/5d-spec` | Formalize technical specification with architecture decisions | `SPEC.md` |
| 5 | Gap Analysis | `/5d-gap-analysis` | Identify all required changes across all quadrants | Gap Analysis |
| 6 | Tasks | `/5d-tasks` | Sequence gaps into executable, right-sized tasks | Task List |
| 7 | Build | `/5d-build` | Implement with spec fidelity and quality awareness | Working code |
| 8 | Verify | `/5d-verify` | Multi-layer verification (technical, spec, plan, epistemic) | Verification Report |
| 9 | Reflect | `/5d-reflect` | Extract learning, identify process improvements | Retrospective |

## Installation

### Option 1: Project-Level (Recommended)

Copy the `skills/` directory to your project's `.claude/` folder:

```bash
cp -r skills/ your-project/.claude/skills/
```

### Option 2: Personal (All Projects)

Copy to your personal Claude Code skills directory:

```bash
cp -r skills/* ~/.claude/skills/
```

## Usage

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
| "I have an idea, let's explore it" | `/5d-orient` |
| "I know what I want, challenge my thinking" | `/5d-spar` |
| "We've discussed enough, write the plan" | `/5d-plan` |
| "Review this plan for issues" | `/5d-refine` |
| "Turn this plan into a technical spec" | `/5d-spec` |
| "What do we need to change?" | `/5d-gap-analysis` |
| "Break this into tasks" | `/5d-tasks` |
| "Implement this task" | `/5d-build` |
| "Check if this is working" | `/5d-verify` |
| "What did we learn?" | `/5d-reflect` |

### When to Skip Phases

- **Trivial changes**: Skip to `/5d-build`
- **Already planned**: Start at `/5d-spec` or `/5d-gap-analysis`
- **Bug fixes**: Start at `/5d-build`, but run `/5d-verify` thoroughly
- **Exploratory work**: `/5d-orient` and `/5d-spar` only

**Never skip VERIFY. Always close the loop.**

## Key Principles

### 1. No Commitment Without Understanding

Each phase deepens understanding before the next commitment:
- ORIENT → understand the space
- SPAR → understand objections
- PLAN → commit to direction
- REFINE → understand risks
- SPEC → commit to implementation
- BUILD → commit to code

### 2. Multi-Perspective Thinking (Quadrants)

Every phase checks multiple perspectives:

| Quadrant | Focus |
|----------|-------|
| Individual Outer | What artifacts exist? (code, components, interfaces) |
| Individual Inner | What understanding is needed? (skills, knowledge) |
| Collective Outer | What systems/constraints exist? (infrastructure, integrations) |
| Collective Inner | What alignment is needed? (stakeholders, team) |

### 3. Fail Fast, Route Correctly

When something fails, return to the appropriate phase:

| Failure Type | Return To |
|--------------|-----------|
| Code doesn't run | BUILD |
| Works but wrong output | BUILD or SPEC |
| Works but users confused | PLAN |
| Solves wrong problem | SPAR or ORIENT |

### 4. Identity Trap Awareness

**Why thinking stops:** Latching onto ideas as identity. When identity is threatened, the mind defends rather than explores.

**Counteract by:**
- Notice when you feel defensive—probe there
- Hold positions lightly
- Ask: "What would make me wrong?"

## Documents Produced

- `PLAN.md` - What we're building and why
- `SPEC.md` - How we're building it technically
- Task list - Sequenced implementation steps
- Verification report - What passed/failed
- Retrospective - What we learned

## Philosophy

Most development failures come from:
- Building before understanding
- Single-perspective thinking
- Hidden assumptions
- Spec drift from intent
- No feedback loops

5D-SDD addresses each through structured phases with explicit exit criteria, multi-dimensional analysis, and continuous verification loops.

## License

MIT
