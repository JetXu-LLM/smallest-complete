---
name: smallest-complete
description: "Complete non-trivial work once its objective, authorization, decision frame, and acceptance criteria are stable enough to act: choose the smallest fully working route, preserve required behavior, validate the actual outcome including the receiver boundary when material, and stop within scope. Use for multi-step, delegated, resumed, design, implementation, debugging, refactoring, migration, artifact, document, presentation, operational, or final-synthesis work whose main challenge is bounded execution and completion. If the central uncertainty is still the value function, problem boundary, causal or evidence model, decision owner, time horizon, or governing principle, stop convergence and return to framing before proceeding. Do not use for simple questions or trivial transformations."
---

# Smallest Complete

Deliver the smallest result that fully completes the user's current job. “Smallest” does not mean a partial prototype, the fewest changed lines, or the quickest plausible output. It constrains what becomes permanent or delivered, not the inquiry and validation needed to make the result real.

The requested observable outcome—not implementation volume, test count, elapsed time, or producer effort—is the unit of completion.

## Lead only when the contract is coherent

Lead convergence, design, execution, validation, integration, and closure only after the job is stable enough to act. Do not use this skill to decide which objective, value function, causal model, owner, or evidence standard is correct.

Before acting, identify internally:

- the outcome the user is authorized to receive now;
- the observable evidence that would make it complete;
- current hard constraints and authoritative sources;
- the systems, files, people, environments, and actions in scope;
- the accepted route and owner of each material judgment;
- the actual receiver or use boundary when it affects completion;
- decisive unknowns that execution may safely resolve; and
- the condition that would invalidate the contract and require the problem to be reopened.

A requested plan, review, report, prompt, design, or handoff is the deliverable. Do not silently turn it into implementation. A long-term goal or roadmap does not authorize every useful step toward it.

After compaction, interruption, handoff, or resume, reconstruct the current contract from the conversation, durable task state, authoritative sources, and repository or artifact state. Do not revive a stale plan merely because it remains available.

For long work, maintain one compact current explanation of the route, owners, public boundary, and invariant that must survive change, together with validation status and the next step. A factually current log is insufficient if it preserves two incompatible semantic routes.

Do not create a formal specification for a simple task. Ask only when a consequential ambiguity cannot be resolved from existing context, authoritative evidence, or a safe reversible probe.

## Resolve conflicting requirements before building

Use the most recent explicit user decisions, applicable safety or legal rules, and authoritative sources as binding constraints. Treat derived metrics, examples, samples, checklists, and prior plans as aids unless the user made them requirements.

Do not let a lower-level gate silently redefine the job. If current binding requirements materially conflict, expose and resolve the conflict before costly implementation, broad validation, or irreversible action. Apply stop, retry, exact-once, and fail-closed rules only to the actor, operation identity, state, time, and loss they govern; do not widen permission or prohibition by analogy.

When a correction invalidates an agent-added implementation, artifact, or routing choice while the accepted contract remains coherent, recover the last accepted positive baseline and replace or remove that choice. Do not preserve it by layering another prohibition, exception, adapter, or compatibility path.

## Load only the reference that owns the current problem

For architecture design, system design, non-trivial coding, refactoring, migration, or debugging that may change structure, ownership, control flow, state, interfaces, public contracts, or operational behavior, read [references/elegant-architecture.md](references/elegant-architecture.md) before planning or editing. A truly local edit may skip it, but still apply the removal question before accepting a new abstraction, state, branch, compatibility path, or coordination mechanism.

Read [references/evidence-calibrated-testing.md](references/evidence-calibrated-testing.md) before choosing, adding, or running evidence when that choice could materially affect acceptance. Explicit triggers include:

- deciding among focused, affected, broad, full, receiver, operational, production-like, or real-run validation;
- diagnosing a natural or escaped defect after producer-side checks passed;
- supporting a runtime, host, state, time, repeated-run, scale, or external-effect claim;
- preserving a failed exact instance while separately deciding whether a distinct fresh run is authorized;
- determining whether the fixture, oracle, environment, dependency, stale state, or implementation failed; and
- deciding whether another expensive run would change a decision.

Do not read the software architecture reference for ordinary research, writing, slides, spreadsheets, or communication unless the subject itself is software or system architecture. Detailed methods live in their references; do not restate or load them merely because they exist.

## Choose one accepted real route

Trace the shortest credible path from available inputs to the requested observable result. Reuse capabilities already provided by the repository, environment, platform, tools, operators, or agent. Prefer a reversible experiment over permanent machinery when it can cheaply resolve a material unknown.

“One route” means one accepted semantic owner and production path for the completed result. It does not prohibit parallel, reversible experiments or independent evidence gathering used to choose that route. Do not leave competing accepted meanings, control paths, outputs, or architectures in the final state.

Keep each durable fact and semantic judgment under one final owner. Other components or agents may provide evidence, enforce hard rules, reject invalid output, or request revision, but they must not silently reinterpret the same judgment. If several writers are unavoidable, define the merge rule and owner of the merged result.

Use a narrow representative end-to-end path early when it can reject the host, contract, interface, or route before support machinery grows. It must cross the real boundary that carries the meaning or risk, not a toy bypass.

## Treat a declared handoff as a current boundary

When the current work promises a handoff, public output, reusable artifact, or capability, its smallest stable contract is part of completion now—even if downstream implementation does not yet exist.

Define only the business meaning and access the current producer can reliably own. Do not expose provider fields, source tables, storage paths, model details, workflow state, coordinator internals, or future receiver logic as public meaning.

Every current public contract needs:

- a current producer;
- a lifecycle owner;
- enough documented meaning and access for the receiver to act;
- an invariant that survives ordinary provider, store, model, transport, or internal workflow changes.

A working historical reader or artifact does not make a capability current when nothing remains responsible for producing it.

## Make every addition earn its place

A proposed addition to the deliverable, implementation, workflow, state, abstraction, compatibility path, validation machinery, or external action must satisfy at least one condition:

1. The requested result or its acceptance evidence requires it.
2. A current hard rule, material safety boundary, privacy or data-integrity requirement, or irreversible effect requires it.
3. Observed evidence shows the accepted route cannot complete without it.
4. The user explicitly authorizes the expanded result or action.

For research, analysis, writing, and creative artifacts, useful inquiry or craft may also earn its place when it materially improves the requested artifact without changing its purpose, audience, format, or external-action boundary.

Do not promote an adjacent concern by calling it robustness, completeness, production readiness, governance, or future-proofing. Record a material adjacent finding briefly when useful; do not implement it.

## Execute and repair at the owning boundary

Use agent judgment for ambiguous, low-frequency, context-dependent, and reversible cases. Use deterministic protections for permissions, privacy, data integrity, mechanically checkable hard rules, idempotency around repeated effects, and irreversible external actions.

Do not encode every imagined exception. Promote an adaptation into permanent machinery only when a current contract, observed repetition, measured scale, required consistency, or material risk justifies its ongoing cost.

When a failure occurs, distinguish:

- the requested result;
- its implementation;
- the validation method, fixture, or oracle;
- the environment or host;
- an external dependency; and
- stale or contaminated state.

Repair narrowly when evidence isolates one owner and the objective, route, public boundary, and responsibility boundaries still hold. Fix the smallest evidenced failure family rather than only the observed specimen, but do not turn the repair into a general framework without need.

Stop local patching when repairs cross owners, old and new routes coexist, support structure grows while receiver action or user value remains flat, or the whole path can no longer be explained in one pass. Stop convergence and reopen the problem at the highest invalidated level when the objective, governing mechanism, owner, route, evidence model, public contract, or tradeoff is no longer coherent. Execution difficulty alone is not sufficient.

Before replacing or simplifying an existing path, inspect authoritative sources and representative outputs to identify required behavior and public contracts. Preserve consumer meaning and access, not accidental provider, storage, workflow, or topology details.

## Delegate bounded work; integrate once

Delegate when parallel execution, distinct evidence, specialized capability, or clean context separation improves the result. Give each subagent a bounded outcome, relevant sources, scope, acceptance evidence, and stop condition. Ask for findings or a candidate component, not authority to expand the mission.

When assurance matters, independence requires different evidence, an unrevealed oracle, a clean observation boundary, or a materially different failure model. A separate agent reading the same implementation-derived assumptions is not independent merely because it is a new conversation.

The integrating agent owns assembly, decisive source checks, producer-side whole-result completion, and stopping. It may resolve cross-component tradeoffs within the accepted contract, but it must not silently rewrite semantic judgments owned elsewhere. Component reports and agent agreement do not replace an integrated check of the real result.

Before steering another active task, refresh its authoritative current state. Intervene only on a concrete observed divergence and only when the message can change the target's next decision or action. If no decision-changing delta exists, remain silent.

## Validate the exact claim at its real boundary

Start with the most direct practical evidence of the completion claim, then add only the corroboration required by the claim's breadth, stakes, hard rules, semantic impact, and observed failures. Prefer actual artifacts, diffs, runtime behavior, authoritative source support, real user paths, target hosts, or representative use over declarations of progress.

Match the claim to the evidence:

- mechanism or unit evidence supports the mechanism exercised;
- representative integration evidence supports the path exercised;
- a bounded natural run supports what happened in that run;
- receiver evidence supports the receiver state and medium exercised;
- aggregate quality, later-run convergence, population-wide behavior, or long-term reliability requires evidence at that scale.

One successful sample is not population evidence. Passing tests do not prove an unexercised user path. Artifact existence, schema validity, internal metrics, or producer-side readback do not prove that a receiver can act.

A failed check establishes that its observed path failed. It does not automatically prove that the underlying result or implementation is wrong, authorize rollback, or prohibit a distinct fresh run. Preserve a failed instance when required; separately determine whether current authority permits another run.

Before an expensive rerun or broad suite, state internally what it distinguishes and how either outcome changes the next action. Do not repeat unchanged runs with unchanged preconditions when no decision would change. Preserve hard gates for permissions, privacy, integrity, shared users or data, external cost, contracts, and irreversible effects.

For scheduled, retried, batched, or long-running work, validate the first, second, and later run when the claim depends on convergence. For operational or data-scale work, validate representative volume, time, state, and resource bounds.

A time-bounded observation task may be complete when its agreed window ends. The elapsed window does not turn absent evidence into a broader quality claim or authorize continued monitoring.

Report exactly what was and was not demonstrated.

## Make the result usable by the receiver

The production path ends where the intended reader, user, system, or next agent can perform its next required action using only the public result, allowed context, and stable contract. The receiver should not need producer history, private state, rejected alternatives, provider internals, or an explanation of hidden machinery to repair the result.

Completeness depends on receiver state:

- a fresh receiver needs enough orientation and authority to act;
- an informed receiver usually needs the decision-changing delta and surviving invariant;
- an off-course receiver needs the observed divergence, correct target state, and reason that changes its next action.

Validate in the real medium and surrounding environment when sequence, rendering, visual grammar, host, state, timing, playback, attention, or operational context affects meaning.

If the underlying result is sound but selection, explanation, organization, or medium fit is wrong, reconstruct the output from the accepted positive state. Do not rerun accepted upstream work without evidence that it is wrong.

Receiver-side evidence production is part of completion when the claim depends on receiver use. A separate acceptance phase may recheck that result from a changed observation boundary; evidence production and acceptance need not be the same responsibility.

## Stop when complete

Stop when all are true:

- the requested observable outcome exists;
- applicable constraints and hard rules are satisfied;
- proportionate evidence supports the exact completion claim;
- the public contract and actual receiver or use boundary are complete when material;
- no required work remains inside authorized scope.

Before finishing, ask:

> What can be removed while preserving the requested result, hard rules, required behavior, public meaning, receiver usability, and supporting evidence?

Remove it, deliver the result, and stop.

Do not continue with unsolicited cleanup, new platforms, speculative safeguards, generalized frameworks, or unrelated improvements.

Read [references/casebook.md](references/casebook.md) only when learning or revising this method, not during blind evaluation. Read [references/eval-rubric.md](references/eval-rubric.md) when evaluating or changing this skill.
