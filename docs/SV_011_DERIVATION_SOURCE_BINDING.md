# SV-011 Derivation Source Binding

Status: PREPARED_EXTERNAL_DEPENDENCY
Updated: 2026-09-01
Consumer: `SV-011/entity`

## Canonical derivation inputs

SV-011 should pin and consume the exact bytes of:

1. `docs/TRANSITION_ROLE_MODEL.md`
   - initial role vocabulary
   - role-escalation examples
   - nine required escalation blocks
   - role non-transfer theorem candidate
2. `docs/CONTINUATION_DECISION_FUNCTION.md`
   - `C(D, r, T, x)`
   - six-outcome vocabulary
   - capacity-gap precondition
   - block validation
   - fail-closed semantics
   - receipt emission order

## Native outcome vocabulary

`ALLOW`, `ALLOW_WITH_SIGNOFF`, `DENY`, `FAIL_CLOSED`, `REDIRECT`, `ESCALATE`.

Any projection into a narrower outcome vocabulary must be explicit, deterministic, and receipted.

## Construction rule

SV-011 must not infer a capability from observed behavior. A candidate capability must be traceable to:
- first transition element,
- declared current role,
- requested role escalation,
- required block set,
- commit-time decision,
- continuation receipt.

This source binding is non-authorizing and does not itself implement the SV-011 generator.
