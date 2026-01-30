---
name: 5d-verify
description: "Multi-layer verification of implementation against spec and intent. Use when: (1) After BUILD phase in 5D-SDD workflow, (2) Implementation is complete and needs validation, (3) User asks to 'test,' 'verify,' or 'check' the implementation, (4) Before considering a feature done. This phase catches errors at multiple levels and routes fixes appropriately."
---

# VERIFY Phase

Verify implementation at multiple levels and route failures appropriately.

## Verification Layers

### Layer 1: Technical Correctness

- Does it build/compile without errors?
- Do tests pass?
- Does linting pass?
- Does it run without crashing?

**Failure routing:** Return to BUILD

### Layer 2: Spec Fidelity

- Does implementation match spec interfaces?
- Are all spec requirements addressed?
- Do outputs match spec definitions?

**Failure routing:** Return to BUILD (if code error) or SPEC (if spec error)

### Layer 3: Plan Validity

- Does this solve the problem stated in the plan?
- Does user testing confirm expected behavior?
- Are the original assumptions holding?

**Failure routing:** Return to PLAN or SPAR

### Layer 4: Epistemic Update (Depth + Time)

- Did we learn anything that changes our assumptions?
- Are there new risks or opportunities?
- Should the spec be updated for future work?
- What patterns emerged that apply to future projects?
- What should we "transcend and include" going forward?

**Failure routing:** Document for REFLECT phase

### Layer 5: Multi-Dimensional Check

**Quadrant coverage:**
- Individual Outer: Are artifacts complete and correct?
- Individual Inner: Is understanding documented?
- Collective Outer: Are system integrations verified?
- Collective Inner: Is stakeholder alignment confirmed?

**Height (Skill Dependencies):**
- Did capability gaps cause failures?
- What skills were developed during implementation?
- What remains blocked by missing capabilities?

**Identity Trap:**
- Are we declaring success to avoid examining failures?
- Are failures being minimized because they threaten assumptions?
- What are we not looking at?

## Verification Process

1. Run automated checks (build, lint, test)
2. Manual spec comparison
3. User acceptance testing (if applicable)
4. Collect all failures and discoveries

## Failure Diagnosis

When something fails, identify which layer:

| Symptom | Likely Layer | Action |
|---------|--------------|--------|
| Code doesn't run | Layer 1 | Fix in BUILD |
| Works but wrong output | Layer 2 | Check spec, fix in BUILD or SPEC |
| Works but users confused | Layer 3 | Return to PLAN |
| Works but solves wrong problem | Layer 3-4 | Return to SPAR |

**Critical:** Don't keep fixing code if the spec is wrong. Don't keep fixing spec if the understanding is wrong.

## Output Format

```
## Verification Report

### Layer 1: Technical
- Build: ✓/✗
- Tests: ✓/✗ ([pass]/[total])
- Lint: ✓/✗

### Layer 2: Spec Fidelity
- [Spec item]: ✓/✗
- [Spec item]: ✓/✗

### Layer 3: Plan Validity
- User testing: [results]
- Problem solved: [yes/no/partial]

### Layer 4: Learnings
- [Discovery or assumption update]

### Failures Requiring Action
| Issue | Layer | Routing |
|-------|-------|---------|
| [issue] | [1-4] | [phase to return to] |

**Verification status:** pass / fail-minor / fail-major
```

## Exit Criteria

Feature complete when:
- All Layer 1-3 checks pass
- No unresolved failures
- User confirms acceptance

Proceed to REFLECT when feature is complete or iteration is ending.
