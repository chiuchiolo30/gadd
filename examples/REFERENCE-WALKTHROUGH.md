# Synthetic walkthrough — Payment status feature

**This example is fictional. It does not reproduce any private implementation.**

A team wants to add a payment status screen in an arbitrary application. The codebase has a documented architectural style and a CI pipeline.

## Step 1 — Request

Outcome: a user can see the latest status of a payment. Acceptance criteria: loading, success, missing payment and network error are handled. No sensitive payment details are logged.

## Step 2 — Policy resolution

The project identifies its authoritative architecture file, naming conventions, data privacy rules, test commands and risk tier. Agent configurations refer to these sources and do not redefine them.

## Step 3 — Mandate

An architect agent may propose a design but cannot edit application code. A builder agent may modify files scoped to the approved feature; expanding the scope needs authorization.

## Step 4 — Design and approval

The architect proposes a plan linking each acceptance criterion to a component and test. The accountable owner approves the plan. Evidence: recorded approval reference.

## Step 5 — Implementation

The builder executes the plan, identifies changed files and adds tests. The builder's message is a summary, not proof of validity.

## Step 6 — Independent checks

The CI or local verification runner executes the project's actual analyzer, relevant tests, and architecture tests. Logs and results are attached to the change. Failed checks block acceptance or receive an explicit policy-compliant exception.

## Step 7 — PR integration

The pull request references the requirement and check results. When the team declares a check mandatory, its branch protection or equivalent mechanism enforces the merge requirement. A reviewer verifies deviations and records acceptance.

## Distinctive GADD lesson

The important property is not that an agent wrote the screen. It is that the proposed work had a bounded mandate, coherent project rules, independent evidence and a controlled acceptance decision.
