# Data Phase Model

## Purpose

The Data Phase Model separates data existence from data consequence.

Most failures in agentic systems occur when output silently escalates from representation into action. This model makes that escalation explicit.

## Phases

```text
D0 — latent
D1 — represented
D2 — interpreted
D3 — proposed
D4 — actionable
D5 — committed
D6 — consequential
D7 — irreversible
```

## Definitions

D0 latent: data exists but is not presently observed, retrieved, or used.

D1 represented: data is stored, generated, displayed, encoded, or otherwise made available as representation.

D2 interpreted: a system or actor assigns meaning to the data.

D3 proposed: the data suggests a possible future state, recommendation, action, or transition.

D4 actionable: the data is connected to a mechanism capable of effect.

D5 committed: the data crosses the execution boundary.

D6 consequential: the data produces effect in a system, institution, physical environment, or social context.

D7 irreversible: the effect cannot be fully undone from inside the original control frame.

## Governance region

```text
D3 proposed
→ D4 actionable
→ D5 committed
```

The commit boundary sits between D4 and D5.

## Consequence rule

Data may only enter D5 when continuation admissibility holds at commit.

```text
No admissibility at commit → no continuation
```
