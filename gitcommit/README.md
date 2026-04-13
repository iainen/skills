# git-commit-simple

A minimal Claude Code skill for lightweight git commits. Generates a concise one-line commit message from staged changes — no conventional-commit scaffolding, no co-author footer, no ceremony.

## When to use

Invoke this skill when you want a plain, imperative commit message for already-staged changes:

- `/git-commit-simple` — inspect staged diff, draft a message, confirm, then commit
- `/git-commit-simple Fix login redirect` — commit immediately with the provided message verbatim

If nothing is staged, the skill stops and asks you to `git add` first. It will never stage files automatically.

## Message style

- One imperative sentence, under 72 characters
- Starts with a capitalized verb: `Fix`, `Add`, `Remove`, `Refactor`, …
- Describes *what* changed, not *how*

Good: `Fix redirect error after user login`
Bad: `Fix bug`, `Update code`

## Installation

Place the `gitcommit/` directory under a Claude Code skills path (e.g. `~/.claude/skills/` or a project-local skills directory). The skill will appear as `git-commit-simple`.

## Files

- `SKILL.md` — skill definition and steps
- `README.md` — this file
