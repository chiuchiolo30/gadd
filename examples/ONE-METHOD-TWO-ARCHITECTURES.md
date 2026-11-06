# One governance method, two architectures (synthetic)

**Fictional demonstration only.** The patterns below are illustrative and are not copies of any private repository.

GADD does not tell every team to use the same architecture. Its requirement is that agents follow **the architecture authorized for the project**, not their preferred architecture.

| Decision | Project A: MVVM | Project B: Hexagonal / Clean |
|---|---|---|
| Presentation | View and ViewModel | UI and state manager |
| Business coordination | Repository via ViewModel, optional dedicated domain use cases | Dedicated domain use cases and ports |
| Infrastructure | Services and data models isolated from Views | Adapters implement domain ports |
| Forbidden shortcut | View calling a remote service directly | UI importing concrete persistence adapter |
| Shared GADD gate | Agent reads project policy, scope is approved, relevant static checks run, integration follows acceptance policy | Agent reads project policy, scope is approved, relevant static checks run, integration follows acceptance policy |

## A governed agent's decision

A user asks an agent to add a screen. The agent first identifies which project is active and reads its authoritative architecture contract.

- If Project A uses MVVM and its design says business actions belong in the ViewModel, the agent must not invent a mandatory pass-through use-case layer simply because a familiar template suggests it.
- If Project B requires use cases and domain ports, the agent must not bypass them to make a faster network call from the UI.

In both projects, the task has a bounded mandate, the resulting change is evaluated against the chosen architecture, the validation result is retained and the acceptance gate is applied.

## Important distinction

A prompt saying "never bypass use cases" is only guidance. An independently executed check demonstrating that layer boundaries are intact is stronger evidence. A required CI check that blocks integration is stronger enforcement still. GADD requires teams to describe these guarantees accurately.

## The coherence problem

A generic instruction file and an architecture-specific agent file can contradict each other. The team must resolve that conflict by identifying an authoritative source, specifying precedence, and preferably adding automated policy-consistency tests. An agent should not silently choose whichever rule is more convenient.
