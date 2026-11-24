# RSE skill suite

Five complementary agent skills for **Claude Code** and **Codex** that make AI coding agents take
proportionate, evidence-based engineering decisions. Install all five side by side.

| Skill | Role | What it does |
| --- | --- | --- |
| [reliable-software-engineering](https://github.com/reliable-engineering-skills/reliable-software-engineering) | Core (required) | Proportionate, evidence-based engineering decisions: scope, smallest sufficient change, contracts, payments and data history, authorization, caching, operations and honest verification. |
| [rse-task-packs](https://github.com/reliable-engineering-skills/rse-task-packs) | Companion | Turns accepted work into portable, resumable task packs for another agent or a later session, with a structural validator. |
| [rse-refactoring](https://github.com/reliable-engineering-skills/rse-refactoring) | Companion | Behavior-preserving refactoring and codebase rescue, one responsibility at a time, with a before/after check recorder. |
| [rse-security-review](https://github.com/reliable-engineering-skills/rse-security-review) | Companion | Focused security review: trace untrusted input to sensitive sinks and report evidence-graded findings without touching production. |
| [rse-debugging](https://github.com/reliable-engineering-skills/rse-debugging) | Companion | Fixes reported bugs from evidence: reproduces with a failing check, fixes the cause, and leaves a regression test, even when the cause looks obvious. |

**How they fit together:** the core skill owns the shared rules (respect the request type, smallest sufficient
change, preserve contracts, unknown outcome is not failure, no evidence no claim). Each companion adds one
workflow and links back to the core instead of copying it, so every rule has a single owner.

## Install the suite

The companions link into the core skill's files, so install all five side by side.

Claude Code (PowerShell):

```powershell
foreach ($r in "reliable-software-engineering", "rse-task-packs", "rse-refactoring", "rse-security-review", "rse-debugging") { git clone "https://github.com/reliable-engineering-skills/$r" "$env:USERPROFILE\.claude\skills\$r" }
```

Claude Code (bash/zsh):

```bash
for r in reliable-software-engineering rse-task-packs rse-refactoring rse-security-review rse-debugging; do git clone "https://github.com/reliable-engineering-skills/$r" ~/.claude/skills/$r; done
```

Codex: clone the same five repositories into `~/.codex/skills/`. Update later with `git pull` in each folder.
To install exactly the current release instead of `main`, see [Pin a release](https://github.com/reliable-engineering-skills/reliable-software-engineering#pin-a-release).

All repositories are MIT-licensed and tested on Linux, Windows and macOS. Current release: 3.3.0, in which `rse-debugging` sees the failing test fail before it fixes the code (task packs 3.1.1; refactoring and security review 3.0.0).
