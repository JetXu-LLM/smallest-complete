# Contributing

Thanks for helping Smallest Complete become more effective without becoming the
kind of system it is meant to prevent.

## Start with an observed behavior

The strongest contribution begins with a concrete task where the current Skill:

- failed to activate when it should have;
- activated on a trivial task and added friction;
- suppressed useful inquiry or craft;
- allowed unauthorized scope expansion;
- encouraged under-delivery;
- created a conflict between current requirements;
- loaded the software architecture reference in the wrong context.

Open a behavior report before proposing a large rewrite. Include the model,
harness, version, task, expected outcome, observed result, and safe evidence.
Redact private code, credentials, customer data, and personal information.

## Contribution boundaries

- Keep the project focused on scope, completion, evidence, stopping, and the
  conditional software architecture guidance.
- Do not add a runtime, hook, state store, service, framework, mode system, or
  platform adapter without repeated evidence that the current mechanism cannot
  meet a present requirement.
- Do not turn one model-specific anecdote into a universal rule.
- Preserve the distinction between broad inquiry and bounded deliverables,
  changes, and actions.
- Preserve the distinction between “smallest” and “incomplete.”
- Keep public documentation in English and avoid invented effectiveness claims.

## Changing the Skill

The installable source of truth is
[`skills/smallest-complete`](skills/smallest-complete).

For a Skill change:

1. Explain the observed failure and why the current wording does not cover it.
2. Propose the smallest change that fixes the failure family rather than one
   transcript's wording.
3. Check that `SKILL.md`, `agents/openai.yaml`, and the conditional reference
   remain consistent.
4. Test positive, negative, and boundary prompts with isolated runs when
   possible.
5. Report what the evidence demonstrates and what remains unknown.

Keep `SKILL.md` under 500 lines. Put software-only detail in the existing
conditional reference rather than expanding the core Skill for every task.

## Changing installation or documentation

- Installation must remain idempotent, reversible, and limited to the published
  Skill plus one global activation block.
- `install/AGENTS.append.md` is the single source of truth for that block.
- Preserve existing user instructions and stop on conflicting local edits.
- Keep README links relative and verify every referenced file exists.
- The hero can be witty; technical claims must remain literal.

## Pull requests

Keep each pull request focused on one observed problem. Include:

- the behavior or documentation problem;
- the proposed change and why it is the smallest complete fix;
- prompts, diffs, or validation evidence;
- any deliberate non-goals.

Before submitting, read the complete diff as a user and as an agent. Remove any
addition whose omission would not break required behavior, a hard rule, or the
clarity of the requested artifact.
