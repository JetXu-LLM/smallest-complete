# Why Smallest Complete exists

Smallest Complete began with a strange repeated result: several unrelated
projects, with different business goals and different code, converged on the
same failure shape.

The agent was rarely incapable. It was often the opposite. It could see many
risks, imagine many improvements, write large amounts of code, create tests, and
keep going through long sessions. But the primary job became harder to find
inside the machinery built around it.

This document separates the observed pattern from the explanation proposed by
the project. It is not a scientific attribution of one behavior to one model.

## The visible failure pattern

A bounded task starts normally. Then:

1. The agent discovers an adjacent concern.
2. “This may matter” becomes “this belongs in the current task.”
3. The concern becomes permanent code, state, process, or another deliverable.
4. The new structure creates more interactions and more failure cases.
5. Those failure cases justify more coordination, validation, and recovery.
6. The requested result is delayed, obscured, or never proven end to end.

Each individual addition can sound responsible. The damage is multiplicative:
several places start deciding what happens next, modules depend on global
workflow state, old and new paths coexist, and every later fix must preserve more
accidental behavior.

At the extreme, a small business capability is surrounded by thousands or tens
of thousands of lines of synchronization, compatibility, recovery, and
governance code—and the system is still difficult to finish or change.

## The proposed mechanism

The project describes the mechanism as a mismatch among **capability**,
**authorization**, and **stopping**.

### Capability outruns the current contract

Modern agents can investigate, implement, test, delegate, and operate tools for
long periods. Greater capability increases the number of useful adjacent things
the agent can notice. It does not automatically tell the agent which of those
things the user authorized it to build now.

### Helpfulness becomes action bias

Agent harnesses are designed to make progress. When the difference between
“answer,” “plan,” “review,” “change,” and “publish” is not held explicitly, a
useful discovery can become an implementation without a conscious scope
decision.

### Long work accumulates stale constraints

Compaction, interruptions, handoffs, evolving requirements, and repeated repair
passes can preserve old plans and obsolete constraints. The agent may try to
satisfy several historical versions simultaneously by adding compatibility
paths or validation layers rather than reconstructing the current contract.

### Completion becomes open-ended

If success is not tied to an observable requested result, the agent can keep
searching for risks after the job is already complete—or declare success after
building supporting infrastructure without exercising the user path.

## Why this is not simply “a GPT-5.6 problem”

Recent Codex discussions make the pattern unusually visible. Users describe
[simple tasks turning into governance, architecture work, and hypothetical
testing](https://www.reddit.com/r/codex/comments/1uuo6x4/how_to_keep_gpt56_sol_high_from_overengineering/),
[high reasoning effort producing recurring architecture tweaks with little
progress](https://www.reddit.com/r/codex/comments/1utlu6p/is_it_just_me_or_does_56_overcomplicate_tasks/),
and [superseded requirements surviving as compatibility and validation
burden](https://community.openai.com/t/codex-gpt-5-6-sol-retains-superseded-requirements-as-negative-constraints-causing-project-bloat/1388093).

Those reports are useful corroboration, not causal proof. A model can supply the
action tendency, a harness can supply authority and persistence, a prompt can
leave the contract vague, and a repository can contain conflicting historical
rules. The behavior is produced by the whole operating system around the task.

That is also why changing models, lowering reasoning effort, tightening a prompt,
or disabling delegation can help in some cases without being a general cure.

## Why “be elegant” was not enough

“Elegant,” “robust,” “production-ready,” and “best practice” sound precise to a
human who already shares the intended tradeoff. To an agent, they can justify
more architecture just as easily as less.

The useful question is more concrete:

> What required behavior or hard rule would fail today if this addition were
> omitted?

If there is no present answer, the addition is not part of the current job.

## Why minimalism alone was not enough

An instruction to write fewer lines can create the opposite failure: skip
necessary investigation, validation, error handling, or required behavior. A
five-line answer is not better when it solves only half the task.

Smallest Complete therefore uses a two-sided objective:

- **Smallest** limits what becomes permanent or leaves the authorized boundary.
- **Complete** requires the actual outcome, preserved behavior, hard constraints,
  and evidence.

The optimum is not the least work. It is the least *unnecessary* work among the
results that genuinely complete the job.

## Why inquiry and action are treated differently

Research, analysis, writing, and creative work often improve through breadth.
Reading one more source or considering a competing explanation does not create a
new production service or mutate an external system.

Software and operational additions carry durable cost. They create ownership,
state, interfaces, maintenance, and possible irreversible effects. The Skill
therefore keeps inquiry broad enough to support the requested result while
applying a stricter addition gate to changes, deliverables, and external actions.

## The intended reversal

When expansion has already begun, the answer is not another coordination layer.
Return to:

1. one current outcome;
2. explicit non-goals and authority;
3. one primary path to observable completion;
4. the smallest state and structure that path truly requires;
5. evidence that the result works;
6. a hard stop.

That is the whole intervention Smallest Complete tries to keep available in the
agent's context.
