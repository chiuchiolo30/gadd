# The GADD Manifesto — v0.1.0 (Initial Release)

We believe software development with AI agents must remain accountable engineering, not uncontrolled code production.

Agent autonomy can improve throughput. It cannot replace responsibility for requirements, architectural choices, acceptable risk or delivered behavior.

We value:

- **Authorized decisions over autonomous assumptions.** Agents implement within explicit mandates and request approval when crossing a boundary.
- **Project-specific governance over one-size-fits-all generation.** A codebase's architecture and constraints are decided for that codebase, not chosen by the agent's preferences.
- **Executable evidence over claims of success.** Tests, architecture checks and other independent signals matter more than a plausible final message.
- **Traceability over opaque changes.** Teams should connect intentions to plans, code changes and verification results.
- **Policy consistency over duplicated instructions.** Conflicting rules across agent files, workflows and validations must be detected and resolved.
- **Human accountability over ceremonial approvals.** Approval gates must have a named responsible role and a meaningful decision.
- **Pragmatic proportionality over ritual.** Low-risk tasks should stay lightweight; consequential changes require stronger controls.
- **Interoperability over vendor dependence.** The methodology belongs to engineering practice, not a particular agent or product.

In practice, this means:

1. Define outcomes, acceptance conditions and constraints before delegating significant work.
2. Give agents bounded roles, inputs, permitted operations and stop rules.
3. Review designs and plans at risk-appropriate checkpoints.
4. Treat code generation and evidence gathering as separate responsibilities.
5. Block acceptance when relevant mandatory checks fail, and record justified exceptions.
6. Distinguish pre-existing debt from regressions introduced by a change.
7. Apply the same quality conditions to human-authored and agent-authored changes.

**Core statement:** *Agents may drive execution; governance determines authority; evidence determines readiness; humans remain accountable.*

This manifesto proposes a direction. The [GADD Core](CORE.md) states testable minimum expectations.

**Author:** Sergio Edgardo Chiuchiolo · **Project identity:** Chiuchiolo Labs (independent initiative).
