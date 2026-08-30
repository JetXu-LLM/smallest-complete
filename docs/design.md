# Design

Smallest Complete is intentionally not an agent framework. It is a small
instruction system with one core Skill and two conditional references.

## The complete mechanism

```text
global AGENTS.md activation
        ↓
skills/smallest-complete/SKILL.md
        ├─ only for non-trivial coding or architecture work
        │  references/elegant-architecture.md
        └─ only when the choice of tests or other validation evidence is material
           references/evidence-calibrated-testing.md
```

### Global activation: remember when it matters

[`install/AGENTS.append.md`](../install/AGENTS.append.md) contains one paragraph.
It tells Codex when complex work should invoke the global Skill and preserves the
critical distinction between broad inquiry and bounded deliverables, changes,
and actions.

It does not duplicate the Skill body. Global context stays small.

### Core Skill: govern the current job

[`SKILL.md`](../skills/smallest-complete/SKILL.md) owns the cross-domain rules:

- reconstruct the user's current contract;
- separate direction from present authorization;
- resolve conflicting binding requirements before building;
- maintain one current explanation and route through long work;
- make additions earn their place;
- repair at an isolated owning boundary or reintegrate when local fixes no longer
  form one system;
- exercise representative real input through the intended receiver action early;
- validate the observable result;
- retain root whole-result acceptance without reassigning semantic ownership;
- calibrate claims to evidence;
- stop when the current job is complete.

This applies to coding, architecture, research, analysis, writing, documents,
presentations, and operations. It deliberately does not force software
architecture language onto ordinary knowledge work.

### Conditional architecture reference: shape code without bloating every task

[`elegant-architecture.md`](../skills/smallest-complete/references/elegant-architecture.md)
loads only for architecture, system design, non-trivial coding, refactoring,
migration, or debugging that may change structure or behavior.

Its defaults are:

- one clear control owner per end-to-end workflow;
- independently callable capability modules with explicit ownership;
- consumer-informed, domain-owned public contracts with current producers and
  real user outcomes as acceptance;
- decisions made only when their owner has enough information;
- one final owner for each semantic judgment;
- a small coordinator rather than several overlapping routers;
- durable business facts and only the recovery state a real requirement needs;
- local state that affects only its authorized scope;
- agent judgment for ambiguous, reversible cases;
- a useful value path inside minimum permission, privacy, integrity, legal, and
  irreversible-effect boundaries;
- further operational hardening only for a current contract, consumer,
  evidenced loss, or observed failure;
- repeated-run behavior that skips completed work and converges.

These defaults are not a universal topology. Distributed coordination and
stateful components are valid when present requirements, measured scale, or
material risk require them.

### Conditional testing reference: calibrate evidence without testing every task

[`evidence-calibrated-testing.md`](../skills/smallest-complete/references/evidence-calibrated-testing.md)
loads only when the choice of tests or other completion evidence materially
affects acceptance: an escaped failure, a receiver, operational, or real-run
claim, or a consequential choice among focused, broad, and full evidence.

It derives important failure scenarios from real losses, receiver work,
operational exposure, semantic impact, and escaped incidents. It then chooses an
oracle, observation boundary, test method, and execution scope that match the
claim; calibrates critical tests against plausible bad behavior and correct
alternatives; and limits green claims to the evidence actually observed.

Long-lived projects may preserve a compact validation map only when repeated
rediscovery justifies it and the current task authorizes documentation. The
reference defines no mandatory filename, schema, budget, state, or workflow.

## Why this structure

The project uses progressive disclosure. The activation paragraph is always
available, the core Skill loads for qualifying work, and each reference loads
only when its decisions are material.

That avoids two symmetric failures:

1. A short global slogan is too weak to guide difficult work.
2. Full architecture and testing doctrines in every conversation waste context
   and can distort simple work.

One Skill plus two conditional references keeps the methods available without
making either a permanent task protocol.

## The addition gate

An addition to the deliverable, implementation, workflow, or set of actions must
be justified by at least one of four things:

1. the requested result or its acceptance evidence;
2. a current hard rule, material safety constraint, or irreversible effect;
3. observed evidence that the primary path cannot complete without it;
4. explicit user authorization for the expanded result.

For a requested research, writing, or creative artifact, an addition may also
earn its place when it materially improves that artifact for its intended reader
without changing its purpose, audience, format, or external action surface.

This is a judgment rule, not a policy engine. The Skill leaves room for capable
reasoning while giving that reasoning a stable boundary.

For a declared handoff, the public contract is also an information boundary.
Design it backward from the receiver's job, visible facts, and next action.
Consumers inform the business meaning, the domain capability owns it, and the
user's real outcome validates it. A clean receiver should be able to act without
producer internals, semantic repair, or a private explanation. This does not
justify one universal schema: different business facts may have different
contracts, and internal helpers need none.

## Why there is no runtime

Smallest Complete currently has no:

- lifecycle hook;
- daemon or background process;
- task database or recovery state machine;
- telemetry or remote service;
- mandatory checklist executor;
- mode hierarchy or intensity dial;
- deterministic blocker for file edits.

Those mechanisms could improve enforcement in some environments, but they also
create installation cost, context cost, failure modes, and a second system whose
scope must be governed. The current evidence does not show that they are needed
for the first useful version.

The harness still owns permissions, sandboxing, and approval for irreversible
effects. This Skill neither grants nor bypasses authority.

## Why the installer is an instruction, not a script

Codex already knows how to read files, compare content, preserve a user's global
instructions, create a backup, and validate a copy. A dedicated installer would
duplicate capabilities already present in the environment and would need its own
cross-platform implementation and maintenance.

[`INSTALL.md`](../INSTALL.md) instead gives Codex a low-freedom procedure for the
fragile parts: exact source and target files, idempotency, conflicts, backups,
validation, and rollback. The agent adapts path details to the current machine;
deterministic comparisons protect the copied content.

## How the project may grow

New permanent machinery should answer the same question the Skill asks of user
projects:

> What required behavior or hard rule would fail today if this were omitted?

Evidence that could justify expansion includes repeated activation failures that
metadata cannot solve, observed unsafe installation behavior, a supported plugin
distribution requirement, or evaluation results showing a specific missing
mechanism. Popularity alone is not evidence that the architecture needs another
layer.
