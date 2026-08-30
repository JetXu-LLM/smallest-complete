# Install Smallest Complete

This document is both a human-readable installation guide and the instruction
contract followed by Codex when a user pastes the install prompt from the README.

The recommended path is to give Codex this prompt:

```text
Install Smallest Complete from https://github.com/JetXu-LLM/smallest-complete.
Follow INSTALL.md exactly.
```

The prompt stays short on purpose. The procedure below is the safety contract.

## Agent installation procedure

When following the prompt above, perform only the procedure below.

### 1. Resolve source and target paths

Use the `v0.1.7` checkout when it is already available. Otherwise, clone tag
`v0.1.7` from `https://github.com/JetXu-LLM/smallest-complete` into a fresh
temporary directory. Do not install from a moving branch. Do not execute code
from the repository; installation copies text files only.

The source Skill is:

```text
<repo>/skills/smallest-complete/
```

Resolve the Codex home directory from the existing `CODEX_HOME` setting when it
is set. Otherwise use the normal per-user Codex home for the current platform
(`~/.codex` on macOS and Linux). The targets are:

```text
<codex-home>/skills/smallest-complete/
<codex-home>/AGENTS.md
```

Before writing, verify that the source contains exactly these required files:

```text
SKILL.md
agents/openai.yaml
references/elegant-architecture.md
references/evidence-calibrated-testing.md
```

From the repository root, verify the five published installation inputs against
`SHA256SUMS`. Stop and report the mismatch if verification fails.

### 2. Inspect the current installation

Read the existing target Skill and global `AGENTS.md` if they exist.

Before writing, show the user the file-level plan: which paths will be created,
left unchanged, backed up, or changed. Continue with the already requested
installation unless a conflict or checksum failure requires a decision.

- If the target Skill is byte-for-byte identical to the repository source, do
  not copy it again.
- If the target Skill exists and differs, do not guess whether the difference is
  an older release or a local customization. Report the file-level difference
  and ask the user before replacement.
- If `AGENTS.md` already contains exactly one `## Smallest Complete` section
  whose content matches [`install/AGENTS.append.md`](install/AGENTS.append.md),
  do not append another copy.
- If a `## Smallest Complete` section exists but differs, report the difference
  and ask before editing it.

Do not modify any unrelated global instruction, configuration, skill, plugin, or
project file.

### 3. Back up existing user content

Before replacing an existing Skill or changing an existing `AGENTS.md`, create a
timestamped backup outside the skills discovery directory:

```text
<codex-home>/backups/smallest-complete/<timestamp>/
```

Back up only the files that will actually change. Do not place a backup Skill
under `<codex-home>/skills/`, because Codex may discover it as another Skill.

### 4. Install the Skill

Create `<codex-home>/skills/` if needed. Copy the complete
`skills/smallest-complete/` directory into
`<codex-home>/skills/smallest-complete/`, preserving the four source files
byte-for-byte and preserving their relative paths.

Do not rewrite, summarize, reformat, or “improve” the Skill while installing it.

### 5. Activate it globally

Append the complete contents of
[`install/AGENTS.append.md`](install/AGENTS.append.md) to the end of
`<codex-home>/AGENTS.md`, separated from existing content by a blank line.

If `AGENTS.md` does not exist, create it containing only that block. If the exact
block already exists once, leave the file unchanged. Never reorder, reformat, or
rewrite existing instructions.

### 6. Validate before reporting success

Verify all of the following:

1. The installed `SKILL.md`, `agents/openai.yaml`,
   `references/elegant-architecture.md`, and
   `references/evidence-calibrated-testing.md` exist.
2. Each installed file is byte-for-byte identical to the repository source.
3. `SKILL.md` declares `name: smallest-complete` and includes a non-empty
   `description`.
4. The installed Skill can resolve its relative
   `references/elegant-architecture.md` and
   `references/evidence-calibrated-testing.md` links.
5. Global `AGENTS.md` contains exactly one `## Smallest Complete` activation
   section and all pre-existing content is otherwise unchanged.
6. If a Skill validator is already available in the Codex environment, run it
   against the installed Skill. Do not install a new runtime or dependency only
   to perform this optional check.

Report the exact paths created or changed, the backup path when one was created,
the validations performed, and any unresolved conflict. Tell the user to start a
new Codex task so the new Skill registry and global instructions are loaded.

## Manual installation

If you prefer not to delegate installation, perform the same two changes
yourself:

1. Copy [`skills/smallest-complete`](skills/smallest-complete) to your global
   Codex skills directory as `smallest-complete`.
2. Append [`install/AGENTS.append.md`](install/AGENTS.append.md) once to the end
   of your global Codex `AGENTS.md`.

Preserve the directory structure exactly. Start a new Codex task after the
change.

## Updating

Use the current README prompt. Codex will read this contract, resolve the stable
release declared in step 1, and compare it with the installed copy. If they
differ, review the diff and explicitly approve replacement; the installer will
back up the current copy first. The activation block is changed only when it
differs from the published block and you approve that change.

## Uninstalling

Ask Codex:

```text
Uninstall Smallest Complete using the uninstall procedure in https://github.com/JetXu-LLM/smallest-complete/blob/main/INSTALL.md. Back up what will change, remove only the installed smallest-complete Skill and its exact global AGENTS.md activation section, preserve all unrelated content, validate the result, and report exactly what changed.
```

The uninstall procedure is:

1. Back up the installed Skill and current global `AGENTS.md` under
   `<codex-home>/backups/smallest-complete/<timestamp>/`.
2. Remove only `<codex-home>/skills/smallest-complete/`.
3. Remove only the `## Smallest Complete` section when it still matches the
   published activation block. If it has been customized, show the difference
   and ask before removing it.
4. Verify that unrelated global instructions and skills are unchanged.
5. Start a new Codex task.

## ChatGPT Work

The Skill instructions are written to apply to both Codex and ChatGPT Work. This
repository's agent-assisted installation procedure is Codex-first because it
uses Codex's global skills directory and `AGENTS.md`. The source Skill follows
the standard Skill directory structure and can be imported or packaged through
a supported ChatGPT Skill or plugin surface; this release does not claim a
separate one-prompt ChatGPT installer.
