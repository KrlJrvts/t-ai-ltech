---
name: qa
version: 0.0.1
description: |
  Systematically QA test a web application or browser-based university project.
  Supports full, quick, and regression-style passes with screenshots, issue
  tracking, and a report written to .agent-stack/qa-reports/.
allowed-tools:
  - Bash
  - Read
  - Write
---

# QA

You are a QA engineer testing a real project, not just loading a page once.

## Modes

- `full`: systematic exploration of the main user-facing flow
- `quick`: 30-second smoke pass
- `regression`: repeat a previous QA scope and compare changes

## Parameters to infer from the user request

- target URL
- mode
- output directory
- page or feature scope
- auth requirements
- browser engine if specified

Defaults:

- mode: `full`
- output directory: `.agent-stack/qa-reports`
- browser engine: `chromium`

## Setup

Find the browse binary:

```bash
B=$(browse/bin/find-browse 2>/dev/null)
```

If missing, stop and tell the user to run `./setup`.

Create the report directory:

```bash
REPORT_DIR=".agent-stack/qa-reports"
mkdir -p "$REPORT_DIR/screenshots"
```

If the user requested a specific browser, use:

```bash
BROWSE_BROWSER=firefox "$B" goto https://example.com
```

Replace `firefox` with `chromium`, `chrome`, or `edge` as needed.

## Workflow

### Phase 1: Orient

1. Open the target page
2. Capture an annotated snapshot
3. Inspect console errors
4. Map navigation and major flows

### Phase 2: Explore

For each important page or state:

- verify page load
- click important controls
- test forms and validation
- inspect loading, empty, and error states
- check console after interaction
- verify responsive layout when relevant

### Phase 3: Document

Record issues immediately with:

- screenshot or annotated snapshot
- repro steps
- observed result
- expected result
- severity

### Phase 4: Wrap up

Produce:

- pass/fail summary
- issue list ordered by severity
- top 3 fixes
- screenshots
- short smoke-test path

## Severity model

- Critical: likely demo failure or broken main flow
- High: visible breakage or major confusion
- Medium: meaningful bug or UX weakness
- Low: polish issue

## Report standard

The report should be usable by:

- the student
- a teammate
- a grader
- a future agent rerunning the same QA scope

Keep it concrete and evidence-driven.
