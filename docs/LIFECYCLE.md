# GADD reference lifecycle v0.1

The lifecycle is **a reference pattern**, not a universal command sequence. Teams may adapt steps to risk, technology and architecture while preserving the Core requirements.

```text
Human-defined intent and acceptance criteria
                │
                ▼
       Policy and scope resolution
                │
                ▼
       Agent mandate / delegation
                │
                ▼
   Plan and design ──► approval if required
                │
                ▼
       Implementation / change
                │
                ▼
      Deterministic validation
     (tests, build, architecture)
                │
                ├── failure ──► fix / documented exception
                │                        │
                │◄───────────────────────┘
                ▼
    Independent review / acceptance
                │
                ▼
    Pull request / integration checks
                │
                ▼
      Human acceptance / release
```

## Gates

**Gate A — authorization:** the objective, risk and allowed scope are sufficiently understood.  
**Gate B — design (where required):** plan/architecture is approved before implementation.  
**Gate C — technical evidence:** relevant independent checks ran and passed, or an authorized exception exists.  
**Gate D — integration:** branch/PR policy is applied and checked before merging.

## Roles

- **Accountable owner:** authorizes scope, accepts risk and outcomes.
- **Architect role:** proposes solution consistent with authoritative project policies.
- **Builder role:** implements the approved scope and reports factual changes.
- **Verifier:** executes tests, architecture rules and other machine-verifiable checks; should not rely only on the building agent's narrative.
- **Reviewer role:** compares outcomes to requirements, design and evidence.

Roles can be fulfilled by people, specialized agents and independent tools as appropriate. Role separation does not automatically imply independent evidence.

## Changes authored by people

GADD is not an exemption framework for humans. The same PR and acceptance criteria apply to human- and agent-authored code; only execution mandates specific to AI agents differ.

## Risk profiles (illustrative)

| Profile | Typical artifacts | Minimum decision points |
|---|---|---|
| Quick | request, acceptance criteria, code change, validation evidence | accept after checks |
| Standard | specification, plan, tasks, change, validation and review | approve design and acceptance |
| Critical | Standard + risk analysis, stakeholder approvals, expanded evidence | explicit approvals across risk gates |

No profile bypasses a mandatory project policy.
