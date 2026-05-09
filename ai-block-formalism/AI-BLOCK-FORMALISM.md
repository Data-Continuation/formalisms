# AI Block Formalism

**Status:** Draft v0.1.0  
**Domain:** StegVerse Transition Periodic Table / 15D Transition Admissibility Space  
**Primary primitive:** Inference-Consequence Coupling  
**Canonical placement:** `formalisms/ai-block-formalism`

## 1. Purpose

The AI Block formalism defines how AI-mediated transitions are classified, burdened, gated, and reconstructed inside the StegVerse Transition Periodic Table.

The AI Block does not classify AI as dangerous. It classifies the degree to which machine inference is coupled to consequence.

AI output remains symbolic until it is coupled to selection, authority, tools, persistence, externalization, or recursion. Without admissibility governance, that coupling becomes consequence-deterministic for the AI-mediated execution path. StegVerse interrupts that determinacy at the commit boundary.

## 2. Core Primitive

The core primitive is:

```text
ICC = Inference-Consequence Coupling
```

Definition:

```text
ICC(u) = f(I_r, T_b, A_s, E_x, P_s, R_c)
```

Where:

| Symbol | Meaning |
|---|---|
| `I_r` | inference role |
| `T_b` | tool binding |
| `A_s` | authority scope |
| `E_x` | externalization |
| `P_s` | persistence |
| `R_c` | recursion |

A first executable form is:

```text
ICC(u) =
I_r
* (1 + T_b)
* (1 + A_s)
* (1 + E_x)
* (1 + P_s)
* (1 + R_c)
```

Normalized:

```text
ICC_hat(u) = ICC(u) / ICC_max
```

So:

```text
ICC_hat(u) in [0, 1]
```

Plain meaning:

> ICC measures how tightly AI inference is connected to real consequence.

## 3. AI Block Membership

A transition belongs to the AI Block when machine inference materially shapes any part of transition formation.

```text
u in AI
```

if:

```text
Influence_AI(formation, selection, authorization, execution, recursion) > theta_AI
```

More compactly:

```text
AI = {
  u :
  AI materially affects Form(u)
  or Select(u)
  or Auth(u)
  or Exec(u)
  or Recur(u)
}
```

This includes:

- inference
- generation
- ranking
- decision
- tool use
- autonomous chaining
- recursive self/governance modification

## 4. AI Sub-Block Taxonomy

```text
AI = {
  AI_inf,
  AI_gen,
  AI_rank,
  AI_dec,
  AI_tool,
  AI_agent,
  AI_rec
}
```

| Sub-block | Meaning | Primary Risk |
|---|---|---|
| `AI_inf` | inference, classification, summarization | claim-reality mismatch |
| `AI_gen` | artifact, code, text generation | invalid or mis-targeted artifact |
| `AI_rank` | ranking or prioritization | affordance/opportunity distortion |
| `AI_dec` | selecting an action | authority confusion |
| `AI_tool` | invoking external tools | target-bound mutation |
| `AI_agent` | multi-step goal pursuit | compound transition drift |
| `AI_rec` | changing future AI/governance behavior | recursive admissibility mutation |

## 5. AI Phase Ladder

AI transitions must be phase-indexed.

```text
AI-P0 -> AI-P1 -> AI-P2 -> AI-P3 -> AI-P4 -> AI-P5 -> AI-P6 -> AI-P7 -> AI-P8
```

| Phase | Meaning |
|---:|---|
| `AI-P0` | latent model capability |
| `AI-P1` | prompted inference |
| `AI-P2` | interpreted or classified state |
| `AI-P3` | generated artifact |
| `AI-P4` | selected action |
| `AI-P5` | tool-bound target |
| `AI-P6` | committed external mutation |
| `AI-P7` | person, life, or financial consequence |
| `AI-P8` | recursive governance, tool, model, or memory mutation |

Important rule:

```text
ALLOW(AI-P_n) does not imply ALLOW(AI-P_(n+1))
```

Permission at one phase does not automatically transfer to a deeper phase.

Examples:

- An AI may be allowed to generate code without being allowed to install it.
- An AI may be allowed to suggest an email without being allowed to send it.
- An AI may be allowed to classify repo structure without being allowed to create a new repo.

## 6. Artificial Consequence Determinacy

Define:

```text
D_AI =
(A_AI * T_u * Auth * P * R * E)
/
(G * C * t * rho * R_i)
```

Where:

| Symbol | Meaning |
|---|---|
| `A_AI` | AI agency level |
| `T_u` | tool access |
| `Auth` | authority scope |
| `P` | persistence |
| `R` | recursion |
| `E` | externalization |
| `G` | governance |
| `C` | control |
| `t` | trust / claim-reality alignment |
| `rho` | receipt sufficiency |
| `R_i` | recoverability |

Interpretation:

```text
D_AI up
```

means the AI-mediated path is becoming structurally more likely to produce consequence unless interrupted.

This formalism explicitly distinguishes:

```text
D_AI != danger
```

```text
D_AI = consequence-determinacy pressure
```

## 7. AI-Refined Admissibility Invariant

The AI Block plugs into the refined GCAT invariant:

```text
a_eff(u) * H_C(Y | x, u) * ICC_hat(u)
<=
K * g^alpha * c^beta * t^gamma * R_i^lambda * rho^mu
```

Where:

| Symbol | Meaning |
|---|---|
| `a_eff(u)` | effective autonomy exercised |
| `H_C(Y | x, u)` | consequence-weighted uncertainty |
| `ICC_hat(u)` | normalized inference-consequence coupling |
| `g, c, t` | GCAT governance, control, and trust terms |
| `R_i` | recoverability |
| `rho` | receipt sufficiency |

Plain statement:

> AI-mediated transitions are admissible only when effective autonomy, consequence-bearing uncertainty, and inference-consequence coupling are bounded by governance, control, trust, recoverability, and receipts.

## 8. Monotonic Burden Law

The AI Block uses a monotonicity rule:

```text
partial Z_tau / partial ICC_hat >= 0
partial Z_tau / partial A_AI >= 0
partial Z_tau / partial ToolAccess >= 0
partial Z_tau / partial AuthorityScope >= 0
partial Z_tau / partial Externalization >= 0
partial Z_tau / partial Recursion >= 0
```

Plain statement:

> As AI moves closer to authority, tools, persistence, externalization, or recursion, admissibility burden cannot decrease.

This is the core testable theorem.

## 9. Hard Gates

The AI Block defines hard gates that cannot be averaged away.

### 9.1 Target Binding

```text
Target_intended = Target_selected = Target_committed
```

If false:

```text
FAIL-CLOSED
```

### 9.2 Authority Boundary

```text
Authority_executed <= Authority_delegated
```

If false:

```text
FAIL-CLOSED
```

### 9.3 Context Sufficiency

```text
CS(x, u) >= CS_min(tau)
```

If false, either downgrade to advisory phase or fail closed.

### 9.4 Receipt Sufficiency

```text
rho_AI >= rho_min_AI
```

If false:

```text
FAIL-CLOSED
```

### 9.5 Recursive Mutation Isolation

```text
AI_rec => ElevatedGovernanceRequired
```

No recursive AI transition should be admitted under ordinary generation or tool-use burden.

## 10. Failure Variables

The formalism defines AI-specific defect variables:

| Variable | Meaning |
|---|---|
| `Hallu` | hallucination / claimed-state failure |
| `TB_f` | target-binding failure |
| `CS_f` | context-sufficiency failure |
| `AD` | assumption debt |
| `CD` | continuity debt |
| `CL` | confidence laundering |
| `NP` | novelty pressure |
| `MRG` | model-reality gap |
| `DR` | instruction-to-action drift |

Key relationships:

```text
AD up => H_C up
CD up => t down
CL up => rho_required up
TB_f = 1 => FAIL-CLOSED
MRG up => t down and H_C up
```

These make assistant failures mathematically visible.

## 11. Continuity-before-Novelty Law

This law is required for persistent ecosystems.

```text
NewArtifact(u) => Proof(NoExistingArtifactServesRole)
```

If no such proof exists:

```text
DENY(NewArtifact)
```

and instead:

```text
Continue(ExistingArtifact)
```

Plain statement:

> AI systems working on persistent ecosystems must prove continuity before creating novelty.

## 12. Human-in-the-Loop Non-Sufficiency

The formalism rejects weak human-in-the-loop claims.

```text
HumanClick != Governance
```

Human presence only contributes governance if the human has:

- context
- time
- visibility
- authority
- refusal power
- consequence understanding
- receipt access

Define:

```text
HITL_valid =
Context
* Visibility
* Authority
* Time
* Refusal
* Understanding
```

If:

```text
HITL_valid < theta
```

then human-in-the-loop does not materially raise governance or trust.

Plain statement:

> A human click is not governance unless the human can meaningfully evaluate and refuse the transition.

## 13. AI Receipt Schema

Minimum AI receipt:

```text
R_AI = (
  instruction,
  assumptions,
  context,
  model_state,
  toolset,
  interpretation,
  target,
  authority_basis,
  transition_class,
  output,
  verification,
  residual_uncertainty
)
```

Tool-bound AI receipt:

```text
R_AI_tool =
R_AI + (
  tool_call,
  parameters,
  prestate,
  poststate,
  rollback_path,
  commit_identifier
)
```

Recursive AI receipt:

```text
R_AI_rec =
R_AI_tool + (
  prior_rule,
  new_rule,
  rule_diff,
  approval_basis,
  future_impact
)
```

Receipt sufficiency condition:

```text
H(S_(t+1) | S_t, u, R_AI, O_(t+1)) <= epsilon
```

Plain statement:

> AI receipts must reconstruct how inference became consequence.

## 14. Seed Transition Elements

| Code | Name | Required Burden |
|---|---|---|
| `AI-INF-P2-I` | AI Inference Transition | claim-reality alignment |
| `AI-GEN-P3-R` | AI Artifact Generation | reconstruction and format sufficiency |
| `AI-GEN:CFG-P5-G/R` | AI Configuration Generation | governance and receipt sufficiency |
| `AI-GEN:WORKFLOW-P5-G/R` | AI Workflow Generation | executable configuration burden |
| `AI-RANK:PERS-P7-Q` | AI Person Ranking | standing and consequence burden |
| `AI-DEC-P4-G` | AI Decision Selection | authority/admissibility burden |
| `AI-TOOL:EMAIL-P6-Q` | AI Email Sending | external communication consequence |
| `AI-TOOL:GITHUB-P5-R` | AI GitHub Mutation | target and reconstruction burden |
| `AI-AGENT:DEP-P6-V/H` | AI Agent Deployment | viability and entropy burden |
| `AI-REC:POLICY-P5-G` | AI Policy Mutation | recursive governance burden |
| `AI-CRED-P5-G/H` | AI Credential Transition | authority and irreversibility |
| `AI-FIN-P7-Q/H` | AI Financial Transition | settlement and consequence |
| `AI-LIFE-P7-L/H` | AI Life-Affecting Transition | viability, welfare, irreversibility |
| `AI-PERS-P7-Q/R` | AI Person-Affecting Transition | standing, appeal, reconstruction |
| `AI-MEM-P8-G/R` | AI Memory Mutation | future behavior and reconstruction |

## 15. Test Cases

The first test suite should verify classification and burden monotonicity.

### 15.1 Classification Tests

| Input | Expected Class |
|---|---|
| summarize a document | `AI-INF-P2-I` |
| draft markdown | `AI-GEN-P3-R` |
| generate workflow file | `AI-GEN:WORKFLOW-P5-G/R` |
| send an email through a tool | `AI-TOOL:EMAIL-P6-Q` |
| mutate GitHub file | `AI-TOOL:GITHUB-P5-R` |
| deploy generated code | `AI-AGENT:DEP-P6-V/H` |
| alter policy rules | `AI-REC:POLICY-P5-G` |
| rank people for opportunity | `AI-RANK:PERS-P7-Q` |
| modify memory | `AI-MEM-P8-G/R` |

### 15.2 Monotonic Burden Test

Verify:

```text
Burden(AI_inf)
<
Burden(AI_gen)
<
Burden(AI_dec)
<
Burden(AI_tool)
<
Burden(AI_agent)
<
Burden(AI_rec)
```

with modifiers:

```text
PERS, LIFE, FIN, CRED, REC
```

raising burden.

### 15.3 Hard-Gate Tests

Verify:

```text
TB_f = 1 => FAIL-CLOSED
CS < CS_min => FAIL-CLOSED
Authority_executed > Authority_delegated => FAIL-CLOSED
rho_AI < rho_min => FAIL-CLOSED
```

## 16. Done Criteria

The AI Block is done when it can:

1. Classify AI-mediated transitions by sub-block.
2. Assign phase depth from `AI-P0` to `AI-P8`.
3. Compute or estimate ICC.
4. Estimate `D_AI`.
5. Apply the AI-refined admissibility invariant.
6. Enforce hard gates.
7. Emit an AI receipt.
8. Fail closed on missing target, missing authority, missing context, or missing receipt.
9. Prove burden monotonicity across AI phases.
10. Compose with Life, Person, Finance, Credential, GitHub, Workflow, and Recursive blocks.

## 17. Signature Line

> AI is not dangerous because it is capable. It becomes consequence-deterministic when capability couples to authority, tools, persistence, and recursion without admissibility governance. StegVerse breaks that determinacy at commit.

## 18. Placement

Canonical formalism placement:

```text
formalisms/ai-block-formalism
```

Executable test placement:

```text
formalism-tests/ai-block-formalism-tests
```

The formalism belongs under `formalisms` because it defines the canonical mathematical and conceptual object.

The tests belong under `formalism-tests` because they verify classification, monotonic burden, and hard-gate behavior.
