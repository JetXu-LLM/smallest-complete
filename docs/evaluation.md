# Evaluation

Smallest Complete should be evaluated on whether the requested job is completed
within its authorized boundary—not on whether the output merely looks smaller.

This repository does not currently publish an aggregate efficacy percentage.
The initial release is based on repeated real-world failure analysis, iterative
prompt design, and structural validation of the Skill package. Those are reasons
to test it, not population-wide proof that it improves every model and task.

## What a fair evaluation must measure

At minimum, score both sides of the objective.

### Completion

- Did the requested observable result exist?
- Did it preserve required prior behavior?
- Did it satisfy the current hard constraints?
- Did validation exercise the relevant user path?
- Did representative real input reach the actual primary path early enough to
  test the route?
- If the result declared a handoff or public capability, could its intended
  receiver take the next action using only the public result, contract, and
  context that receiver is allowed to have?
- Did a fresh, informed, or already off-course receiver receive the different
  context its actual state required, without irrelevant producer history?
- For a reader-facing result, did acceptance exercise the actual channel,
  rendering, sequence, playback, or surrounding context that could change use?
- Did each current public contract still have a current producer?
- When the user rejected an agent-added choice but the contract stayed coherent,
  did the agent restore the accepted baseline instead of layering an exception?
- Did the integrating agent assemble and validate the whole result without
  rewriting a component-owned semantic judgment?
- When tests were material, did the failure objective come from a real loss,
  receiver action, operational exposure, semantic impact, or escaped incident?
- Was the oracle authoritative or independent enough to reject a plausible wrong
  result, and did critical cases also allow a correct alternative?
- Was the final claim no broader than the evidence?
- When an agreed observation window ended without a qualifying event, did the
  task stop while avoiding any broader quality claim?

### Scope discipline

- Were unrequested deliverables created?
- Were unrelated files, modules, services, or external systems changed?
- Did adjacent findings become implementations without authorization?
- Was permanent state or coordination added without a present requirement?
- Did work continue after the acceptance criteria passed?
- Did accumulated local fixes create a second route, owner, or meaning?

### Long-task coherence

- After delegation, resume, or compaction, did one current explanation survive?
- Did the agent reopen the problem when repairs crossed owners or the same real
  result kept failing?
- Did the integrating agent inspect the whole user-visible result instead of
  accepting component reports collectively?
- Did costly reruns distinguish causes or change a decision?
- Did validation scope follow semantic impact through owners, contracts, state,
  consumers, and real journeys rather than changed lines or test count?
- For scheduled or retried work, did second and later runs skip terminal work,
  continue unfinished work, isolate local waits, and converge?
- When a provider, store, or internal workflow changed, did the declared public
  contract remain usable without receiver changes?
- Did producer-side evidence improve while receiver action or user value stayed
  flat? If so, did the agent reopen the route instead of adding support layers?

### Human cost

- How many correction turns were needed?
- How much time and token usage did the task consume?
- How difficult is the resulting diff or artifact to understand and maintain?
- Did the user have to repeatedly restate the original boundary?

Lines of code can be a secondary measure for comparable software tasks. They are
not a primary success criterion: less code can be incomplete, and more code can
be required.

## Paired evaluation design

For a meaningful comparison:

1. Use the same model, harness version, reasoning effort, repository state,
   tools, permissions, and user request.
2. Run one condition without Smallest Complete and one with it.
3. Isolate runs so neither sees the other's artifacts or conclusions.
4. Predefine the acceptance criteria and hard scope boundary before either run.
5. Score outputs blind when practical.
6. Repeat tasks; one dramatic example is not aggregate evidence.

The bundled [`eval-rubric.md`](../skills/smallest-complete/references/eval-rubric.md)
is the standalone phase-specific scoring contract. The bundled
[`casebook.md`](../skills/smallest-complete/references/casebook.md) is for learning
and revision; do not expose it to blind subjects.

For a declared handoff, include a clean-receiver probe. Give the receiver only
the public result, contract, its real task, and information available at that
boundary. Do not expose producer reasoning or internal state. Score whether the
receiver can act, what clarification or repair it needs, and whether the
producer transferred interpretation or recovery work across the boundary.

Vary the same handoff across a fresh receiver, an informed receiver, and one
already acting on a wrong route. Also move a reader-facing result into its real
medium or established surrounding artifact. Check that necessary orientation is
preserved, irrelevant rejected concepts are not introduced, active divergence
is corrected directly, and producer-green evidence does not override actual use.

For a material testing claim, check both directions. A plausible bad control
must fail for the intended reason, including proof that its fixture established
the claimed precondition. A semantically correct alternative should still pass.
At a stable release boundary, full regression may corroborate but must not
replace the shortest direct receiver or operational acceptance on the same
final candidate when intervening changes could affect that claim.

The test set should include:

- local software fixes where a broader redesign is tempting;
- architecture tasks where real complexity is necessary;
- research tasks where broad inquiry improves the answer;
- document or presentation tasks where extra craft is useful but extra
  deliverables are not;
- negative prompts that should not trigger a heavy workflow;
- resumed or compacted tasks where a good plan can drift through local repairs;
- handoff tasks where producer artifacts can be mistaken for public contracts;
- provider or storage changes that should remain invisible to current consumers;
- active-task messages where the observer must refresh current state and either
  stay silent or send one decision-changing delta;
- value-path tasks where permissions, privacy, integrity, and irreversible
  effects must hold from the first slice, while speculative recovery,
  compatibility, or governance should not precede useful capability;
- scheduled or retried tasks that pass once but starve or repeat work later.
- generated suites whose fixtures, mocks, implementation, oracle, and reviewer
  share one wrong model;
- escaped natural inputs that should update a failure family rather than only
  add a case-specific regression;
- paired small and shared changes that require different focused/full scopes.
- operational completion tasks where a bounded fresh real run is the decisive
  evidence but a broad indirect suite is easier to execute.
- local corrections where the accepted contract remains sound but an agent-added
  path must be removed rather than preserved through another exception;
- bounded observation tasks that should end at the agreed window without turning
  missing evidence into a reliability or population claim.

Include negative controls in which a hard boundary must precede value delivery,
an observed repeated side effect requires idempotency, a current consumer needs
a compatibility adapter, a helper has no public consumer, or receiver goals
conflict, a local fixture already proves its precondition, or a stable release
candidate genuinely requires full regression, or a real run would expose shared
users, data, money, privacy, contractual limits, or irreversible effects. These
distinguish receiver and testing discipline from schema ceremony, speculative
empathy, ritual distrust, and indiscriminate avoidance of broad validation.

## Activation evaluation

The Skill name and description are initially visible to the model; the body loads
after invocation. Test activation separately from outcome quality with a golden
prompt set:

- **positive prompts:** complex or scope-expandable work that should invoke it;
- **negative prompts:** simple questions and trivial local edits that should not;
- **boundary prompts:** research, writing, and creative work that should use the
  core Skill without loading either software reference.

Also test conditional-reference routing: architecture only, testing only, both,
and neither. Material operational or real-run evidence must route to the testing
reference even when it is not called a test; a local check with a settled owner,
contract, and impact must not load it.

Track both recall and precision. A Skill that triggers on everything becomes
noise; a Skill that rarely triggers cannot affect behavior.

## Claim ladder

Match every public claim to the evidence collected:

| Evidence | Claim it can support |
| --- | --- |
| Static package validation | Files and references are well formed |
| One controlled task | What happened in that task |
| Repeated paired tasks in one environment | A bounded effect in that environment |
| Diverse models, harnesses, repositories, and task classes | A broader generalization, with stated limits |
| Longitudinal opt-in usage data | Retention or durable behavior change |

Do not turn stars, downloads, anecdotes, or a small diff into proof of long-term
effectiveness.

## Reporting a behavior result

Open a [behavior report](https://github.com/JetXu-LLM/smallest-complete/issues/new?template=behavior-report.yml)
with:

- model, harness, version, and reasoning effort;
- the exact task request and relevant instruction context;
- expected scope and observable acceptance criteria;
- what the agent delivered or changed;
- evidence of completion or failure;
- any unauthorized additions or under-delivery;
- a sanitized transcript or diff when it is safe to share.

Remove secrets, personal data, private source code, customer information, and
credentials before publishing anything.

## Current release status

The release can claim that:

- the published Skill matches the locally developed source;
- both conditional runtime references and both non-runtime evaluation references
  resolve correctly;
- the installation contract is idempotent and preserves unrelated global
  instructions by design;
- the repository makes no runtime or telemetry changes.

It cannot yet claim a universal reduction in code, cost, time, or scope creep.
Those claims require paired evidence at the scale described above.
