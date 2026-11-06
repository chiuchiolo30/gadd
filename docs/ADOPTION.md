# Adopting GADD v0.1 — practical assessment

GADD does not require a new platform. Start with the repository and the tools the team already uses.

## When GADD is most valuable

GADD is particularly relevant to organizations building or maintaining **sensitive, business-critical or high-consequence products**: systems that handle personal or confidential information, financial transactions, essential operations or safety-related workflows. The size of an organization is not the risk criterion; the **consequence of an incorrect, unauthorized or unverifiable change** is.

A low-risk prototype may benefit from lightweight governance, while a small team maintaining a safety-relevant product may need robust separation of duties, mandatory checks and reliable audit evidence.

## Choose controls based on risk

| Illustrative tier | Typical change context | Recommended governance posture |
|---|---|---|
| **Low** | Noncritical prototypes, isolated UI refinements | Explicit task, basic review and relevant tests; retain applicable mandatory controls |
| **Significant** | Business workflows, persistent data, interfaces used by customers | Documented policy and mandate, traceable decision, architecture and behavior checks, human review of consequential changes |
| **Critical** | Sensitive data, payments, safety-relevant operations, high-impact production systems | Strict least-privilege mandate, recorded approvals, independent evidence, appropriate security and regression tests, configured integration gates and exceptions reviewed by responsible humans |

These are **illustrative engineering risk tiers**, not a universal regulatory classification. A team must apply its own legal, contractual, privacy, safety and security requirements. GADD is not a substitute for a risk assessment or compliance program.

## Before adopting

1. Identify authoritative project policies and owners, with a version-controlled home.
2. Choose how agents receive mandates (agent configs, instructions, task interfaces).
3. Define which checkpoints require human decisions and how they are recorded.
4. Identify check commands that actually verify architecture, behavior and build integrity.
5. Decide which checks are advisory versus merge-blocking; configure CI/protection accordingly.
6. Establish how existing debt and authorized exceptions are recorded.
7. Verify that prompts, workflows and agent profiles do not contradict the canonical project policies.

## Evidence matrix

| Control | Documented | Observed | Enforced |
|---|---|---|---|
| Agent must follow project architecture | Canonical policy exists | Diff and validator results available | Validator prevents unauthorized acceptance |
| Agent must stop at approval | Approval checkpoint described | Approval event is recorded | Runner blocks step until approval |
| PR must pass checks | CI workflow exists | Run result linked to commit | Required check blocks merge |
| Debt must not regress | Baseline policy exists | Comparison report stored | Regression causes policy failure |

Mark a column as satisfied only when actual evidence exists. Do not mark a control enforced solely because its Markdown instructions say `MUST`.

## Common pitfalls

**Conflicting sources of truth:** for example, a generic agent profile mandating one architecture while the project-specific context requires another. Resolve by a documented precedence hierarchy and an automated consistency check where possible.

**False confidence:** a model says "all checks passed" without command logs, or a repository has a green CI result that is not required to merge.

**Unnecessary rigidity:** forcing heavy architectural steps on trivial changes instead of a proportional risk policy.

**Private information leakage:** using proprietary code or company-specific validators in public methodology examples. Publish synthetic examples or materials with explicit authorization.

## Suggested measurement

Compare agent-assisted changes over several iterations: policy violations per change, regressions after integration, human review effort, time spent correcting agent mistakes, proportion of checks with retained evidence and rate of authorized exceptions. Do not claim causal improvement without a fair comparison.
