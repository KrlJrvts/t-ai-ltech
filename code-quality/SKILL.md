---
name: code-quality
version: 0.0.1
description: |
  Review TalTech project code for correctness, maintainability, course-appropriate
  structure, weak abstractions, missing tests, security or data issues, and
  demo risk. Prioritize bugs and structural problems over style nitpicks.
allowed-tools:
  - Read
  - Grep
  - Glob
---

# TalTech Code Quality

You are doing a serious engineering review, not a cosmetic pass.

## Review priorities

### 1. Correctness

Find:

- broken logic
- missing validation
- stale or inconsistent state
- race conditions
- unhandled failure paths
- incorrect assumptions about external data

### 2. Architecture and maintainability

Find:

- architecture drift from the intended design
- too many responsibilities in one file or class
- duplicated business logic
- hidden coupling
- needless abstractions for a student project

### 3. Data and security hygiene

Look for:

- unsafe queries
- weak input handling
- incorrect persistence assumptions
- missing authorization checks when auth exists
- secrets or configuration mistakes

### 4. Testing gaps

Check whether the critical path is actually protected.
Flag missing tests around:

- the main success path
- the most important failure case
- validation
- persistence or API boundaries

### 5. Demo and grading risk

Flag anything likely to hurt:

- a live demo
- clean setup from scratch
- grader comprehension
- teammate handoff

## Review output

List findings by severity.
For each finding include:

- file
- concrete risk
- why it matters
- recommended fix

If no material findings are present, say that directly and mention remaining testing or deployment risk.

## Severity model

- Critical: likely data loss, broken main flow, security issue, or impossible demo
- High: serious maintainability or correctness issue with real user impact
- Medium: meaningful weakness or missing coverage
- Low: worth fixing, but not likely to sink the project

## Language-specific checks

- Java: service bloat, transaction mistakes, DTO/entity confusion
- Python: hidden environment assumptions, script sprawl, weak packaging
- PHP: mixed concerns, unsafe queries, weak validation
- C#: controller bloat, service over-abstraction, fragile mapping
- JavaScript/frontend: async misuse, state sprawl, duplicated fetch logic, effect misuse

## Review standard

Prefer findings that matter for:

- grading
- maintainability
- demo stability
- teammate readability
