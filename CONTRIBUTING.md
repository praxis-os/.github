# Contributing to Praxis OS

Contributions are welcome. This guide explains what we expect and how to work with us effectively.

## Before you contribute

Read this document fully before opening a pull request. Praxis OS has deliberate architectural boundaries, and contributions that ignore them will be asked to restructure.

If your change is non-trivial — new public API, new subsystem, changed behavior — open an issue or proposal first. We would rather align on direction before you invest significant effort.

## What belongs where

Praxis OS is built in layers. Contributions must respect these boundaries:

- **`praxis`** owns single-invocation runtime semantics: the state machine, policy hooks, budget enforcement, error taxonomy, observability, tool invocation, and trust boundaries.
- **`praxis-os`** (future) will own higher-level orchestration: multi-step workflows, coordination patterns, and control-plane primitives.
- **Hosted platform concerns** (observability dashboards, governance UIs, commercial operational tooling) should not be back-projected into kernel or orchestration repository scope.

If you are unsure where a contribution belongs, ask in an issue before writing code.

## Issue first vs. PR first

| Change type | Start with |
|---|---|
| Bug fix with clear reproduction | PR is fine |
| Small documentation improvement | PR is fine |
| New feature or public API change | Issue or proposal first |
| Architectural or design change | Proposal first |
| Cross-repo or cross-layer concern | Proposal first |

## Design expectations

- Prefer explicit interfaces and typed contracts over implicit behavior.
- Preserve observability and policy enforcement as first-class design elements — do not bypass or weaken them.
- Avoid generic abstraction creep. A concrete, well-bounded implementation is better than a premature generalization.
- Respect the typed error taxonomy. New error paths should integrate with existing retry and reporting semantics.
- Consider budget enforcement implications. Changes that affect token consumption, tool call counts, or timing should account for budget guardrails.

## Development expectations

- Write tests for meaningful behavior changes. Unit tests for logic, integration tests for lifecycle and boundary behavior.
- Do not introduce dependencies without justification. The dependency footprint matters.
- Follow existing code conventions. If the codebase uses a pattern, match it unless you have a strong reason to diverge (and explain that reason).
- Keep commits focused. One logical change per commit where practical.

## Documentation expectations

- Meaningful code changes should include documentation updates where appropriate.
- Public API additions or changes require doc updates.
- If your change affects how users interact with the system, update the relevant guides or examples.

## Review expectations

Pull requests should explain:

- **What changed** — a clear summary of the modification.
- **Why it belongs in this repository** — which layer this targets and why it fits there.
- **Whether public API is affected** — new types, changed signatures, removed functionality.
- **Whether observability, budgets, security, policy, or trust boundaries are affected** — these are first-class concerns and reviewers will ask.
- **Whether it introduces breaking behavior** — callers, configurations, or integrations that would need to change.

Expect review to be direct and focused on correctness, boundary discipline, and operational implications.

## Scope discipline

This project is deliberately narrow in scope at each layer. Contributions that expand scope should justify themselves clearly:

- Do not mix kernel and orchestration concerns in a single change.
- Do not add features that assume a specific deployment topology or commercial platform dependency.
- Do not add configuration options for hypothetical future requirements. Solve the problem at hand.
- Do not weaken type safety, observability hooks, or policy enforcement for convenience.

We value restraint. The right contribution is often smaller than you think.
