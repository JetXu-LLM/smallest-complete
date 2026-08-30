# Elegant Architecture

Use this reference for software development and architecture work. It preserves
the complete guidance from the original `elegant-architecture` skill body; its
skill-registration frontmatter is intentionally omitted because this file is a
conditional reference owned by `smallest-complete`, not a separately registered
skill.

## Contents

- [Start With the Real Job](#start-with-the-real-job)
- [Recognize the Failure Pattern](#recognize-the-failure-pattern)
- [Keep One Clear Control Path](#keep-one-clear-control-path)
- [Build Independent Capability Modules](#build-independent-capability-modules)
- [Keep State Honest](#keep-state-honest)
- [Use Agents for the Adaptive Tail](#use-agents-for-the-adaptive-tail)
- [Make Every Addition Earn Its Place](#make-every-addition-earn-its-place)
- [Design or Simplify the System](#design-or-simplify-the-system)
- [Explain the Decision Clearly](#explain-the-decision-clearly)

Build the simplest system that reliably completes the job required now. Make
the design easy to explain in one pass: a clear path through the work, modules
that each own a real capability, and state only where durable facts or safe
recovery require it.

Do not equate simplicity with the fewest files or components. A large component
that hides many responsibilities is not simple. Preserve necessary capability,
safety, clarity, and operability while removing structure that does not earn
its ongoing cost.

Use the guidance below as a strong default, not a universal topology. Some
domains genuinely require distributed coordination or stateful components.
Require concrete evidence before accepting that extra complexity.

## Start With the Real Job

Before choosing components, establish:

- the smallest end-to-end job that must work now;
- what observable result means the job is complete;
- the business, safety, data, and operational rules that must never be broken;
- the failures and variation that have actually been observed;
- the capabilities already provided by the codebase, platform, operators, and
  agents;
- the important unknowns.

Build the value path and minimum hard boundary together. The first slice
protects permissions, privacy, data integrity, binding safety or legal rules,
and irreversible effects. Add retry, recovery, compatibility, governance,
audit, and other hardening only for a current contract, consumer, evidenced
loss, or observed failure. Value-first permits no disposable prototype, bypass,
or deferred integrity.

Treat a future specification as useful input, not proof that every possible
mode, exception, or extension must be implemented now. Keep an unknown explicit
or test it with a reversible experiment instead of turning it into permanent
structure.

Decide when the needed information exists. A later consumer's need for a firm
answer does not mean the earliest stage can produce it reliably. Keep unknown
meaning unknown until an owner has enough evidence to decide. A current promise
to publish an output, handoff, or reusable capability creates a present boundary
even when receiver code does not exist yet. Define only the stable meaning and access that the current owner can reliably supply; do not make an early stage
settle an unknowable judgment or build future receiver logic.

For a broad authorized implementation, first prove a narrow but representative
end-to-end path through the real control path and the interface through which
the result will actually be used. It must exercise the core capability and
meaningful integration boundaries, not a toy, injected state, or bypass. Expand
breadth along that proven path, and do not mistake the slice for completion of
the full contract.

## Recognize the Failure Pattern

Stop and reconsider when each uncertainty, exception, or future possibility
creates another status, mode, adapter, compatibility path, retry branch,
recovery path, or coordinating layer. These additions multiply rather than
merely add: modules begin to depend on global workflow state, several places
decide what happens next, and every change must preserve many combinations of
old and new behavior.

The result can be thousands or tens of thousands of lines devoted to
coordination while the real business capability remains small. The primary
path may still not work, fixes create more states, migrations keep both
architectures alive, and no change is ever finished because each one exposes
another cross-system rule.

Do not complete this design by adding another layer. Return to one real
end-to-end job, one control owner, explicit module contracts, and the smallest
state needed for business facts or safe recovery. Delete or defer everything
that cannot justify itself against that path.

## Keep One Clear Control Path

Prefer one place that decides what happens next for each end-to-end workflow.
That place may be an agent, a small program, or a workflow engine. It does not
mean that an entire product must have one global orchestrator; independent
workflows may each have their own coordinator.

Keep the coordinator small and easy to follow. Let it:

- receive the job and its explicit context;
- choose and call capability modules in a simple order;
- pass results between modules;
- record only the progress needed for observation or safe restart;
- stop, retry, or escalate.

Keep the ordinary path close to a straight line. Add a branch only when a real
requirement or observed failure needs one. Do not let an agent, scheduler,
workflow engine, service layer, and worker all make overlapping routing
decisions. Choose one decision owner and make the others triggers, tools, or
executors.

Do not put domain rules into the coordinator when a capability module should
own them. Do not copy module-owned data into workflow state. Do not make the
coordinator a second business system.

## Build Independent Capability Modules

Draw a module boundary around a stable business capability or responsibility,
not around every implementation step, data field, exception, or imagined
future variant.

Make each module:

- complete one meaningful piece of work through a small, explicit contract
  owned by that capability;
- own the business rules and data that belong to that capability;
- accept explicit inputs and return explicit results;
- callable, understandable, testable, and replaceable without knowledge of
  unrelated workflow state;
- robust against normal variation inside its own boundary;
- clear about failures it cannot handle;
- idempotent where retries could repeat an external effect.

Let testability come from these same real seams. Tests consume a capability contract; they do not co-own its meaning or justify exposing internal state.

For a consumed capability or declared handoff, treat the public boundary as an
information boundary and design backward from the receiver's job, visible
information, and next action. Consumers inform meaning, the domain capability
owns the contract, and user outcomes validate value. Expose stable, documented
meaning and access to act without prescribing downstream workflow. Keep sources,
providers, transports, storage, models, prompts,
workflows, staging artifacts, coordinator state, and raw payloads behind the
boundary. Provenance may cross it, but must not shape business fields.
Consumers should not query internals, need producer explanation, or repair meaning.

Every current public contract needs a current producer and lifecycle owner. Historical data or a working reader does not make a capability current when nothing
is responsible for producing it.

Give each durable fact and semantic judgment one final owner. Other modules may
provide evidence, validate hard rules, reject invalid output, or request
revision, but they must not silently reinterpret and rewrite the same judgment.
If several writers are unavoidable, define their merge rule and who owns the
merged result.

Keep a module externally free of hidden workflow state. It may read or write
the business data it owns; this does not mean it must be side-effect-free.
Avoid making it depend on a global mode, a previous call's hidden memory, or a
copy of the coordinator's state.

Choose the number of modules by the quality of their boundaries, not by a
target count. Do not create forty modules merely because there are forty data
sources, and do not force unrelated sources into four modules merely to reduce
the file count. Stable does not mean universal or immutable: semantically
different capabilities may have different contracts, and internal helpers do
not need public versioned schemas. Add compatible fields when that preserves meaning; when business meaning changes, version and migrate deliberately. Keep a
compatibility adapter only while a current consumer still requires it.

## Keep State Honest

Persist durable business facts. Add only the minimum execution record required
to resume safely, prevent duplicate effects, meet audit needs, or observe
progress.

Do not create state merely to make uncertainty feel controlled. Do not model
every imagined exception as a status or mode. If the workflow can safely be
restarted from explicit inputs and completed outputs, prefer that over a large
recovery state machine. If a workflow engine already owns execution state, do
not mirror that state elsewhere.

For every stored field or state transition, identify the present failure,
requirement, or hard rule that makes it necessary.

A local failure, wait, or unknown should affect only the capability that owns
it. Escalate it into a wider stop only when a shared safety rule, data-integrity
boundary, or irreversible effect is at risk. If two facts have different
consumers or blocking authority, store them separately instead of compressing
them into one global status.

## Use Agents for the Adaptive Tail

When an agent is available, let it handle ambiguous, context-dependent,
low-frequency, and reversible decisions. Examples include choosing among known
tools, interpreting an unusual source response, making a temporary adaptation,
or deciding whether to retry or escalate.

Keep deterministic code for permissions, data integrity, mechanically checkable
hard rules, idempotent protection against repeated effects, and irreversible
actions. Do not make code guess an open semantic judgment, repair its meaning, and
then publish the rewrite as if it were the original owner's decision. Give the
agent freedom inside the hard boundaries rather than encoding every possible
situation in advance.

Idempotency prevents duplicate effects; it does not require independent
intelligent runs to reach identical meaning. A repair added for weaker output
must become a no-op on already-valid stronger output.

If the agent decides what happens next, keep the code coordinator as a thin
runner and safety boundary. Do not build a second smart router that duplicates
the agent. When the same adaptation recurs, or when its risk demands
repeatability, move it into the module that owns the capability.

## Make Every Addition Earn Its Place

Before adding a module, service, queue, state, mode, abstraction, compatibility
layer, or coordination path, ask:

> What required behavior or hard rule would fail today if this were omitted?

Apply the same question to test-only branches, modes, state, interfaces, and alternate control paths. Mock or fixture convenience is not a product requirement; prefer a real seam or keep the accommodation inside the test harness.

For a safeguard, name the current loss, protected actor, and burden. Applicable
permission, privacy, integrity, legal, safety, and irreversible-effect protections
belong in the first slice; other hardening needs a current rule, consumer,
evidenced loss, or observed failure.

Accept reasons grounded in the domain, observed repetition, measured scale, or
material risk. Do not accept "production-grade," "complete," "clean,"
"enterprise," "robust," or "we may need it later" as sufficient reasons by themselves.

Consider what the addition removes or makes simpler, whether an existing
module, platform feature, operator, or agent can handle the need safely, and
how the addition could later be removed. Prefer the design with the lower
ongoing mental and operational burden, not merely the smaller initial diff.

## Design or Simplify the System

1. Trace the required job from sources and explicit inputs, through any public
   contract, to a next action the receiving actor can complete using only that
   boundary.
2. Identify one control owner for that workflow and one owner for each durable
   fact and business decision.
3. Propose the smallest end-to-end path using existing capabilities.
4. Look for deletion, consolidation, and reuse before adding structure.
5. Test each proposed addition with the question above.
6. Implement or recommend a narrow, representative end-to-end slice inside the
   minimum hard boundary that can produce real value evidence.
7. Validate actual behavior, then add complexity only when new evidence
   requires it.

For scheduled, retried, batched, or long-running work, validate the first,
second, and later run. Completed units should stay complete, unfinished work
should continue, local failures should remain isolated, and repeated operation
should converge instead of starve or recreate work.

For an existing system, choose the intended single path and owner first.
Delete, collapse, or bypass accidental layers before wrapping them in a new
abstraction. Use a temporary bridge only when direct migration is materially
unsafe or impractical, keep it local, and give it a concrete removal condition.
Do not preserve old and new architectures indefinitely in the name of
compatibility; retain only an adapter still required by a current consumer.

At natural milestones in a long implementation, trace the actual path again
from source or input through the public contract to the receiver. Give a clean
receiver only that result, contract, allowed context, and task; needing producer
context makes the path incomplete. Ask whether one credible internal change
would force receiver changes; if so, the boundary leaks. Check for bypasses, public readers
without producers, and competing outputs. Fold valid changes into one current
explanation and delete structure and tests that protect only the old mechanism.

Scale the analysis to the stakes and reversibility of the decision. Do not
create architecture ceremony for a simple local choice.

## Explain the Decision Clearly

Use ordinary language. Make clear:

- the job and hard rules;
- the control path and its decision owner;
- the capability modules, public contracts, and what each owns;
- the business and execution state that must persist;
- what the agent may decide and what code must guarantee;
- what was deliberately left out;
- what future evidence would justify adding more.

Use no mandatory report template. Keep the explanation proportional to the
decision. Before finalizing, try to remove one more concept, state, branch, or
coordination edge. Keep it removed unless a present requirement demonstrably
fails.
