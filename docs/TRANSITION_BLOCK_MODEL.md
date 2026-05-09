# Transition Block Model

## Purpose

A transition block is a reusable governance constraint package attached to a data-continuation attempt.

The Transition Periodic Table classifies the continuation crossing. Transition blocks define what must hold before that crossing may continue into consequence.

## Core rule

```text
A transition block is not a label alone.
A transition block is a constraint package.
```

## Block structure

```text
TransitionBlock {
  id
  name
  description
  applies_to_roles
  applies_to_transition_classes
  required_inputs
  admissibility_condition
  fail_closed_condition
  receipt_fields
  replay_fields
}
```

## Required block families

```text
authority
custody
evidence
scope
trust
risk
reversibility
receipt
replay
human_signoff
revocation
state_freshness
```

## Example block

```yaml
id: authority_current
name: Authority Current
description: The authority basis for the continuation must be current at commit.
applies_to_roles:
  - authorization_basis
  - command
  - transaction_basis
  - physical_control_signal
required_inputs:
  - authority_id
  - authority_scope
  - authority_timestamp
  - revocation_status
admissibility_condition: authority exists, scope matches, and revocation status is clear
fail_closed_condition: missing, stale, out-of-scope, or revoked authority
receipt_fields:
  - authority_id
  - authority_scope
  - authority_timestamp
  - revocation_status
replay_fields:
  - authority_id
  - authority_scope
  - authority_timestamp
```

## Relationship to GCAT/BCAT

GCAT/BCAT evaluates whether legitimacy capacity can support consequence mass.

Transition blocks evaluate whether required constraint families resolve.

A continuation is admissible only when both hold:

```text
M(D, r, T) ≤ Λ(x)
and
∀b ∈ Blocks(T, r), b(D, x) = true
```

## Relationship to standing dimensions

Standing dimensions such as authority, evidence, custody, continuity, risk, receipt basis, replay basis, and decay can be represented as transition block families.

This preserves dimensional coverage while keeping StegVerse organized around transition classification and commit-time admissibility.

## Transition compounds

A transition compound is a composed chain of transition blocks or transition classes.

```text
identity_binding
+ authority_delegation
+ custody_transfer
+ asset_movement
= governed financial settlement
```

Local admissibility does not imply compound admissibility.

The compound must be evaluated as its own continuation structure.
