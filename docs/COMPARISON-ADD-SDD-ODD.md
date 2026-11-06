# GADD, ADD, SDD and ODD — a technical comparison

**Document status:** Technical comparison for GADD v0.1.0, reviewed November 6, 2026.  
**Scope:** Comparison with representative, currently documented approaches. **SDD** here refers primarily to the **GitHub Spec Kit** implementation; SDD is a broader family of practices, not a single proprietary methodology. **ADD** refers to [Agent Driven Development at getadd.dev](https://getadd.dev/docs/). **ODD** refers to [Organic Driven Development described in Gentle AI](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md). **GADD** refers to this repository's [Core proposal](CORE.md). These references may change over time.

## Executive summary

GADD (Governed Agent-Driven Development) is a **proposed governance-oriented, risk-driven software engineering methodology** for development with AI agents, with particular relevance to sensitive and business-critical systems. It is **not** a replacement for requirements engineering, SDD, TDD, DDD, ADD or ODD, and does not claim to have invented approval gates, role-based agents, independent verification or CI. Those practices predate GADD and occur in other approaches.

The distinguishing **design emphasis** GADD proposes is an explicit, auditable agreement between (a) authoritative project policy, (b) authorized agent mandates and human decisions, (c) independent evidence about actual changes, and (d) acceptance/integration enforcement. This design should apply regardless of the code's human or agent authorship or the architecture selected by the project.

The proposal is **grounded in practical evidence rather than an untested idea**: a publicly discussed demonstration of one feature implemented under two distinct architectural policies, and observed use of executable architectural checks in real projects. These observations support key mechanisms; they **do not establish universal GADD conformance, verified branch-level enforcement in every environment, or superiority over SDD, ADD or ODD**. The comparative benefits and transferability of the complete methodology remain open to measurement.

## 1. Comparison at a glance

| Dimension | SDD (GitHub Spec Kit reference) | ADD (getadd.dev) | ODD (Gentle AI) | GADD v0.1 proposal |
|---|---|---|---|---|
| Primary organizing question | What must be built, and how do artifacts carry intent into implementation? | How should coordinated AI agents develop, verify and ship software as a team? | How do we scale agent workflow to understanding, risk and resumability without unnecessary ceremony? | Who may authorize each action, which policies are authoritative, and what verifiable evidence permits acceptance? |
| Main operating unit | Specification, plan, tasks, implementation and convergence | Feature specs, agent roles, TDD cycles and quality gates | A request or a recoverable feature document, with proportionate work units | A governed change with mandate, relevant policy version, evidence and acceptance decision |
| Project instructions / architecture | Has a project constitution and plan; cross-artifact consistency analysis | Includes project setup, architecture guidance and roles | Respects repo policies; explores existing conventions | Requires an authoritative policy hierarchy with a conflict-resolution rule |
| Human involvement | Review of phase artifacts and clarification | Multiple engagement modes, including explicit human approval | Authorization and context-dependent decisions | Identified accountable human role; scope and risk determine approval checkpoints |
| Independent verification | Checklists, consistency analysis and convergence, plus project testing as configured | TDD RED/GREEN/REFACTOR/VERIFY, independent verification and quality gates | Test-first where suitable; observed checks and optional bounded review | Requires evidence outside the producing agent's unsupported assertion for applicable properties |
| Risk / proportionality | Short and more rigorous process variants; extensible workflows | Maturity-dependent rigor and autonomy modes | Explicitly proportional to understanding, risk and ability to resume | Risk tier can vary process overhead, but must preserve applicable mandatory policy |
| PR / integration enforcement | Can be integrated with CI and additional gates; the SDD process itself is not evidence that branch protection is enabled | Provides quality/ship gates; enforcement depends on configured runtime/CI | Honors existing repository and delivery gates, with optional review controls | Explicitly distinguishes documented, observed and **actually enforced** controls, including required checks for merge |
| Language / architecture | Many agents and tech stacks | Runtime-neutral methodology with specific adapters | Multiple agent runtimes | Methodology requires no particular tool or architecture |

**Reading rule:** This table summarizes *emphasis and documented mechanisms*, not the absence of features in other systems. For example, ADD also has scoped permissions and verification, and ODD also has explicit authorization and evidence. GADD cannot credibly claim exclusivity over these elements.

## 2. SDD — Spec-Driven Development

The GitHub Spec Kit reference implements a structured path: constitution → specify → clarify → plan → checklists → tasks → analyze → implement → converge. Its `/speckit-analyze` examines cross-artifact consistency, and its convergence step compares implementation against intended work.

**Direct overlap:** GADD uses requirements, plans, traceability and checks. GADD should be able to incorporate an SDD process for intent and implementation without duplicating its value.

**Proposed GADD extension:** Treat the specification as one part of the governance system, alongside agent permissions, policy authority, approvals, actual validator outputs and documented integration enforcement. A well-written spec or constitution by itself does not establish that an agent followed it or that a PR is protected.

**Avoid this false comparison:** “SDD has no governance.” Spec Kit has a constitution, verification steps, consistency analysis and customizable gates. The difference is the explicit *object of evaluation* in the GADD proposal.

Source: [GitHub Spec Kit — quickstart](https://github.github.com/spec-kit/quickstart.html).

## 3. ADD — Agent Driven Development

ADD explicitly treats agents as a coordinated team: spec-writing, test-writing, implementation, independent verification, decisions and deployment. Its documentation includes roles, permission scopes, collaboration modes, maturity-dependent checks and RED → GREEN → REFACTOR → VERIFY.

**Direct overlap:** This is the closest conceptual neighbor to GADD. It already addresses agent delegation, boundaries, human decisions and independent verification.

**Proposed GADD extension / distinction of emphasis:** GADD describes governance as a **tool-independent assessment contract** that can be applied to a human-authored or agent-authored change, with an explicit evidence matrix for policies, approvals, baselines, violations, exceptions and branch integration. It is not prescriptive about TDD cycles or an agent-team topology.

**Avoid this false comparison:** “ADD lets agents work without controls.” Its published guidance explicitly imposes controls. Whether GADD yields **additional comparative benefits** beyond ADD—such as fewer regressions or lower review overhead in comparable projects—requires measurement and independent feedback. This does not negate the practical evidence of architecture-specific governance and executable checks.

Source: [ADD documentation](https://getadd.dev/docs/).

## 4. ODD — Organic Driven Development

ODD's published protocol authorizes changes, explores context, classifies work by size/risk/resumability, keeps small understood work lightweight, uses a recoverable feature document for substantial work and runs proportionate tests. Gentle AI also documents bounded review and delivery behavior.

**Direct overlap:** GADD likewise values proportionality, authorization, task context and verified outcomes.

**Proposed distinction of emphasis:** ODD focuses on how work is routed and scaled without needless process; GADD focuses on what makes governing rules, delegation authority and acceptance **auditable and, where mandated, independently enforced**, whether the work is small or large.

**Avoid this false comparison:** “ODD means no specs, tests or governance.” Its actual documentation includes all of these when appropriate.

Source: [Gentle AI — Organic Driven Development](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md). That file documents the current main branch and may differ from tagged releases.

## 5. What GADD is, and is not, claiming

**Proposed contributions:**

1. A common assessment model for governance at **Documented / Observed / Enforced** levels.
2. A requirement to reconcile conflicting governance artifacts and establish authoritative policy precedence.
3. Explicit traceability from delegation to change, checks, exceptions and acceptance.
4. An approach applying architectural constraints to agent and human changes alike.
5. An architecture-neutral methodology that permits different project-specific governance under an identical functional requirement.
6. A clear separation of local agent workflow guidance, deterministic validation and branch/integration controls.

These items are a **coherent proposed combination and emphasis**, not individually unprecedented inventions.

**Not claimed:** First use of agent-driven development, independent agent review, architectural policy, SDD, TDD, CI validation, risk-based gates, human approval or debt baselines.

## 6. Earlier public demonstration: one spec, two architectures

A Flutter Tucumán event titled **“Arquitectura Flutter en serio: gobernanza, capas y buenas prácticas”** was listed for **11 June 2026, 20:00 Argentina**. A community post about its Pokédex demo describes the same feature requirements implemented under **MVVM** and **Hexagonal architecture**, with different structure, responsibilities and dependencies.

This illustrates GADD's foundational principle that a common product requirement need not dictate one technical architecture: **intent describes what; project governance determines permissible implementation**.

The example precedes the name and public proposal “GADD” as formulated here. It should **not** be presented as evidence that GADD already existed under that name or that every proposed control was enforced.

- [Meetup event (public listing; direct page access may vary)](https://www.meetup.com/es-es/flutter-tucuman/events/314892755/)
- [Flutter Tucumán's public post discussing the Pokédex example](https://es.linkedin.com/posts/flutter-tucum%C3%A1n_flutter-fluttertucuman-dart-activity-7471973622002266112-k-aI)
- [Retrospective case study](CASE-STUDY-001-POKEDEX.md)

## 7. Existing practical evidence and ongoing evaluation

GADD is **not a method devised without practical precedent**. Its core principles consolidate earlier engineering experience. The correct question is which observations already support those principles, and which broader outcomes still require independent evaluation.

### 7.1. What has already been observed

- **Public architectural demonstration (June 2026).** The same Pokédex feature requirements were implemented in separate Flutter projects governed by MVVM and Hexagonal policies. The observed source structures followed different project architecture choices. This supports the feasibility of **project-specific governance without prescribing a single universal architecture**. See the [retrospective](CASE-STUDY-001-POKEDEX.md).
- **Executable architectural checks in practice.** Real-world experience includes independently executed architecture checks with both successful and failing outcomes. This demonstrates that some rules **can be checked outside an agent's self-report**. Third-party project artifacts, proprietary tools and private logs are not published in this repository.
- **Policy drift identified in retrospective review.** The Pokédex example surfaced inconsistencies between implementation patterns and planning documents, motivating explicit source-of-truth precedence and policy coherence checks.

### 7.2. What this evidence does not prove

A validator failing on a violation establishes an **executable check**, but not, by itself, that branch protection prevented merging, all approvals took place, or every functional acceptance criterion passed. The June demonstration also predates the publication and name of GADD: **the methodology now formalizes these existing principles and experiences**.

### 7.3. What we will evaluate next

Future comparisons are intended to **quantify benefits, limitations and transferability**, not to suggest the core practices have never worked. Select comparable changes and measure:

- **Policy conflicts:** contradictions detected before implementation.
- **Unauthorized scope:** deviations caught, escalated or blocked.
- **Evidence completeness:** proportion of changes with retained check output and acceptance records.
- **Integration controls:** checks run versus checks actually required before merge.
- **Architectural regressions:** new violations relative to accepted baselines.
- **Operational overhead:** human review time and process cost.
- **Independence:** consistent outcomes across agents, runtimes and architectures.

The resulting evidence should refine GADD and establish when the benefits justify the costs. **Additional evaluation extends the scope of prior observations rather than erasing them.**

## 8. Positioning statement

> **SDD helps carry intent into implementation. ADD coordinates agent development. ODD scales agent workflow organically. GADD proposes a verifiable governance contract for delegating and accepting software changes across architectures and tools.**

This is a **comparative shorthand**, not a universal definition of SDD, ADD or ODD. They can be combined rather than treated as competitors.

## Primary sources (consulted 2026-11-05)

- GitHub: [Spec Kit documentation](https://github.github.com/spec-kit/), [quickstart](https://github.github.com/spec-kit/quickstart.html).
- ADD: [Agent Driven Development documentation](https://getadd.dev/docs/), [overview](https://getadd.dev/).
- ODD: [Gentle AI README](https://github.com/Gentleman-Programming/gentle-ai), [ODD usage protocol](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md).
- GADD: [Core](CORE.md), [conformance model](CONFORMANCE.md), [case study](CASE-STUDY-001-POKEDEX.md).
