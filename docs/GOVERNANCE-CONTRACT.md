# GADD Governance Contract — reference model v0.1

**Status:** Proposed reference model; not a certification scheme.  
**Audience:** Software teams adopting AI agents, independent of programming language, framework, IDE, or agent runtime.

The [GADD Core](CORE.md) states the minimum methodology requirements. This document shows how to express them as a concrete *governance contract* for a particular project.

## 1. Separate four responsibilities

| Responsibility | Primary question | Expected artifact or evidence |
|---|---|---|
| **Authority** | Who can approve an objective, a design decision, a deviation, or integration? | Owner/approver role; scoped approval or exception |
| **Governance** | Which rules apply to the project, who maintains them, and which source takes precedence? | Versioned canonical policy and precedence rules |
| **Execution** | What is the agent or developer authorized to change, and when must it stop? | Work item, scope, agent mandate and stop conditions |
| **Verification & acceptance** | What actually ran, what failed, and what allows a change to enter the codebase? | Test/static check results, review, mandatory integration gates |

An agent's final message is **not independent verification**. A green CI job is **not necessarily a required merge gate**.

## 2. Minimal contract data

A team may use Markdown, YAML, issue templates, a workflow engine or another format. GADD imposes *meaning*, not file names.

| Field | Needed for | Example (fictional) |
|---|---|---|
| Change ID and goal | Traceability | `FEAT-42: show order status` |
| Owner role | Accountability | `tech-lead` |
| Risk tier | Proportional controls | `standard` |
| Canonical policy revision | Rule authority | `policy-commit-sha` |
| Mandate | Bounded execution | `change files in approved feature only` |
| Stop rules | Authorization | `stop before implementation until plan is approved` |
| Approval record | Human decision | `plan-approved-by-owner` |
| Required validation | Independent evidence | `lint; unit tests; architecture check` |
| Acceptance rule | Integration | `required check passes before merge` |
| Baseline / exception reference | Evolution of debt | `approved baseline revision, if used` |

Avoid logging secrets, production data or private source excerpts in portable evidence.

## 3. Policy authority and conflict handling

GADD does not define the preferred architecture of an application. The project must make its own architectural decisions.

**Example precedence policy (adopt or replace explicitly):**

1. Legal, safety and organizational controls that the team cannot waive.
2. Repository's canonical, versioned architectural and verification policies.
3. Approved change-specific requirements and design decisions.
4. Workflow role definitions and agent instruction adapters.
5. Suggestions, examples, model defaults and generated plans that have not been approved.

The precedence order must be documented; this is a *sample*, not an automatic rule for every project. Any material conflict that changes design or verification obligations must halt the affected step until an accountable human resolves it. A local agent prompt cannot silently override repository policy.

A generated plan that describes a different architecture from the project's canonical contract must be corrected or explicitly authorized before implementation.

## 4. Reference lifecycle and gates

```text
INTENT / ACCEPTANCE CONDITIONS
           |
PROJECT POLICY + AGENT MANDATE
           |
DESIGN / PLAN -- approval where risk or policy requires
           |
IMPLEMENTATION WITH BOUNDED SCOPE
           |
INDEPENDENT EVIDENCE (tests, static analysis, fitness functions)
           |
REVIEW OF OUTPUT, DEVIATIONS AND BASELINES
           |
INTEGRATION GATE (required status checks where configured)
           |
ACCOUNTABLE ACCEPTANCE
```

Each gate has:
- **Condition:** what must be true to continue.
- **Authority:** who or what is allowed to decide.
- **Evidence:** how a reviewer later verifies the result.
- **Failure action:** stop, repair, obtain authorized exception, or reject.

The exact number of human approvals should be proportionate to risk. A mandatory control cannot be downgraded merely because an agent asserts that the task is simple.

## 5. Three evidence levels

| Level | What can truthfully be claimed | What it does not prove |
|---|---|---|
| **Documented** | Policies, stop rules and commands are written and versioned | The agent obeyed them |
| **Observed** | A particular change has actual approvals or execution results | Future changes cannot bypass them |
| **Enforced** | A separate mechanism blocks unauthorized progression or integration when a required condition fails | All defects are detected |

**Failure behavior must be explicit.** For a validation to count as a blocking command, a detected mandatory error must produce a failed status (nonzero exit code, failed job, or equivalent). An informational debt report is still useful but must not be called a blocking quality gate.

**Integration enforcement must be verified separately.** Running the check on every PR does not prove that branch protection requires the check. Check names, event contexts, allowed bypasses and branch policies matter.

## 6. What an independent check can and cannot do

A deterministic architecture check can detect *the rules it implements*, not every form of architectural defect. Heuristic checks may produce false positives or false negatives. Their coverage and failure modes should be tested, and diagnostic warnings distinguished from errors.

Debt monitoring can deliberately run in **report-only** mode as part of evolutionary governance. A later policy can promote a metric regression to a blocking failure, provided the policy defines scope, thresholds, baseline validity and exception handling. Adding LOC or classes is not automatically a regression.

## 7. Applying one specification to different architectures

Two projects may share functional acceptance criteria while choosing different implementations, such as MVVM and Hexagonal architecture. Agents must obey the architecture selected **by their respective projects**. A methodology-neutral functional specification should avoid smuggling in mandatory design patterns that are not actually functional requirements.

See [the earlier Pokédex retrospective](CASE-STUDY-001-POKEDEX.md). It documents the lesson without reproducing any private application code.

## 8. Minimum readiness review

Before calling a governed change ready for acceptance, reviewers should be able to answer:

- Was the agent/developer operating under an authorized, bounded task?
- Was the applicable project architecture unambiguous?
- Were mandatory approvals recorded, not merely claimed?
- Did independent checks actually run on the relevant revision?
- Were failures addressed and any exceptions approved?
- Were existing baselines distinguished from newly introduced problems?
- If a check was called "blocking", is the integration boundary actually configured to require it?
- Was restricted information kept within the authorized environment?

See [Conformance & Evidence](CONFORMANCE.md) for the evaluation worksheet.

## 9. Relationship to existing practice

GADD does not replace SDD, TDD, DDD, code review, architecture fitness functions, CI or agent collaboration methods. It proposes a shared governance contract that can connect those existing practices, with explicit authority, conflict handling and evidence. The usefulness of this integration is a subject for real-world evaluation, not an established superiority claim.
