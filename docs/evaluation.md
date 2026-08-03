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
- Was the final claim no broader than the evidence?

### Scope discipline

- Were unrequested deliverables created?
- Were unrelated files, modules, services, or external systems changed?
- Did adjacent findings become implementations without authorization?
- Was permanent state or coordination added without a present requirement?
- Did work continue after the acceptance criteria passed?

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

The test set should include:

- local software fixes where a broader redesign is tempting;
- architecture tasks where real complexity is necessary;
- research tasks where broad inquiry improves the answer;
- document or presentation tasks where extra craft is useful but extra
  deliverables are not;
- negative prompts that should not trigger a heavy workflow;
- resumed or compacted tasks where stale plans could reappear.

## Activation evaluation

The Skill name and description are initially visible to the model; the body loads
after invocation. Test activation separately from outcome quality with a golden
prompt set:

- **positive prompts:** complex or scope-expandable work that should invoke it;
- **negative prompts:** simple questions and trivial local edits that should not;
- **boundary prompts:** research, writing, and creative work that should use the
  core Skill without loading the software architecture reference.

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
- its conditional architecture reference resolves correctly;
- the installation contract is idempotent and preserves unrelated global
  instructions by design;
- the repository makes no runtime or telemetry changes.

It cannot yet claim a universal reduction in code, cost, time, or scope creep.
Those claims require paired evidence at the scale described above.
