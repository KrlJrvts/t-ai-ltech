---
name: build
version: 0.0.1
description: |
  Build the smallest strong TalTech project with conventional architecture,
  course-appropriate technology choices, meaningful tests, and documentation
  that is strong enough for grading, demo, and teammate handoff.
allowed-tools:
  - Bash
  - Read
  - Write
  - Edit
  - Grep
  - Glob
---

# TalTech Build

You are implementing a TalTech project for delivery.

## Priorities

1. Ship the graded user flow.
2. Keep the architecture explainable.
3. Use the course-appropriate language and conventions.
4. Add tests for the critical path.
5. Leave clear setup and demo documentation.

## Operating rules

- Prefer adapting existing code over adding new abstractions.
- Prefer conventional folder structure over custom architecture.
- Prefer one stable data flow over multiple partially-finished features.
- Prefer explicit validation and error handling over optimistic happy-path code.
- Prefer boring deployment over clever infrastructure.

## Build workflow

### Phase 1: Orient

Read the current repo first:

- package or build files
- test setup
- environment configuration
- entry points
- existing docs

Determine:

- what already exists
- what is missing
- what can be reused directly

### Phase 2: Lock the vertical slice

Define the critical path being built in this pass:

- trigger
- main processing steps
- expected result
- success criteria

Do not expand scope mid-build unless the user explicitly changes the goal.

### Phase 3: Implement

Implement the main path first, then fill in:

- validation
- error states
- empty states
- persistence
- tests
- docs

### Phase 4: Harden

Before finishing, review for:

- duplicated logic
- hidden configuration
- unclear naming
- brittle async flows
- demo-breaking rough edges

### Phase 5: Close out

Update the docs and setup story so someone else can run the project.

## Required engineering standards

### Structure

- keep responsibilities separated
- avoid giant files that mix unrelated concerns
- keep service boundaries obvious

### Validation

- validate user input explicitly
- do not rely on the frontend alone for correctness
- surface actionable errors

### Tests

At minimum, protect:

- the main success path
- the most important validation failure
- one integration boundary

### Docs

The repo should explain:

- how to install dependencies
- how to run locally
- how to run tests
- required environment variables
- how to demo the project

## Before finishing, verify

- local run works
- test command works
- env vars are documented
- known limitations are written down
- the main demo path is stable

## Language-aware bias

- Java: keep the application structure conventional and avoid service explosion
- Python: keep environments explicit and package structure clean
- PHP: keep routing, validation, rendering, and database access separated
- C#: keep MVC or API layers conventional and testable
- JavaScript: keep module boundaries clean and async flows understandable
