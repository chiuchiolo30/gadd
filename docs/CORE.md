# GADD Core v0.1 — Preliminary specification

**Status:** Proposed; not a formal industry standard. Terms MUST, SHOULD and MAY express requirements of this proposal.

## 1. Scope

GADD governs **the development process involving one or more AI agents**, including change planning, code modification, review, verification and integration. It is especially relevant to **sensitive, business-critical and high-consequence software**, where unauthorized changes, regressions or weak evidence can have disproportionate impact. Risk and applicable obligations—not organizational size—determine control rigor. It is architecture-agnostic and compatible with human-only contributions to the same repository. GADD does not provide a safety certification, guarantee regulatory compliance, or eliminate risk.

## 2. Terms

- **Human accountable owner:** person or recognized role responsible for final acceptance and risk.
- **Agent:** AI-enabled actor that proposes or performs development tasks.
- **Mandate:** authorized goal, scope, allowed actions, limits and stop conditions for a task or stage.
- **Policy:** versioned, project-specific rule constraining design, implementation or review.
- **Gate:** condition checked before proceeding to a controlled stage.
- **Evidence:** durable record of a check, decision or outcome that a reviewer can verify.
- **Baseline:** accepted historical state against which new regressions are evaluated.
- **Exception:** recorded, authorized and time-bounded waiver of a rule, where allowed.

## 3. Minimum process requirements

**GADD-01 — Accountability.** Each governed change MUST have an identified human accountable owner or approver role. Approval MUST NOT be represented as granted until recorded.

**GADD-02 — Explicit mandate.** Before execution, agents MUST receive a bounded goal and applicable constraints. Material scope changes MUST trigger renewed authorization.

**GADD-03 — Authoritative policies.** The project MUST identify the authoritative sources for architecture, naming, workflow and verification policy. It MUST define a precedence rule and MUST resolve material contradictions before the affected work proceeds. Agent-specific instruction files MAY act as adapters but MUST NOT silently redefine the canonical policy.

**GADD-04 — Change traceability.** Significant changes MUST be associated with an intended outcome and acceptance conditions; teams MUST be able to identify relevant plans, code changes and checks. Format and granularity MAY depend on risk.

**GADD-05 — Independent checks.** A change MUST be assessed by relevant mechanisms outside the producing agent's unsupported self-assertion (for example, deterministic tests, linters, architecture checks, build checks or an independent review). A producing agent's statement that a command passed is not by itself acceptable evidence.

**GADD-06 — Controlled acceptance.** Acceptance MUST consider the applicable check results and unresolved risks. If an integration policy says a check is mandatory, the repository SHOULD technically enforce it as a required status check or equivalent mechanism. Teams MUST distinguish checks that are advisory from those that actually prevent merging.

**GADD-07 — Failure and debt handling.** Failed mandatory checks MUST stop acceptance until fixed or explicitly waived by an authorized human under a documented exception policy. Pre-existing debt MUST be distinguished from new or worsened violations wherever baselines are used.

**GADD-08 — Technology independence.** Conformance MUST NOT require a particular LLM, IDE, provider, programming language or architectural pattern. Each project selects its own implementation of the requirements.

**GADD-09 — Risk-driven proportionality.** Teams SHOULD classify the consequence of failure and impact of each change before work starts (for example, Low, Significant or Critical), and vary artifacts, approvals, confidentiality safeguards and verification rigor accordingly. High-consequence changes SHOULD have independently executed mandatory checks and documented human acceptance. Teams MUST NOT reduce an applicable mandatory safety, security, contractual or quality gate without appropriate authorization; regulatory obligations cannot be waived by the methodology.

**GADD-10 — Confidentiality.** Governance artifacts and logs SHOULD avoid exposing secrets, company code, customer information or restricted operational details when evidence is shared outside the authorized environment.

## 4. Required evidence examples

For a governed change, a team SHOULD be able to show: work request and acceptance criteria; mandate or task assignment; policy version; required approvals; change/commit/PR identifier; verification command and actual result; disposition of failures; final human acceptance where required.

## 5. What does not count as proof

- An `AGENTS.md` file alone does not prove agent compliance.
- A workflow declaration alone does not prove that stop rules were observed.
- A passing check without a retained log/commit association may not be independently auditable.
- A green but optional CI check does not prove merge protection.
- Passing tests does not prove architectural compliance unless those properties are tested.
- An AI reviewer is useful but not a substitute for independent deterministic evidence for testable properties.

## 6. Process versus enforcement

**Documented:** rules and workflow exist.  
**Observed:** executions and check results can be inspected.  
**Enforced:** relevant gates are applied by an independent mechanism that blocks unauthorized progression or integration.

A team MUST disclose which level it actually meets for each claimed control. GADD v0.1 does not confer a certification or label.

## 7. Exceptions and evolution

Every exception SHOULD identify approver, rationale, affected policy, scope, expiry or review date and remaining risk. Policies SHOULD be versioned and tested for contradictory instructions across tools and agents.

## 8. Open questions for community review

- What minimum evidence is necessary for low-risk changes?
- How should non-deterministic reviews be described without implying hard guarantees?
- Which controls should be mandatory in local development versus protected branches?
- How should governance policy migrations and legacy debt be handled?
