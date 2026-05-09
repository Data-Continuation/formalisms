# Continuation Decision Function

## Purpose

The continuation decision function determines whether data may continue from representation into consequence.

## Function

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

## GCAT/BCAT continuation test

```text
Λ(x) = K·g^α·c^β·t^γ
I(D, r, T, x) = M(D, r, T) - Λ(x)
```

Decision precondition:

```text
I(D, r, T, x) ≤ 0
```

## Block validation

```text
∀b ∈ Blocks(T, r), b(D, x) = true
```

## Fail-closed condition

```text
missing required basis → FAIL_CLOSED
unknown required basis → FAIL_CLOSED
stale required basis   → FAIL_CLOSED
negative capacity gap  → FAIL_CLOSED or DENY
```

## Decision order

```text
1. Confirm role is declared.
2. Confirm transition class is declared.
3. Confirm required blocks are known.
4. Confirm required evidence exists.
5. Compute consequence mass.
6. Compute legitimacy capacity.
7. Evaluate capacity gap.
8. Evaluate required blocks.
9. Decide.
10. Emit receipt.
```

## Central doctrine

```text
Data may continue only when consequence mass does not exceed legitimacy capacity and all required blocks resolve at commit.
```
