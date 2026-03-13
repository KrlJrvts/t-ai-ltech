---
name: ship
version: 0.0.1
description: |
  Release or submit a ready branch: sync with main, run tests, review the
  diff, update VERSION, commit, and push. This workflow does not maintain a
  detailed changelog.
allowed-tools:
  - Bash
  - Read
  - Write
  - Edit
  - Grep
  - Glob
  - AskUserQuestion
---

# Ship

Use this only when the branch is already ready to land.

## Stop conditions

Stop if:

- you are on `main`
- merge conflicts cannot be resolved safely
- tests fail
- review finds critical issues that require fixes first

## Workflow

### 1. Pre-flight

- check current branch
- inspect `git status`
- inspect `git diff origin/main --stat`
- inspect recent branch commits

### 2. Sync with main

```bash
git fetch origin main
git merge origin/main --no-edit
```

### 3. Run tests

Run the project's actual test commands.
If the repo has multiple suites, run the suites that matter for the changed code.

If tests fail, stop and report the failures.

### 4. Review before release

Run a review pass against `origin/main`.
If the review finds critical issues, stop and surface them.

### 5. Version update

This repository uses a simple semantic version in `VERSION`:

- `MAJOR.MINOR.PATCH`

For normal work, bump `PATCH`.
Ask before changing `MAJOR` or `MINOR`.

### 6. Commit and push

Group changes logically, then:

```bash
git push -u origin <branch>
```

## Important rules

- Do not invent a changelog workflow here.
- Do not hide failing tests.
- Do not cut corners on version or setup consistency.
- Prefer smaller logical commits over one large dump when the diff is substantial.
