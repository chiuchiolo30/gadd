# GADD — Governed Agent-Driven Development

**Version:** v0.1.0 · Initial Release  
**Created by:** Sergio Edgardo Chiuchiolo  
**Independent initiative:** Chiuchiolo Labs  
**Initial release:** November 6, 2026

> Delegate execution to agents. Preserve engineering authority through governance and verifiable evidence.

**Chiuchiolo Labs** is the independent project identity used by the author, not a claim of a registered company or trademark.

GADD is a **governance-first, risk-driven software-engineering methodology proposal** for integrating AI agents into development. Its strongest intended use is in **sensitive, business-critical, or high-consequence systems**, where changes require explicit human accountability, coherent project policies, traceability, independent verification, and controlled integration.

It is usable in lower-risk projects, but controls SHOULD scale to the risk of the product and change; a lightweight prototype does not need the same process overhead as a regulated or business-critical system. The relevant criterion is **consequence of failure**, not company size.

**GADD does not, by itself, certify safety, security, regulatory compliance, or freedom from defects.** Each organization must identify its obligations, establish controls, and verify their actual enforcement.

GADD is **not** a programming language, coding assistant, architecture style, IDE extension, or AI model. It does not require Clean Architecture, MVVM, DDD, a particular agent framework, or any specific product.

## The problem

AI agents can produce code quickly, but code production is not equivalent to authorized, reviewable, architecture-compliant engineering. Project instructions alone do not guarantee compliance. GADD separates authority, delegated execution, verifiable evidence, and acceptance.

## Core principles

1. **Human accountability** — a named human role owns objectives, risk and acceptance decisions.
2. **Explicit delegation** — agents have defined tasks, permitted actions and stop conditions.
3. **Coherent governance** — architecture, conventions and workflow policies are project-specific, versioned and free of unresolved contradictions.
4. **Traceable evolution** — requirements, decisions, changes and verification evidence can be connected.
5. **Independent verification** — a successful agent response is not proof of correctness; relevant checks run outside the agent's self-assessment.
6. **Controlled integration** — evidence and required checks inform the decision to accept or merge changes.
7. **Proportional process** — controls are commensurate with risk and complexity, without skipping mandatory safeguards.
8. **Tool independence** — teams can use different models, agents, CI systems and architectures.

Read the [Manifesto](docs/MANIFESTO.md), [Core specification](docs/CORE.md) and [Lifecycle](docs/LIFECYCLE.md).

## What GADD requires, and what it does not

A team can adopt GADD without a proprietary tool. A workflow must identify who authorizes work, what policies apply, how conflicts are resolved, what evidence is required and what blocks acceptance. A policy file that tells an agent to run tests is **guidance**; it is not evidence that tests ran. A passing optional CI job is not the same as a branch-protection rule that prevents merge.

GADD complements rather than replaces Spec-Driven Development (SDD), Test-Driven Development (TDD), Domain-Driven Design (DDD), Clean Architecture or MVVM.

## Contents

- [Manifesto](docs/MANIFESTO.md)
- [Core: normative vocabulary and minimum requirements](docs/CORE.md)
- [Reference lifecycle](docs/LIFECYCLE.md)
- [Governance Contract — reference model](docs/GOVERNANCE-CONTRACT.md)
- [Contrato de gobernanza — español](docs/es/CONTRATO-DE-GOBERNANZA.md)
- [Conformance and evidence model](docs/CONFORMANCE.md)
- [Adoption and evidence assessment](docs/ADOPTION.md)
- [An original, synthetic example](examples/REFERENCE-WALKTHROUGH.md)
- [Same governance, different architectures](examples/ONE-METHOD-TWO-ARCHITECTURES.md)
- [Earlier Pokédex demonstration (June 2026)](docs/CASE-STUDY-001-POKEDEX.md)
- [Comparison: GADD vs. ADD, SDD and ODD](docs/COMPARISON-ADD-SDD-ODD.md)
- [Comparación en español](docs/es/COMPARACION-ADD-SDD-ODD.md)
- [Spanish manifesto](docs/es/MANIFIESTO.md)
- [Spanish overview](docs/es/README.md)

## Status and origin

This is an initial written formulation based on practical experimentation with architecture-governed, agent-assisted development in multiple projects. It makes no claim to have invented agent-driven development, approval gates, independent code review, or architecture tests. The origin timeline, comparative research and validation evidence will be expanded as sources are verified and reviewed for confidentiality.

No private repositories, company-specific architectures, unpublished source code, proprietary validators, internal infrastructure, or confidential project details are included in this package.

## How to use GADD

Start with the [Manifesto](docs/MANIFESTO.md), read the [Core specification](docs/CORE.md), and adapt the [Governance Contract](docs/GOVERNANCE-CONTRACT.md) to your own project. Use the [Lifecycle](docs/LIFECYCLE.md) and [Conformance model](docs/CONFORMANCE.md) to separate documented guidance, observed execution and enforced controls. See the [synthetic walkthrough](examples/REFERENCE-WALKTHROUGH.md) for a tool-independent example.

GADD is an evolving **methodology proposal**, not a product, a certification, or a claim that all controls are automatically implemented by reading this repository. See [Risk-sensitive adoption](docs/ADOPTION.md) before deciding what governance rigor is appropriate.

## Participate

Feedback should focus on falsifiable claims: which decisions can be delegated, which gates are truly enforced, which evidence is retained and whether the process reduces regressions without imposing undue overhead. Contributions should not contain confidential code, client information, internal policy files, private validation tools, or unpublished employer materials.

## Attribution and license

**Created by Sergio Edgardo Chiuchiolo** — an independent initiative from **Chiuchiolo Labs**. It is a project identity, not a claim to a registered company or trademark.

Original methodology documentation and original Markdown examples are licensed under **[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE.md)**. You may share and adapt the licensed material, including commercially, with attribution and an indication of changes. See the [license notice](LICENSE.md) and [citation metadata](CITATION.cff) for the citation format and scope. CC BY 4.0 is not a trademark license, and no trademark registration is claimed.