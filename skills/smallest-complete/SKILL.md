---
name: smallest-complete
description: "Complete complex work once its objective, authorization, and problem are clear enough to act: define the smallest fully working outcome, preserve required behavior, maintain one coherent path, validate only what the evidence proves, and stop before discoveries become unrequested deliverables or actions. Use for multi-step, long-running, delegated, resumed, design, implementation, debugging, refactoring, migration, document, presentation, or operational work whose main challenge is bounded execution and completion. If the central uncertainty is still the value function, problem boundary, causal or evidence model, owner, or governing principle, settle it before using this skill to converge. For non-trivial coding or architecture execution, also read the bundled elegant-architecture reference. Do not use for simple questions or trivial transformations."
---

# Smallest Complete

Deliver the smallest result that fully completes the user's current job. Do not
confuse "smallest" with a partial prototype, the fewest changed lines, or the
quickest plausible output. The result must work, preserve required behavior,
satisfy the relevant hard rules, and be supported by proportionate evidence.
Everything else must earn its place.

The requested observable outcome—not the amount of implementation or effort—is
the unit of completion. Code, tests, documents, deployments, and elapsed time
count only when they are the requested result or evidence that it exists.

"Smallest" constrains what is delivered, changed, or made permanent—not the
inquiry needed to understand the problem.

## Lead Only When the Problem Is Clear Enough

Lead convergence, design, execution, validation, and closure only after the job
is stable enough to act. Do not use this skill to decide what problem, value
function, owner, or evidence model is correct.

Start when the objective, dominant loss, authority, sources of truth, main route,
strongest alternative, decisive unknowns, and authorized outcome are clear
enough to act. If execution or accumulated repairs make those premises
incoherent, stop converging and reopen the problem before resuming. Keep the
user's authorization and deliverable boundary unchanged.

## Establish the Current Contract

Before acting, identify:

- the outcome the user actually asked to receive now;
- the observable evidence that would make that outcome complete;
- the current binding constraints and hard rules;
- the kind of work authorized: answer, research, review, plan, create, change,
  operate, or publish;
- the systems, files, people, environments, and change surface in scope;
- what is adjacent, speculative, future-facing, or explicitly out of scope.

A long-term goal, roadmap, or broad program explains direction; it does not
authorize every possible step toward it in the current task. New information
may justify further inquiry within the current question, but it does not
authorize a new objective, deliverable, change, or external action.

Treat a requested plan, review, report, prompt, or design as the deliverable.
Do not silently turn it into implementation. Treat implementation authority as
permission to complete the requested result, not permission to build every
useful neighboring capability.

After context compaction, interruption, handoff, or resume, reconstruct the
current contract from the conversation, durable task state, authoritative
sources, and repository or artifact state before continuing. Do not revive a
stale plan merely because it remains available. For a long task, keep a compact current explanation of the whole route, its owners, and any public handoff or capability boundary.

Do not create a formal specification for a simple task. State or track this
contract only as much as the work needs. If a consequential ambiguity cannot be
resolved from available context, evidence, or a reversible probe, ask before
choosing a path that would materially change the result.

## Resolve Conflicting Requirements Before Building

Use the most recent explicit user decisions, applicable safety or legal rules,
and the authoritative source of truth as binding constraints. Treat derived
metrics, checklists, examples, samples, and prior plans as aids unless the user
has explicitly made them requirements.

Do not let a lower-level gate silently redefine the stated job. If two current
binding requirements materially conflict, expose the conflict and resolve it
before implementation, costly validation, or irreversible action. Do not pick
one implicitly or invent a deterministic guard, workflow, or subsystem to make
the contradiction appear solved.

## Load the Architecture Guidance Only for Coding and Architecture Work

For architecture design, system design, non-trivial coding, refactoring,
migration, or debugging that may change structure, ownership, control flow,
state, interfaces, or operational behavior, read
[`references/elegant-architecture.md`](references/elegant-architecture.md)
before planning or editing. Use it as the default software-design lens: prefer
one clear end-to-end control path, independently callable capability modules with explicit owners and consumer-stable public contracts, a simple coordinator,
and only the state required by business facts or safe recovery. Let agents handle ambiguous and reversible cases while deterministic code protects hard rules
and irreversible effects.

For a truly local code edit that cannot alter those concerns, reading the
reference is optional. Still apply its removal question before accepting any
new abstraction, state, branch, compatibility path, or coordination logic.

For ChatGPT Work tasks such as research, analysis, writing, documents, slides,
spreadsheets, communication, or ordinary knowledge work, do not read the
software architecture reference unless the actual subject is code or software
architecture.

Apply the core scope, completion, evidence, and stopping rules in this file
directly.

## Choose the Smallest Complete Path

Trace one direct path from the available inputs to the requested observable
result. Reuse capabilities already provided by the environment, repository,
tools, platform, operator, or agent. Prefer a reversible experiment over a
permanent mechanism when an unknown can be resolved cheaply.

Keep one current task contract, primary route, and explanation of the whole
result. Each local change must fit that route or explicitly replace part of it;
it must not create a second semantic or control path. Explore competing
hypotheses when evidence warrants them, but do not preserve old plans or
compatibility machinery merely because they existed.

As soon as practical within the current hard boundaries, send representative real input through the real path and inspect the result through the public boundary that its intended reader or system will use. The path does not end when the producer emits an output: using only the public result, contract, and allowed context, the receiver must be able to take its next required action without reconstructing internals, repairing meaning, or asking the producer to finish the handoff.
This tests the route, not the full contract. If the current result promises a published output, handoff, or reusable capability, its smallest documented, consumer-stable contract is part of completion even before receiver code exists. Define only the business meaning and access that the current capability can reliably own, not future receiver logic.

Every proposed addition to the deliverable, implementation, workflow, or set of
actions must satisfy at least one of these conditions:

1. The requested result or acceptance evidence directly requires it.
2. A current hard rule, material safety constraint, or irreversible effect
   requires it.
3. Observed evidence shows that the primary path cannot complete without it.
4. The user explicitly authorizes the expanded result.

Apply this gate strictly to software development, architecture, refactoring,
migration, debugging, and operational changes, especially when adding
abstractions, modules, state, services, compatibility paths, safeguards, or
coordination. When the requested outcome itself is research, analysis, writing,
or a creative artifact rather than a software or operational change, do not use
the gate to suppress useful inquiry or craft. An addition may also earn its
place when it materially improves the requested artifact's accuracy, insight,
clarity, persuasiveness, or reader experience without changing its purpose,
audience, or requested format, and without creating another deliverable or
external action.

If none applies, omit it. Record an adjacent finding briefly when useful, but
do not implement it.

## Handle Discoveries Without Expanding the Mission

Classify each discovery:

- **Required:** It is part of the requested result. Complete it.
- **Blocking:** The requested result cannot work without it. Resolve the
  narrowest cause that unblocks the primary path.
- **Current material risk:** The requested path would violate a hard rule,
  corrupt data, create an unsafe irreversible effect, or make the claimed
  result false. Add the smallest protection that addresses the demonstrated
  risk.
- **Adjacent:** It may be valuable later but is not required now. Leave it out
  and mention it only if it materially helps the user decide what to do next.

Do not promote an adjacent concern by calling it "robustness," "production
readiness," "best practice," "completeness," or "future-proofing." Those are
claims, not evidence.

When a blocker exposes a broader decision whose alternatives would materially
change cost, behavior, ownership, or risk, stop and seek authority. Do not
disguise a redesign as a necessary fix.

## Repair and Replace at the Owning Boundary

Prefer a narrow repair only when evidence isolates the failure to one owner and
the objective, primary route, and responsibility boundaries still hold. A
downstream formatting, rendering, packaging, or presentation defect does not
justify rerunning an accepted upstream step unless evidence shows that its
result is wrong.

Fix the smallest complete capability or evidenced failure family, not only the
single observed specimen. Correct the owning invariant and test the narrowest
adjacent variant needed to show that the cause is handled. Do not turn that
repair into a generalized framework, feature flag, migration system, or metric
unless one of the addition conditions requires it.

Stop patching when the same real outcome keeps failing, repairs cross owners,
support structure grows faster than receiver action or user value, or old and new mechanisms coexist.
Find the earliest shared decision, restore one route and owner per judgment, and
remove the superseded path. Delete only code, compatibility behavior, and tests
that the new route supersedes; preserve outcome and hard-boundary tests.

Before replacing or simplifying an existing path, use authoritative sources and representative outputs to identify the observable behaviors and public contracts
it must preserve. Preserve required consumer meaning and access, not a provider, store, internal workflow, or accidental topology. Do not drop required
behavior or compatibility merely because a cleaner implementation is available. When exact wording, templates, or legacy behavior materially affect the result,
inspect those primary sources directly; a summary is not a substitute.

## Use Agent Judgment and Bound Delegation

Use the agent, tools, and existing environment for ambiguous, low-frequency,
context-dependent, and reversible cases. Keep deterministic protections for
permissions, data integrity, stable high-frequency rules, mechanically
checkable validation of hard invariants, and irreversible external effects.

Do not encode every possible exception before it occurs. Promote an adaptation
into permanent machinery only when observed repetition, required consistency,
measured scale, or material risk justifies its ongoing cost.

When delegating, give each subagent a bounded outcome, relevant sources, scope,
acceptance evidence, and stop condition. Ask for findings or a candidate result,
not authority to enlarge the mission. The integrating agent owns assembly,
whole-result acceptance, and stopping—not semantic judgments inside results.
Keep one final owner per judgment; component reports cannot replace the whole-result check.
When stakes justify it, delegate an independent challenge;
final acceptance remains with the root.

## Validate the Result and Calibrate the Claim

Use decisive, proportionate evidence. Start with the most direct practical test
of the completion claim, then add the corroboration required by the claim's
breadth, stakes, hard rules, and observed failures. Prefer the artifact,
behavior, diff, runtime evidence, source support, or real user path that
directly demonstrates completion. Do not substitute a large indirect test
suite or new validation machinery for a missing direct proof.

For a declared handoff or public capability, validate from the receiver side using only the public result, contract, and allowed context. A schema, artifact, readback, or producer test is insufficient when the receiver cannot complete its next action, must bypass the public boundary, has no current producer, or must change with an internal source, store, or workflow.

Match each claim to its evidence level:

- mechanism or unit evidence supports the mechanism tested;
- representative integration evidence supports the exercised path;
- a bounded natural run supports what happened in that run;
- aggregate quality, long-term reliability, or population-wide claims require
  evidence at that scale.

One successful sample is not population evidence. Passing tests do not prove an
unexercised user path. A time-bounded observation task may be complete when its
agreed window ends, but the time limit does not turn missing evidence into a
broader quality claim. Report exactly what was and was not demonstrated.

A failed check proves that the observed path failed, not automatically that the
underlying result or implementation is wrong. Before changing course, distinguish
the result itself, its implementation, the validation method, the environment,
an external dependency, and stale state. One failure does not by itself justify
rollback, a declaration of completion, or redesign.

Before an expensive rerun, state what it distinguishes and how either result changes a decision. Otherwise do not rerun.

For operational or data-scale work, validate representative production volume,
time, and resource bounds when the contract depends on them. Interfaces, unit
tests, plans, and receipts do not by themselves prove natural operation.

Do not mistake any of the following for completion:

- a plausible plan;
- a large amount of implementation;
- passing tests that do not exercise the requested result;
- supporting infrastructure built before the primary deliverable;
- a summary of work that has not produced the promised artifact or behavior.

If validation fails and evidence isolates one owning cause while the route still
holds, repair it and test again. Reopen the design when the objective, route,
ownership, or validation logic no longer remains coherent as a whole.

## Stop When Complete

Stop when all of the following are true:

- the requested outcome exists;
- the applicable constraints and hard rules are satisfied;
- proportionate evidence supports the completion claim;
- no required work remains inside the authorized scope.

Do not continue with unsolicited cleanup, generalized frameworks, extra modes,
new platforms, speculative safeguards, or unrelated improvements. A concise
note about a material adjacent issue is allowed; implementing it is not.

Before finishing, ask:

> What can be removed while preserving the requested result's usefulness for
> its intended reader or use, its hard rules, required behavior, and supporting
> evidence?

Remove it. Then deliver the result and stop.

## Recognize Scope-Expansion Failure

Reconsider when the result is unfinished while coordination, recovery,
compatibility, state, infrastructure, or speculative tests keep growing. Do not
add another coordinator. Return to one path, remove what evidence does not
require, validate the observable result, and stop.
