# Praxis OS

Production-grade Go ecosystem for building and operating agentic systems.

## What exists today

- **[`praxis`](https://github.com/praxis-os/praxis)** — the runtime kernel. A Go library for orchestrating LLM agent invocations with a typed finite state machine, four-phase policy hooks, budget enforcement, structured error taxonomy, and mandatory OpenTelemetry observability. This is the current public focus.
- **[`praxis-docs`](https://github.com/praxis-os/praxis-docs)** — documentation, guides, and design artifacts for the Praxis OS ecosystem.

## Planned layers

- **`praxis-os`** — orchestration layer above the kernel. Multi-step coordination, workflow composition, and higher-level control-flow primitives. Not yet public.
- **examples / benchmarks** — dedicated repositories for usage examples and performance benchmarks. In preparation.
- **Hosted control plane (future, commercial)** — observability, governance, and operational tooling delivered as a hosted service. Separate from current open-source scope.

## Why this exists

Most agent frameworks optimize for demo speed. Praxis OS optimizes for operational correctness:

- Explicit control flow over implicit magic
- Runtime state machine with well-defined transitions
- Observability and tracing as framework guarantees, not afterthoughts
- Policy enforcement at every lifecycle boundary
- Budget guardrails (wall-clock, tokens, tool calls, cost) built into the kernel
- Trust boundaries and identity signing for tool invocations
- Typed error taxonomy driving differentiated retry behavior

The goal is infrastructure you can run in production, audit under pressure, and explain to your security team.

## Start here

**[`praxis`](https://github.com/praxis-os/praxis)** is the entry point. Start with the kernel.

## Project status

Early and intentional. The kernel API is taking shape but has not reached v1.0 stability. Interfaces may evolve. The scope is deliberately narrow — single-invocation runtime semantics first, orchestration later. The quality bar is high; the maturity claim is not.

## Contributing

See the organization [contributing guide](https://github.com/praxis-os/.github/blob/main/CONTRIBUTING.md) for expectations around scope, design, and review.
