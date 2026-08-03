<div align="center">

# Smallest Complete

**Help powerful agents finish the job—and stop before the side quests.**

<p>
  <img alt="Installer: Codex" src="https://img.shields.io/badge/installer-Codex-0F64B5?style=flat-square">
  <img alt="Skill scope: Codex and ChatGPT Work" src="https://img.shields.io/badge/skill_scope-Codex_%7C_ChatGPT_Work-5B56B6?style=flat-square">
  <img alt="Runtime: none" src="https://img.shields.io/badge/runtime-none-0A8447?style=flat-square">
  <img alt="Telemetry: none" src="https://img.shields.io/badge/telemetry-none-3a3f47?style=flat-square">
  <img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-7959A2?style=flat-square">
</p>

<p><sub>The smallest result that fully works. Not the smallest amount of thinking. Not half the job.</sub></p>

</div>

![Four-panel comic: a developer asks an agent to fix one button; the agent builds a state machine, sync layer, recovery system, and version history; Smallest Complete brings it back to a fixed and tested button](docs/assets/export-button-empire.webp)

<p align="center"><em>The button works in panel four. The distributed recovery subsystem did not survive the review.</em></p>

## Install it by asking Codex

Paste this into a new Codex task. Codex will read the repository, install the
Skill, preserve your existing global instructions, add the activation rule once,
and verify the result.

```text
Install Smallest Complete v0.1.0 from https://github.com/JetXu-LLM/smallest-complete/tree/v0.1.0.
Read README.md and INSTALL.md at that release first, then follow INSTALL.md exactly. Verify the published SHA256SUMS before writing. Preserve all existing global Codex instructions, make no unrelated changes, show me the planned file-level changes, install the skill globally, add the required Smallest Complete activation block once, validate the installation, and report exactly what changed. If the existing installation conflicts with the published files, stop and show me the conflict instead of guessing.
```

Then start a new Codex task so the new global Skill registry and instructions are
loaded. That is the recommended install path. If you prefer to inspect or perform
each step yourself, see [INSTALL.md](INSTALL.md).

### What changes on your machine

Only two active changes are made:

1. `smallest-complete` is copied into your global Codex skills directory.
2. The contents of [`install/AGENTS.append.md`](install/AGENTS.append.md) are
   appended once to your global `AGENTS.md`.

Existing global instructions stay in place. When existing content must change,
the installer also creates a timestamped safety backup under
`<codex-home>/backups/smallest-complete/`. There is no runtime, daemon, hook,
MCP server, dependency, account, or telemetry. Installation is inspectable and
reversible.

## You asked for one thing

You asked for a button fix. The agent found an adjacent risk. That risk suggested
a compatibility layer. The compatibility layer needed recovery. Recovery needed
state. State needed migration. Migration needed a test matrix. Several hours
later, the architecture is ready for weather events and international expansion.

The button is still broken.

This is not merely “too much code.” It is a mismatch between three things:

- **Capability:** the agent can notice and build a great deal.
- **Authorization:** useful discoveries are mistaken for permission to act.
- **Stopping:** “done” quietly changes from the requested outcome to the absence
  of any remaining concern.

Similar experiences now recur in Codex community discussions: ordinary tasks
turn into [architecture reworks, governance, and hypothetical-failure
testing](https://www.reddit.com/r/codex/comments/1uuo6x4/how_to_keep_gpt56_sol_high_from_overengineering/),
or into [recursive verification long after the requested work is
complete](https://www.reddit.com/r/codex/comments/1v9dq4b/gpt56_sol_gets_stuck_in_implementation_and_review/).
Those reports are observations, not proof of one universal model defect. The
failure can emerge from the interaction among model behavior, harness defaults,
long context, broad authority, and an underspecified stopping condition.

## Smallest *and* Complete

The name is the objective function.

| | What it constrains | What it prevents |
| --- | --- | --- |
| **Smallest** | Deliverables, permanent machinery, changes, and external actions | Adjacent findings becoming unrequested systems |
| **Complete** | Required behavior, hard constraints, observable success, and evidence | Token minimalism, superficial fixes, and premature stopping |

“Smallest” does **not** mean “investigate as little as possible.” A strong
research answer may need broad inquiry. A difficult bug may require reading a
large part of the system. The boundary is between learning something and turning
it into a new deliverable, implementation, or external action.

“Complete” does **not** mean “solve every related problem.” It means the requested
result works, required behavior is preserved, relevant constraints are satisfied,
and the completion claim is supported by proportionate evidence.

## How it works

Smallest Complete gives the agent one short control loop:

1. **Establish the current contract.** Identify the actual outcome, authorized
   kind of work, hard constraints, observable acceptance evidence, and non-goals.
2. **Make additions earn their place.** Add a deliverable, abstraction, state,
   service, safeguard, or action only when the requested result, a current hard
   rule, observed evidence, or explicit authorization requires it.
3. **Repair at the owning boundary.** Fix the capability that owns the behavior;
   do not turn a local defect into a platform rewrite.
4. **Validate the real outcome.** Test the strongest practical way the claim
   could be wrong, and claim only what the evidence proves.
5. **Stop.** Once the authorized result is complete, record useful adjacent
   findings if needed—do not implement them.

For non-trivial software work, the Skill conditionally loads an
[`elegant-architecture`](skills/smallest-complete/references/elegant-architecture.md)
design lens that keeps control paths, ownership, state, and coordination as
simple as the real job allows.

For research, writing, analysis, documents, and presentations, that software
reference stays unloaded. Inquiry remains as broad as the requested artifact
needs; deliverables and actions remain in scope.

## What should change in practice

These are intended effects, not benchmark claims:

- fewer unauthorized side quests and speculative subsystems;
- a clearer, stable definition of the current job;
- less permanent machinery for hypothetical future problems;
- validation calibrated to the claim instead of to every imaginable failure;
- fewer cases where a plan, scaffold, or test suite is mistaken for the result;
- an explicit point at which a capable agent should stop.

The project does not currently claim an aggregate percentage improvement. Its
evaluation contract is deliberately stricter than that; see
[`docs/evaluation.md`](docs/evaluation.md).

## Three small examples

| Request | Smallest Complete behavior |
| --- | --- |
| “Fix CSV export when descriptions contain commas.” | Fix escaping at the owning boundary, preserve existing formats, test the failing case, and leave a multi-format export redesign as an adjacent suggestion. |
| “Explain why checkout conversion fell last week.” | Investigate broadly enough to support the conclusion, then deliver the requested analysis—not an unsolicited analytics platform. |
| “Turn these notes into a five-slide update.” | Produce five persuasive, accurate slides; do not quietly add a new brand system, content pipeline, or fifteen-slide appendix. |

## What it is not

- Not “write fewer lines at any cost.” Necessary complexity remains necessary.
- Not a replacement for model judgment; it is a better frame for that judgment.
- Not a rigid ceremony for trivial, obviously local tasks.
- Not a permission system or enforcement firewall.
- Not proof against every model, harness, context, or instruction failure.
- Not a new agent framework. It is one Skill, one conditional reference, and one
  activation paragraph.

## Read the project

- [Install, update, and uninstall](INSTALL.md)
- [Why capable agents expand the mission](docs/why.md)
- [Why the project is intentionally this small](docs/design.md)
- [How to evaluate the Skill without fooling yourself](docs/evaluation.md)
- [Contributing](CONTRIBUTING.md)
- [The complete Skill source](skills/smallest-complete/SKILL.md)

## Star it before your agent discovers another adjacent risk

If Smallest Complete helps your agent deliver the thing you actually asked for,
star the repository. It helps the next developer find it before their button fix
gets its own recovery department.

## License

[MIT](LICENSE). Smallest Complete is an independent project and is not affiliated
with, endorsed by, or sponsored by OpenAI or Anthropic. Product names are used
only to describe compatibility.
