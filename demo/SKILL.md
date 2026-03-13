---
name: demo
version: 0.0.1
description: |
  Prepare a TalTech project for presentation: smoke-test the main flow,
  capture evidence, identify issues most likely to hurt a live demo, and leave
  behind a reproducible presentation path.
allowed-tools:
  - Bash
  - Read
---

# TalTech Demo

Your job is to make the demo safe.

## Demo priorities

Focus on the issues most likely to embarrass the project in front of:

- lecturer
- teaching assistant
- teammate
- recruiter reviewing the repo later

## Always check

- entry page loads
- main flow works
- validation failures are understandable
- console has no obvious breakage
- desktop and mobile are acceptable when relevant

## Evidence rules

When using a browser UI:

- collect screenshots for key states
- note the exact repro path for failures
- capture console or visible error evidence for broken flows

When no browser UI exists:

- document the demo commands
- record expected input and output
- note any required seed data or environment setup

## Severity model

- Critical: likely to fail during live demo
- High: works inconsistently or looks unreliable
- Medium: noticeable weakness but not a hard blocker
- Low: polish issue

## Produce

- pass or fail summary
- issue list by demo risk
- screenshots or evidence
- a short demo path

## Closeout

End with:

- top 3 things to fix before presenting
- exact order of screens or commands to demo
- fallback plan if the primary environment fails
