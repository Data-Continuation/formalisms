# Data Continuation Formalism: Commit-Time Governance of Data Becoming Consequence

## Abstract

Data does not become consequence merely because it exists, is generated, is stored, or is replayable. It becomes consequence when it is allowed to continue through a role and transition into a binding effect. We introduce the Data Continuation Formalism (DCF), a commit-time governance model for determining whether data may continue from representation into consequence. DCF distinguishes data phases, role assignment, transition classification, consequence mass, legitimacy capacity, required governance blocks, and fail-closed behavior. The first proof surface demonstrates that the same datum under the same system state may receive different continuation decisions when assigned different roles. This establishes that continuation admissibility is role-transition dependent, not content-only.

## 1. Core Problem

Most automated systems treat data output as if the main question is whether the data is correct, useful, explainable, or logged.

DCF asks a different question:

```text
What is this data being allowed to become?
```

A datum may be admissible as context, conditional as a recommendation, and inadmissible as autonomous actuation.

## 2. Data Phases

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

The critical governance region is:

```text
D3 proposed → D4 actionable → D5 committed
```

## 3. Continuation Decision

```text
C(D, r, T, x) → outcome
```

Where:

```text
D = datum
r = role
T = transition class
x = current system state
```

Outcome set:

```text
ALLOW
ALLOW_WITH_SIGNOFF
DENY
FAIL_CLOSED
REDIRECT
ESCALATE
```

## 4. Capacity Condition

```text
Λ(x) = K·g^α·c^β·t^γ
I(D, r, T, x) = M(D, r, T) - Λ(x)
```

Continuation requires:

```text
I(D, r, T, x) ≤ 0
```

and all required transition blocks must resolve.

## 5. First Proof Surface

The current proof surface demonstrates:

```text
same data
same system state
different role
different continuation decision
```

Example:

```text
Data: “Patient may be at high risk.”

informational_note → ALLOW
clinician_recommendation → ALLOW_WITH_SIGNOFF
autonomous_medication_change → FAIL_CLOSED
```

This verifies:

```text
same data ≠ same continuation admissibility
```

## 6. Fail-Closed Requirement

DCF requires fail-closed behavior when required basis is missing, stale, unknown, or insufficient.

```text
missing required basis → FAIL_CLOSED
insufficient legitimacy capacity → FAIL_CLOSED
```

## 7. Relationship to Transition Periodic Table

The Transition Periodic Table classifies the ways data tries to become real.

DCF provides the ontology:

```text
representation → continuation → consequence
```

The Transition Periodic Table provides the taxonomy:

```text
what kind of continuation is attempting to bind?
```

GCAT/BCAT provides the capacity test:

```text
does legitimacy capacity support consequence mass?
```

## 8. Conclusion

Governance is the law of data continuation.

Data may exist freely as representation. Data may continue into consequence only when admissibility resolves at commit.
