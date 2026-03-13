---
name: containers
version: 0.0.1
description: |
  Guidance for TalTech container-based deployment work. Focus on Docker,
  container config, service boundaries, and environments that students can
  actually explain and operate.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech Containers

## Focus areas

- simple Dockerfiles
- clear service boundaries
- environment configuration
- database and app startup order
- explainable deployment steps

## Expectations

- keep images simple
- separate build-time and runtime concerns
- document ports, volumes, and env vars
- explain how services discover each other

## Review checklist

Review for:

- oversized or confused Dockerfiles
- hidden runtime assumptions
- container orchestration that is too complex for the course
- startup ordering or health-check issues

Avoid container complexity that does not help the assignment.

## Expected output

Good guidance should include:

- image and service boundaries
- build and run commands
- environment variables and secrets handling
- persistent storage assumptions
