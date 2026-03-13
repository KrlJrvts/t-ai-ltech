---
name: testing
version: 0.0.1
description: |
  Guidance for TalTech testing work. Focus on unit, integration, UI, and CI
  coverage for the critical path without building a fake sense of safety.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech Testing

## Focus areas

- critical-path tests first
- maintainable test structure
- meaningful assertions
- CI readiness
- avoiding flaky UI tests

## Test strategy expectations

- choose the smallest test that gives real confidence
- keep the test pyramid sensible
- avoid UI tests for things that unit or integration tests can cover better
- treat setup and test data as part of test quality

## Review checklist

Call out:

- critical demo paths with no protection
- assertions that do not test real behavior
- tests that are too brittle for their value
- no CI or no documented way to run tests

## Expected output

Good testing guidance should name:

- what behavior is being protected
- the smallest test layer that can protect it
- what failure would look like
- how the test should be run locally
