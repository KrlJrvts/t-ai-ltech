---
name: mobile
version: 0.0.1
description: |
  Guidance for TalTech mobile and hybrid mobile coursework. Focus on React
  Native or Flutter-level architecture choices, mobile UX, and stable demos.
allowed-tools:
  - Read
  - Grep
  - Glob
---

# TalTech Mobile

## Focus areas

- simple mobile architecture
- auth and data flow
- offline or weak-network behavior where relevant
- predictable navigation
- demoable build and install story

## Expectations

- choose one stable mobile path
- keep navigation and state handling understandable
- test the app on the target device class early
- keep install and run instructions explicit

## Review checklist

Review for:

- unstable navigation flow
- emulator-only assumptions
- weak handling of loading and failure states
- too many unfinished device features

Prefer one working mobile path over broad but unstable feature scope.

## Expected output

Good guidance should specify:

- target device or platform
- navigation model
- data and auth flow
- install, run, and demo steps
