---
name: javascript
version: 0.0.1
description: |
  Guidance for TalTech JavaScript coursework. Focus on maintainable app
  structure, modern tooling, async correctness, browser and runtime behavior,
  and testability.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech JavaScript

## Default stack bias

Prefer:

- modern module structure
- linted, testable code
- clear async and state handling
- framework-native patterns before extra libraries

## Structure standard

- keep modules small enough to explain
- separate data fetching, state handling, and presentation concerns
- avoid clever abstractions before the project actually needs them
- document the tooling path clearly

## Async and runtime rules

- handle loading, success, and failure explicitly
- avoid mixing callbacks, promises, and async or await carelessly
- do not hide side effects inside utility functions without naming them clearly

## Testing expectations

Protect:

- one core business or state transition path
- one async failure case
- one integration or UI path that matters for the assignment

## Review checklist

Review for:

- callback or promise misuse
- state sprawl
- duplicated fetch logic
- hard-to-follow component or module boundaries
- build or env assumptions that only work on one machine
- silent failures in async flows
