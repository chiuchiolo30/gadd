# Case Study 001 — One Pokédex specification, two architecture policies

**Status:** Documented retrospective (v0.1), not a controlled scientific experiment.  
**Context:** This case reflects the practical Pokédex demonstration discussed in the Flutter Tucumán online event **“Arquitectura Flutter en serio: gobernanza, capas y buenas prácticas” (11 June 2026, 20:00 ART)**. A [public community post](https://es.linkedin.com/posts/flutter-tucum%C3%A1n_flutter-fluttertucuman-dart-activity-7471973622002266112-k-aI) describes the same spec implemented under MVVM and Hexagonal governance. The [Meetup event page](https://www.meetup.com/es-es/flutter-tucuman/events/314892755/) is linked for historical reference, although its full contents were not accessible during this review. The supporting source repositories remain private and are **not distributed or linked here**.  
**Verification scope:** The two private source trees and their specification artifacts were inspected in preparation for this draft. No tests were executed as part of this documentation review.

## Question

Can a developer ask AI agents to implement the **same product requirements** while different project-specific governance policies yield different valid architectural implementations?

## Setup

Two isolated Flutter demonstration projects were given the exact same Pokédex feature specification. The specification described a paginated list of Pokémon from a public API, with names, artwork, loading, empty and error states, automatic pagination and retry behavior. Ten acceptance criteria were defined.

Both projects used agent-facing instructions, specialized roles, a feature workflow and architecture validation tools. Their governing architectural decisions differed.

| | Example A | Example B |
|---|---|---|
| Chosen architecture | MVVM | Hexagonal / Clean |
| Presentation logic | ChangeNotifier ViewModel with Commands | Cubit with explicit state |
| Application boundary | ViewModel invokes Repository | Cubit invokes UseCase |
| Error carrier | Result | Either with typed Failure |
| Infrastructure | Repository and Service | Domain repository port and Data adapter |
| Governance effect | Prevents unnecessary mandatory UseCase and BLoC layers | Requires domain isolation and explicit UseCases |

The implemented source trees exhibit these different patterns. The functional goal remains the same; the policy changes the construction approach.

## What this establishes

1. The shared functional specification can be reused between different architectural implementations.
2. Project-level governance can describe architecture-specific roles, constraints and expected artifacts for agents.
3. The observed implementation structures differ consistently with their project architecture.
4. GADD should be architecture-independent **as a methodology**, while each project policy remains architecture-specific.

## What this does not establish

- This documentation review did not rerun Flutter tests, live API scenarios or architecture validators.
- No independently retained approval events or enforcement logs were evaluated.
- The mere presence of STOP rules in Markdown does not prove that an agent was technically blocked from advancing.
- A shared specification and visibly different source trees are not proof that **all** acceptance criteria passed at runtime.
- This is not a controlled comparison of time-to-delivery, failure rates or productivity.

## Lessons and issues revealed by the retrospective

**1. Keep requirements distinct from implementation.** The shared specification expresses a technology-neutral intention but also includes a technical-capabilities section that mentions a required UseCase path. This does not fit equally well with an MVVM policy in which dedicated UseCases are optional. Future methodology guidance should distinguish functional acceptance criteria from optional or architecture-specific design assumptions.

**2. Validate generated artifacts against current policy.** In the MVVM example, the implemented feature uses a ViewModel and Repository, but an associated technical plan still describes a Clean Architecture/Cubit flow. This divergence is an example of **policy and artifact drift**. GADD should require an effective source-of-truth hierarchy and coherence checks for plans, tasks and agent instructions.

**3. Separate guidance from enforcement.** The demonstration contains architecture rules and local validation tooling. To claim that a particular gate is **enforced**, an observer would also need evidence that the gate ran and prevented unauthorized progression or integration.

## GADD principle illustrated

> The same intent should not require the same internal architecture. Governance defines the implementation boundaries, agents execute within them, and independent evidence determines readiness.

## Reproducibility and confidentiality

This case study deliberately paraphrases high-level observations and does not reproduce proprietary material, private code, private file names, validation implementations or private commit identifiers. An independently reproducible public demo, if later authorized, should use newly authored code and publish its own run logs and test results.
