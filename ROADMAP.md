# Roadmap

This roadmap is directional. It reflects current priorities and planned evolution, not a promise of simultaneous delivery.

## Current focus

Active development across two layers of the stack:

**[`praxis`](https://github.com/praxis-os/praxis)** — the invocation kernel:

- Invocation lifecycle correctness and state machine semantics
- Typed error taxonomy with differentiated retry policies
- Four-phase policy hook model (input validation, pre-execution, post-execution, output filtering)
- Budget enforcement across four dimensions: wall-clock time, token consumption, tool call count, cost
- Cancellation propagation and graceful shutdown behavior
- Filter and hook extension surfaces
- Tool invocation seams with identity signing
- Trust boundary enforcement
- OpenTelemetry tracing and structured lifecycle events
- Provider-agnostic LLM interface (Anthropic adapter shipped, OpenAI planned)

**[`praxis-forge`](https://github.com/praxis-os/praxis-forge)** — declarative agent definition, composition, and materialization:

- Typed `AgentSpec` loader with strict validation
- `ComponentRegistry` with 11 typed factory kinds
- Composition adapters and materialization into a real `praxis` `Orchestrator`
- External registry support (dev-time only)

## Near-term

- [`praxis-docs`](https://github.com/praxis-os/praxis-docs) — documentation site content and public launch
- [`praxis-examples`](https://github.com/praxis-os/praxis-examples) — representative usage patterns and reference agents
- [`praxis-benchmarks`](https://github.com/praxis-os/praxis-benchmarks) — public release of benchmark results
- Expanded contributor documentation and development guides
- Public design artifacts and RFC process

## Mid-term

- **`praxis-os`** — orchestration layer above the kernel
- Multi-step orchestration semantics and coordination patterns
- Workflow composition primitives
- Control-plane abstractions for managing agent graphs

## Longer-term ecosystem direction

- Hosted control plane for observability, governance, and operations (future, commercial)
- Evaluation, audit, and compliance tooling
- Deeper governance workflows for production agent deployments

Not every ecosystem component will become a public repository at the same time. The hosted platform direction is a separate concern from current open-source commitments, and its structure will be defined when the time is right.

## What is intentionally not public yet

- This roadmap is directional guidance, not a guarantee of specific repository creation timelines.
- Future hosted platform work is not represented as a public repository commitment at this stage. That direction exists, but its scope, licensing, and delivery model are still being shaped.
- Items listed under longer-term ecosystem direction may change substantially as the kernel matures and real production usage informs priorities.
