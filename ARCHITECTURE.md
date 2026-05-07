# Data Continuation Architecture

## Assumptions

1. Data can exist without being consequence-binding.
2. Consequence is not a property of data alone.
3. Consequence emerges when data is allowed to continue through a role and transition into effect.
4. Governance is required at the continuation boundary.
5. Missing authority, evidence, state, or replay basis must produce fail-closed behavior.

## Done criteria

This architecture is complete enough for first testing when:

1. Data phases are defined.
2. Continuation roles are defined.
3. Transition classes are declared.
4. A continuation decision function exists.
5. Test cases show that the same data can produce different admissibility outcomes in different roles.
6. Receipts preserve the basis for each outcome.

## Layer model

```text
D0 latent
D1 represented
D2 interpreted
D3 proposed
D4 actionable
D5 committed
D6 consequential
D7 irreversible
```

## Continuation pipeline

```text
input data
→ ingestion
→ representation phase
→ role assignment
→ transition classification
→ block selection
→ eligibility check
→ inference-window refinement
→ commit-time admissibility
→ ALLOW / DENY / FAIL_CLOSED / ALLOW_WITH_SIGNOFF
→ receipt and replay
```

## Transition-aware GCAT/BCAT relation

Original GCAT:

```text
I(x) = a - K·g^α·c^β·t^γ ≤ 0
```

Data-continuation form:

```text
I(D, r, T, x) = M(D, r, T) - K·g^α·c^β·t^γ ≤ 0
```

Where:

```text
D = datum
r = assigned role
T = transition class
M(D, r, T) = consequence mass
x = current system state
g = governance capacity
c = control authority
t = trust/evidence basis
```

Decision rule:

```text
I(D, r, T, x) ≤ 0  → data may continue, subject to required blocks
I(D, r, T, x) > 0   → data may not continue
unknown basis        → FAIL_CLOSED
```

## Relationship to the Transition Periodic Table

The Transition Periodic Table classifies ways data attempts to become real.

A transition entry should define:

```text
transition identity
role change
consequence mass profile
authority charge profile
reversibility profile
required governance blocks
decay modes
composition hazards
receipt requirements
fail-closed conditions
```

## First proof surface

```text
same data
same system state
different role
different continuation decision
```

Example:

```text
Data: “Patient may be at high risk.”

Role: informational_note
Decision: ALLOW

Role: clinician_recommendation
Decision: ALLOW_WITH_SIGNOFF

Role: autonomous_medication_change
Decision: FAIL_CLOSED
```
