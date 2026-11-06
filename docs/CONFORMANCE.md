# GADD v0.1 — Conformance and evidence model

**Status:** Proposed assessment model, not a certification or audit opinion.

GADD evaluates a **change process** rather than a model, framework, IDE or software architecture. The same repository can satisfy different controls to different degrees. The table below aligns with [GADD Core](CORE.md).

## Three levels of evidence

| Level | Meaning | Example |
|---|---|---|
| Documented | A rule is defined and has an identified authority. | A version-controlled workflow instructs an agent to stop for plan approval. |
| Observed | An actual execution produced inspectable evidence. | An approval decision and check result can be linked to a particular change. |
| Enforced | A control external to the agent's assertion prevents unauthorized progression. | A required CI check blocks PR merge, or a workflow engine refuses to proceed without approval. |

These are **descriptive levels, not a numerical score or certification**. Different controls can reach different levels. The word "enforced" must identify an actual enforcement boundary; a prompt alone never qualifies.

## Minimum evidence matrix

| Core rule | Evidence to inspect | Common failure |
|---|---|---|
| GADD-01: Accountability | Named approving role and recorded decision when required | Agent reports approval with no human decision |
| GADD-02: Explicit mandate | Bounded task, allowed paths/actions, escalation rule | Agent expands scope without authorization |
| GADD-03: Authoritative policies | Versioned source of truth, precedence, conflict resolution | Shared agent rules contradict project architecture |
| GADD-04: Traceability | Request/criteria to plan, diff, check result | No link between requested behavior and delivered changes |
| GADD-05: Independent checks | Command execution evidence or independent review | Only the builder agent says tests passed |
| GADD-06: Controlled acceptance | Acceptance record, CI results and required-check setting | Green optional CI check is presented as merge protection |
| GADD-07: Failures and debt | Failed check disposition, baseline comparison, signed exception | New regressions are ignored as "existing debt" |
| GADD-08: Tool independence | A vendor-neutral process description | Conformance requires an unrelated proprietary service |
| GADD-09: Proportionality | Documented risk tier and approval requirements | Quick changes bypass policies without authorization |
| GADD-10: Confidentiality | Evidence-sharing rules and sanitized examples | CI logs or public docs contain restricted data |

## Evaluation worksheet

Use a separate record for each change. Avoid storing secrets in the worksheet.

```yaml
change_id: "example-pr-42"
policy_revision: "example-policy-commit"
risk_tier: "standard"
owner_role: "tech-lead"
agent_mandate_ref: "example-work-item"
controls:
  GADD-01: { level: "observed", evidence_ref: "approval-record" }
  GADD-02: { level: "documented", evidence_ref: "task-definition" }
  GADD-03: { level: "observed", evidence_ref: "policy-consistency-check" }
  GADD-04: { level: "observed", evidence_ref: "spec-plan-pr-trace" }
  GADD-05: { level: "observed", evidence_ref: "ci-run-identifier" }
  GADD-06: { level: "not-assessed", evidence_ref: null }
  GADD-07: { level: "not-applicable", evidence_ref: "no-debt-baseline-policy" }
  GADD-08: { level: "documented", evidence_ref: "process-specification" }
  GADD-09: { level: "documented", evidence_ref: "risk-policy" }
  GADD-10: { level: "documented", evidence_ref: "sharing-policy" }
disposition: "not-assessed"
```

## Important cautions

- A documented rule does **not** establish agent obedience.
- A passing test does **not** prove that an unrelated architecture rule is satisfied.
- A human approving a PR does not automatically prove that the earlier design gate was enforced.
- CI configured to run is not necessarily CI configured to block merges.
- GADD v0.1 does not issue official conformance badges or licenses.

## Evidence protection

For proprietary or client projects, keep the original logs, configs, code and review records private. Publish a **synthetic example** or a separately authorized aggregate description. Do not treat anonymization as sufficient if project identity or architecture can still be reconstructed.
