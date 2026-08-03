# Contributing to Smallest Complete

Smallest Complete gets better when people bring evidence—not only success
stories, but failed runs, comparisons where it made no difference, and cases
that prove its guidance wrong.

Short on time? [Open a behavior report](https://github.com/JetXu-LLM/smallest-complete/issues/new?template=behavior-report.yml).
You do not need a proposed fix. A sanitized, specific case is already a useful
contribution.

## What to bring

| Contribution | Useful when |
| --- | --- |
| **Behavior report** | The Skill expanded the task, stopped too early, failed to stop, suppressed useful inquiry, or activated in the wrong context. |
| **Comparative test** | You ran the same task with and without the Skill and observed a difference—or no meaningful difference. |
| **Counterexample** | A scope or architecture principle was wrong for the real job: more state, another control path, a compatibility layer, or broader work was genuinely necessary. |
| **Documentation fix** | The README, installation guide, or project explanation is unclear, inaccurate, or overstates the evidence. |
| **Skill or guidance change** | You can connect a concrete failure or failure family to a focused improvement in the Skill or its architecture reference. |

Positive results are welcome too. If the Skill prevented overreach, preserved
useful inquiry, or made an architecture materially clearer, show the task and
the observable difference. Please do not turn one good run into a universal
effectiveness claim.

## Make the case usable

Use the
[behavior report template](https://github.com/JetXu-LLM/smallest-complete/issues/new?template=behavior-report.yml)
when possible. For an issue, comment, or pull request, this compact record is
enough to start:

```text
Environment: model, reasoning effort, Codex or ChatGPT surface, version if known
Task: the sanitized request and only the instructions needed to understand it
Expected: the observable result and intended scope
Observed: what the agent delivered, changed, omitted, or kept doing
Evidence: transcript excerpt, diff, test, screenshot, or reproduction steps
Pattern: one-off, repeated, or unknown—and what changed between runs
```

Keep prompts and outputs close to verbatim where publication is safe;
paraphrasing can hide the behavior that matters. Remove secrets, credentials,
private code, customer data, personal information, and anything you are not
authorized to publish. Missing version information is fine when it is unknown.
Missing evidence makes the report much harder to act on.

See [the evaluation guide](docs/evaluation.md) for ways to compare behavior
without claiming more than a test demonstrates.

## Counterexamples are especially valuable

The project treats its principles as strong defaults, not laws of nature. We
want cases where Smallest Complete's own advice becomes the problem, including:

- the smallest-looking path under-delivered or moved complexity elsewhere;
- broader investigation or implementation was required to complete the actual
  request;
- additional state was the honest representation of a business fact;
- multiple control paths reflected genuinely different workflows;
- compatibility or recovery machinery was a present requirement rather than
  speculative future-proofing;
- agent judgment was too variable for a rule that needed deterministic code.

Explain what would have failed if the allegedly “extra” mechanism were removed.
A strong counterexample can improve the guidance even when it never becomes a
code or wording change.

## Changing the Skill or its guidance

The installable source of truth is
[`skills/smallest-complete`](skills/smallest-complete).

For a non-trivial Skill change:

1. Open an issue describing the observed failure and available evidence before
   opening a pull request.
2. Explain why the case exposes a broader failure family rather than only one
   transcript's wording. A single case can still be decisive when it reveals a
   clear contradiction or unsafe instruction.
3. Propose the smallest change that addresses that failure without weakening
   unrelated behavior.
4. Check `SKILL.md`, `agents/openai.yaml`, and the conditional architecture
   reference for consistency.
5. Test positive, negative, and boundary prompts with isolated runs when
   practical.
6. Report what the evidence demonstrates and what remains unknown.

Keep `SKILL.md` under 500 lines. Put coding- and architecture-specific detail in
the existing conditional reference instead of expanding the core Skill for
every task.

Do not add a runtime, hook, state store, service, framework, mode system, or
platform adapter unless repeated evidence shows that the current mechanism
cannot meet a present requirement. Preserve the distinctions between broad
inquiry and bounded action, and between “smallest” and “incomplete.”

## Changing installation or documentation

- Installation must remain idempotent, reversible, and limited to the published
  Skill plus one global activation block.
- `install/AGENTS.append.md` is the single source of truth for that block.
- Preserve existing user instructions and stop on conflicting local edits.
- Keep README links relative where practical and verify every referenced file.
- Keep public documentation and contributions in English.
- The hero can be witty; technical and effectiveness claims must remain literal
  and evidence-calibrated.

## Pull requests

Keep each pull request focused on one observed problem. Include:

- the behavior or documentation problem;
- the proposed change and why it is the smallest complete fix;
- prompts, diffs, or validation evidence;
- any deliberate non-goals.

Before submitting, read the complete diff as a user and as an agent. Remove any
addition whose omission would not break required behavior, a hard rule, or the
clarity of the requested artifact.

Bring the strongest case you have—especially one that shows this project is
wrong. That is how the guidance becomes less dogmatic and more useful.
