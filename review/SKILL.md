---
name: review
version: 0.0.1
description: |
  Review a TalTech project diff for correctness, maintainability, testing
  gaps, risky architecture, and issues likely to surface during grading or
  demo. Findings first. No style-nit output.
allowed-tools:
  - Bash
  - Read
  - Edit
  - Write
  - Grep
  - Glob
  - AskUserQuestion
---

# Review

You are running a serious code review.

Primary concerns:

- broken logic
- hidden risk
- weak validation
- bad persistence or data handling
- missing tests on the critical path
- setup or demo fragility

## Step 1: Check branch scope

1. Run `git branch --show-current`.
2. If on `main`, stop with: `Nothing to review — no feature branch diff.`
3. Run `git fetch origin main --quiet`.
4. Run `git diff origin/main --stat`.
5. If there is no diff, stop with the same message.

## Step 2: Load the checklist

Prefer the local checklist:

- `review/checklist.md`

If that file is unavailable, report the error and stop.

## Step 3: Read the full diff

Run:

```bash
git diff origin/main
```

Read the full diff before commenting. Do not flag issues that are already fixed in the same change.

## Step 4: Review passes

Review in this order:

1. correctness and data safety
2. architecture and maintainability
3. test coverage gaps
4. setup and demo risk

## Output rules

- Findings come first.
- Order by severity.
- Include file references.
- Keep each finding concrete.
- Do not pad with style comments unless they represent maintainability risk.

For each finding include:

- file
- problem
- why it matters
- recommended fix

## Severity model

- Critical: broken main flow, data-loss risk, serious security issue, impossible demo
- High: significant correctness or architecture problem
- Medium: real quality gap or missing coverage
- Low: worth fixing, but unlikely to sink the project

## If the user wants fixes

If the review surfaces high-value fixes and the user wants them applied, fix only the concrete reviewed issues. Do not silently redesign the project during review.
