---
name: plan
version: 0.0.1
description: |
  Plan a TalTech project architecture before implementation. Lock in course
  fit, component boundaries, data flow, testing scope, deployment shape, and
  what must be deferred to keep the project finishable.
allowed-tools:
  - Read
  - Grep
  - Glob
  - AskUserQuestion
---

# TalTech Plan

Plan the project before building it.

This is the architecture pass. The goal is to remove ambiguity before code is written.

## Step 0: Scope challenge

Before reviewing anything, answer:

1. What already exists in the repo that solves part of the problem?
2. What is the minimum diff that achieves the assignment goal?
3. Which parts of the current idea look overbuilt for a TalTech project?
4. Which decisions materially affect maintainability, testability, or demo reliability?

If the plan touches many moving parts, challenge scope once up front. After that, commit to making the chosen scope succeed.

## Required planning sections

Always cover these sections:

### 1. Course fit

State which course area this project belongs to and why the chosen architecture matches that course.

### 2. Stack confirmation

State:

- primary language
- framework
- persistence technology
- frontend technology, if any
- test stack
- deploy or demo approach

### 3. Architecture boundaries

Explain:

- major components
- responsibilities of each component
- what logic lives where
- what should not be mixed together

### 4. Data flow

Describe the critical path from user input to persisted or displayed result.

Use ASCII diagrams for:

- request flow
- state transitions
- API boundaries
- major background or async steps

### 5. Persistence and integrations

Be explicit about:

- schema or entity ownership
- validation boundaries
- external APIs or services
- failure handling

### 6. Testing plan

Map the architecture to tests:

- unit tests for logic-heavy code
- integration tests for boundaries
- UI or browser smoke tests for the main flow

For each major new codepath, say what test should protect it.

### 7. Deployment or demo plan

State whether the project is:

- local-only
- locally demoed with seeded data
- deployed publicly

If deployment is planned, name the platform and configuration assumptions.

### 8. Not in scope

List deferred work clearly. A clean deferral is better than pretending optional work is part of the MVP.

## Review checklist

Evaluate the plan against these dimensions:

- course alignment
- architecture clarity
- dependency sprawl
- state or data complexity
- testability
- deployability
- demo reliability
- documentation burden

## Failure-mode requirement

For each major codepath, identify one realistic failure mode and whether the plan covers:

- validation
- error handling
- user-visible feedback
- a test

If a codepath can fail silently with no test and no user feedback, flag it as a critical planning gap.

## AskUserQuestion rule

Use `AskUserQuestion` only for real architectural forks, such as:

- monolith vs split frontend/API
- server-rendered vs SPA
- ORM vs explicit SQL-heavy approach
- local state vs shared/global client state

Lead with the recommended option and explain the tradeoff in code quality, learning value, and delivery risk.

## Planning standard

Prefer the smallest architecture that still looks rigorous and maintainable.
Bias toward explicit boundaries, minimal abstractions, and testable critical flows.
