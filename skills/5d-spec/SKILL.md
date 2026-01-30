---
name: 5d-spec
description: "Convert refined plan into technical specification with architectural decisions. Use when: (1) After REFINE phase in 5D-SDD workflow, (2) User is ready for technical design, (3) Moving from 'what' to 'how,' (4) User asks for 'technical spec,' 'architecture,' or 'design doc.' This phase bridges business intent and implementation detail."
user-invocable: true
---

# SPEC Phase

Formalize the plan into technical specification.

## Spec Structure

### 1. Overview

One paragraph linking back to the plan. What is being built and why (from PLAN.md).

### 2. Architecture

Describe the technical approach:
- Components and their responsibilities
- Data flow between components
- External integrations
- Key technical decisions with rationale

Use diagrams where helpful (mermaid, ASCII, or description).

### 3. Data Model

Define data structures:
- Entities and relationships
- Key fields and types
- Validation rules
- Storage approach

### 4. Interface Contracts

For each boundary (API, UI, integration):
- Inputs (with types and constraints)
- Outputs (with types and error cases)
- Behavior specification

### 5. Domain Bridge (Width)

Explicitly connect technical decisions to business/user intent:

| Business Need | Technical Implementation |
|---------------|-------------------------|
| [need from plan] | [how spec addresses it] |

This prevents spec drift from plan intent.

### 6. Quadrant Coverage

Ensure spec addresses all perspectives:

| Quadrant | Spec Element |
|----------|--------------|
| Individual Outer | Components, interfaces, data structures |
| Individual Inner | Skills/knowledge required to implement |
| Collective Outer | System integrations, infrastructure |
| Collective Inner | Team alignment, review needs |

### 7. Skill Dependencies (Height)

Document implementation prerequisites:
- What capabilities must the team have?
- What domain expertise is required?
- What learning must happen before or during implementation?

### 8. Identity Trap Check

Flag where spec might be protecting assumptions rather than solving problems:
- Are any technical decisions "because we always do it this way"?
- What alternatives were dismissed too quickly?

### 9. Testability Criteria

For each spec item, define how correctness is verified:

| Spec Item | Verification Method |
|-----------|-------------------|
| [item] | [how we know it's right] |

If you can't define verification, the spec is too vague.

### 10. Transcend and Include (Time)

Document what existing code/patterns are being:
- **Kept:** [what stays unchanged]
- **Extended:** [what's being built upon]
- **Replaced:** [what's being deprecated]

## Output Format

Produce a standalone document titled `SPEC.md` with sections above.

Include enough detail that implementation is unambiguous, but no more.

## Exit Criteria

Proceed to GAP ANALYSIS when:
- Every plan item maps to spec item
- All interfaces are defined
- Verification criteria exist for each component
- User confirms spec matches intent
