# Evidence-Calibrated Testing

Use this reference when tests or evaluations materially affect whether a complex result can be accepted. It does not demand more testing. It helps choose
which evidence is needed, where to observe it, when to run it, and what the result can honestly prove.

Here, a test may be a scripted check, a focused probe, a clean-receiver trial, natural use, a canary, or another controlled observation. No one test type is
the default for every problem.

Use these distinctions internally. Unless the user asks for a test strategy, report only the decision-changing objective, evidence, and bounded claim; do not narrate the lifecycle or method catalog.

## Derive the Assurance Question

Do not begin with the changed function or a request to add edge cases. First
identify the claim whose failure would matter.

Useful sources are a principal's unacceptable loss or hard boundary; the next decision or action a real receiver must complete; actual operational inputs,
environments, states, and timing; the semantic reach of the current change through owners and consumers; and failures that escaped earlier validation.

An important failure is a meaningful deviation that harms one of those jobs,
decisions, boundaries, or recovery paths. Code structure alone does not decide
importance.

State the test objective in ordinary language before choosing a framework. A
consequential objective should make clear:

- the actor, job, or loss being protected;
- the triggering context and state;
- the real boundary the behavior must cross;
- the source that is entitled to define the expected result;
- the observable outcome;
- one plausible wrong behavior; and
- one different but acceptable implementation or result.

The oracle may come from a binding requirement, a current consumer contract, a
domain owner, an authoritative implementation, a frozen incident, a mathematical
property, or independently collected natural evidence. If correctness depends
on private preference or an open semantic judgment that no current source can
settle, ask the owner or narrow the claim. Do not let the implementation invent
its own expected answer and then certify itself.

Separate two jobs:

- **Discovery:** expose a wrong host, receiver, construct, contract, or problem frame before a large regression suite exists.
- **Regression:** protect behavior after its meaning and owner are stable.

An early real probe is valuable when it can reject the route. A regression is valuable when it can reject a future change to a known behavior. Neither should
pretend to do the other's job.

## Build an Evidence Portfolio

For a material use claim, combine only the responsibilities it actually needs:

1. **Representative route-breaker:** exercise a small real path early enough to show that the host, contract, construct, or receiver route can work—or reject it
   before support machinery grows.
2. **Owner-local regression:** after the owning cause is known, protect the invariant with a fast, attributable check.
3. **Receiver or operational acceptance:** at a natural milestone, cross the boundary where the user, module, agent, environment, state, or time-dependent process must act.

Choose a method from the unknown, not from habit:

| Main unknown | Useful evidence |
| --- | --- |
| Deterministic rule | examples, properties, and selective mutation |
| Input combinations | equivalence classes, boundaries, pairwise or t-way cases |
| State or operation sequence | model-based or stateful property testing |
| No exact answer but a stable relation | metamorphic testing |
| Authoritative compatible implementation | differential testing |
| Module or service boundary | consumer contract plus actual consumer/provider check |
| External dialect or host | real endpoint, clean install, target-host smoke, or canary |
| Human use or understanding | representative task observation without producer coaching |
| Agent workflow | knowledge-bounded environment, allowed tools, and final-state outcome |
| Repeated or distributed operation | later-run checks, fault injection, model checking, or soak |
| Unsettled frame | prototype, exploratory use, or natural boundary probe |

For a clean-receiver check, provide only the public result, allowed context, and
the receiver's real task. Producer reasoning, internal tables, private state,
and repair instructions are not part of the boundary unless the contract says
they are.

Do not optimize a fixed pyramid ratio. Several tests that share one fixture,
mock, generator, oracle, and observation boundary may represent one failure
model. One real-host or receiver probe may contribute genuinely different
evidence.

## Write a Discriminating Case

A good case is the smallest causal witness of an important failure, not a
transcript of the production implementation.

- Trigger it through the interface the real actor uses.
- Build only the state needed to expose the risk.
- Verify that the fixture actually created the claimed precondition.
- Let the wrong behavior propagate to an observable outcome.
- Assert the receiver result, hard loss, or required side effect—not unrelated
  internal calls.
- Keep provenance to the requirement, consumer need, incident, authority,
  operational sample, or loss scenario that justified it.

Calibrate critical tests in both directions:

- **Plausible bad control:** remove or bypass the key behavior, return an empty but legal result, use stale state, or introduce another credible fault. The test
  should fail for the intended reason.
- **Correct alternative:** change an internal algorithm, provider, store, ordering, or equivalent representation while preserving business meaning. The test
  should still pass.

Red-before-green establishes that a check is connected to a change. It does not by itself establish that the fixture is real, the oracle is right, or the
contract serves the user. When setup is the suspected blind spot, state and verify the failed precondition before interpreting the result; a later bad control
does not validate the original fixture.

Use mocks to isolate an owned boundary, not to erase the dependency that carries the risk. Avoid test-only production methods, global modes, alternate control
paths, or public fields created only to make a fixture convenient. Testability should usually follow from a clear real contract; special accommodation belongs
inside the test harness unless the product itself needs it.

## Select Execution by Semantic Impact

Changed line count is not the testing boundary. Trace the behavior instead:

`changed behavior -> owner -> public contract or shared state -> direct consumers -> user or agent journeys -> losses and hard boundaries`

During implementation, continue through this order only while the change's semantic impact reaches the next layer:

1. Run the direct reproducer or new-behavior check.
2. Run affected owner tests.
3. Run affected consumer tests when a public boundary changed or may leak.
4. Run the shortest real route when host, state, timing, or side effects matter.
5. Run full regression once at a stable merge, release, or production boundary, or earlier when the impact cannot be bounded safely.

Broaden validation when the change touches shared core behavior, protocol or
schema, serialization, authentication, permissions, privacy, public API or ABI,
state machines, storage or migration, cursor or time semantics, dependencies,
runtime or build configuration, shared fixtures, test harnesses, oracles, or
dynamic behavior that defeats reliable impact analysis. Also broaden when
several local changes have accumulated and the current blast radius can no
longer be explained.

Do not repeat an unchanged full run when the tree, environment, inputs, and
preconditions are the same and no decision would change. A focused iteration
does not permanently waive the full stable-boundary gate. A full suite is valid
evidence for the paths it covers; it is not a substitute for a missing receiver,
real host, natural input, or later-run observation.

At a stable boundary, run the shortest direct completion, receiver, or operational acceptance on the same final candidate when changes since its last
run could affect that claim. Full regression corroborates that evidence; it does
not replace it.

Test-impact tools may help select existing tests after their dependency model is
calibrated. Treat their omissions as a measurable risk, especially with dynamic
loading, reflection, data and configuration dependencies, or stale coverage
maps. They cannot choose the product oracle or invent a missing real-boundary
test.

## Interpret the Result and Stop

Before acting on a failure, distinguish:

- the requested result itself;
- its implementation;
- the test, fixture, or oracle;
- the environment or host;
- an external dependency; and
- stale or contaminated state.

A failed check establishes that its observed path failed. It does not
automatically authorize rollback, redesign, or another large test cycle. A
passing check supports only the actor, input, environment, state, time, and
boundary it actually exercised.

Case count, pass rate, coverage, mutation score, schema validity, and artifact
existence are useful local signals in the right setting. None automatically
proves user value, receiver action, production compatibility, long-run
convergence, or population-wide quality.

Before a costly or broad run, know what it distinguishes and how either result
changes the next decision. Cheap CPU does not make a low-information test a
strong oracle.

Stop testing the current change when:

- the direct completion claim and hard boundaries have proportionate evidence;
- the affected owner and consumer paths have been addressed;
- the important residual uncertainty is either resolved or reported honestly;
- the required stable-boundary gate has passed or is explicitly pending; and
- another run with unchanged preconditions would not change a decision.

Do not claim more. A bounded natural run proves what happened in that run. A
later-run claim needs later-run evidence. Long-term reliability or aggregate
quality needs evidence at that scale.

## Learn From Escaped Failures

Treat a natural escape as data about the validation model, not only as another
specimen to encode.

Classify the missing layer:

- **objective:** the important actor, job, or loss was absent;
- **oracle:** the expected result came from the implementation or a weak proxy;
- **path:** the test bypassed the mechanism that failed;
- **input:** fixtures did not represent natural or high-loss cases;
- **environment:** the real provider, host, runtime, or dependency differed;
- **state or time:** only the first or clean run was exercised;
- **selection:** the right existing test was not run for the semantic impact;
- **claim:** the evidence was sound but the completion statement was too broad.

Repair the owning invariant and add the narrowest regression that protects the
failure family. Also restore the receiver, operational, or exploratory evidence
that exposed the gap. Do not respond to every escape with another parallel
harness, global status, compatibility layer, or pile of near-duplicate cases.

Periodically challenge critical tests with credible bad controls, known escaped
incidents, or selective mutations. Remove tests that protect only a superseded
mechanism, repeat the same blind spot, or have no current consumer or hard
boundary. Preserve outcome, contract, and hard-boundary tests when their claims
remain current.

A separate test agent is independent only when it has different evidence, an
unrevealed oracle, a clean receiver boundary, or a genuinely different failure
model. A new chat using the same implementation-derived assumptions does not
create semantic independence.

## Preserve Project Truth Only When It Pays

Reuse current requirements, consumer contracts, incident records, runbooks,
monitoring, and test configuration before creating another document.

For a long-lived project with several owners or receivers, important state or
time behavior, or repeated loss of validation context, keep a compact validation
map in an existing project record. Preserve only what would be expensive to
rediscover:

- the critical claim and protected actor or loss;
- the oracle and its authority;
- the owner, public boundary, and direct consumers;
- the earliest real route-breaker and operational acceptance;
- the normal focused and stable-boundary full-run points; and
- known blind spots or evidence still missing.

Do not require a universal filename, schema, state machine, coverage matrix, or
test budget. Do not create or update project documentation without authority.
For a local check with a settled owner, contract, and impact, use the relevant
focused test, report what it proves, and stop.
