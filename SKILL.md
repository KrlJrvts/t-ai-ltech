---
name: t-ai-ltech
version: 0.0.1
description: |
  Top-level repository skill for T-AI-LTech. Use it to orient a
  coding agent inside this repo, choose the right skill folder, and follow the
  TalTech-first engineering workflow.
allowed-tools:
  - Read
  - Grep
  - Glob
---

# T-AI-LTech

This is the top-level entrypoint for the repository.

Use this skill when you need to understand:

- what this repository is for
- which skill folder should handle the task
- how the TalTech workflow is structured
- which language or curriculum topic the work belongs to

## Read first

Read these files in this order:

1. `AGENTS.md`
2. `README.md`
3. `STACK.md`
4. `CURRICULUM.md`

Then read the specific skill folder that matches the task.

## Workflow skills

- `intake/`
- `plan/`
- `build/`
- `code-quality/`
- `deploy/`
- `demo/`
- `submit/`

## Language skills

- `java/`
- `python/`
- `php-web/`
- `csharp/`
- `javascript/`

## Frontend framework skills

- `react/`
- `vue/`
- `angular/`

## Curriculum-topic skills

- `computers/`
- `web-tech/`
- `databases/`
- `algorithms/`
- `networking/`
- `operating-systems/`
- `testing/`
- `containers/`
- `mobile/`
- `mathematics/`
- `general-studies/`
- `internship/`
- `thesis/`

## Browser tooling

Use `browse/` when the task requires:

- UI testing
- smoke checks
- screenshots
- deploy verification
- browser-based demos

Browser engine selection is controlled by `BROWSE_BROWSER`:

- `chromium` (default)
- `chrome`
- `edge`
- `firefox`

## Selection rule

Choose the narrowest skill that actually matches the task.

If the user gives:

- an assignment brief -> `intake/`
- an architecture/design task -> `plan/`
- implementation work -> `build/`
- a code review task -> `code-quality/` or `review/`
- a browser/UI verification task -> `browse/`, `qa/`, or `demo/`
- a final hand-in task -> `submit/`

## Repository standard

Always optimize for:

- course fit
- code quality
- maintainability
- explainability
- testability
- demo readiness
