# Transition Role Model

## Purpose

The same data can be admissible in one role and inadmissible in another.

A role is the function a datum is being asked to occupy in a consequence pathway.

## Core rule

```text
same data ≠ same continuation admissibility
```

## Initial roles

```text
context
informational_note
evidence
recommendation
instruction
authorization_basis
command
policy_basis
identity_claim
custody_basis
transaction_basis
physical_control_signal
```

## Role escalation examples

```text
context → evidence
evidence → authorization_basis
recommendation → instruction
instruction → command
command → execution
prediction → policy_basis
identity_claim → access_grant
simulation → deployment
risk_score → service_denial
```

## Required role-escalation blocks

```text
role_change_declared
transition_class_declared
authority_current
evidence_fresh
scope_valid
trust_basis_current
risk_basis_current
receipt_required
fail_closed_if_missing
```

## Transition role tuple

```text
(D, r, T, x)
```

Where:

```text
D = datum
r = role
T = transition class
x = current system state
```

## Role non-transfer theorem candidate

```text
Admit(D, r₁, T, x) does not imply Admit(D, r₂, T, x)
```
