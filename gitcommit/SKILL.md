---
name: gitcommit
description: Generate a concise one-line commit message from staged changes and commit. A minimal alternative to git-commit with no conventional-commit scaffolding. Use when the user wants a lightweight commit flow, a plain commit message, or mentions "simple commit".
allowed-tools: Bash
---

# Simple Git Commit

**Arguments**: the user may pass a commit message directly, e.g. `/git-commit-simple Fix login redirect`. If an argument is present, treat it as the final message verbatim — **skip steps 2 and 3** (no drafting, no confirmation) and go straight to step 4.

1. **Inspect**: `git diff --staged`. If nothing is staged, stop and tell the user to `git add` first — never stage automatically.
2. **Draft** (only when no argument was provided): one imperative sentence under 72 chars saying *what* changed, not how. Start with a **capitalized** verb (`Fix`, `Add`, `Remove`, `Refactor`…).
   - Good: `Fix redirect error after user login`
   - Bad: `Fix bug` (which bug?), `Update code` (what changed?)
3. **Confirm** (only when no argument was provided): show the message to the user and wait for approval or an edit.
4. **Commit**: `git commit -m "<message>"`
