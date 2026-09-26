---
name: github-issues
description: File, triage, or label a GitHub issue in this repo the way we do it — apply an issue TYPE (Bug/Feature/Task), the right LABELS, and the Project board fields (Status/Priority/Size/Estimate). Use whenever creating, editing, triaging, prioritizing, sizing, or bulk-labeling issues, moving an issue on the board, or adding/renaming/removing a label. Covers the "Bug is a type not a label" gotcha, the gh-can't-set-type gotcha, the version-controlled label taxonomy in .github/labels.yml, and a helper that sets board fields by name.
---

# Filing & triaging GitHub issues

This repo classifies issues on **three independent axes**. Set all three.

1. **Issue type** — `Bug` · `Feature` · `Task`. Org-level metadata, exactly
   one per issue. This is _not_ a label.
2. **Labels** — the taxonomy in `.github/labels.yml` (area, status, kind…).
   Zero or more per issue.
3. **Project board fields** — `Priority`, `Size`, `Estimate` and `Status` on
   the org board **"Pragmatic Papers Development"** (project #3). See
   [Project board fields](#project-board-fields).

The single most common mistake: treating `Bug` as a label. **There is no
`bug` label** — `Bug` is an issue _type_. Applying a nonexistent label
silently no-ops, so the issue ends up classified as nothing.

## Issue types

| Type      | Use for                                        |
| --------- | ---------------------------------------------- |
| `Bug`     | An unexpected problem or behavior              |
| `Feature` | A request, idea, or new functionality          |
| `Task`    | A specific, scoped piece of work (the default) |

Pick one on **every** new issue. When unsure between `Task` and `Feature`:
user-facing capability → `Feature`; internal/dev work (refactor, CI, deps,
tests, docs tooling) → `Task`.

### Setting the type

**GitHub MCP tools (web / remote sessions — the easiest path).**
`issue_write` takes the type by _name_ in the same call that creates the
issue: