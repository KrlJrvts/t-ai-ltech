---
name: operating-systems
version: 0.0.1
description: |
  Guidance for TalTech operating systems work. Focus on processes, files,
  permissions, services, environment setup, process lifecycle, and debugging
  runtime issues.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech Operating Systems

## Focus areas

- process and service behavior
- filesystems and permissions
- environment variables
- shell and process debugging
- how OS behavior affects application runtime

## Expectations

- explain runtime behavior in terms of processes, files, and permissions
- make setup reproducible
- avoid hidden shell assumptions

## Review checklist

Review for:

- incorrect permission assumptions
- brittle shell commands
- environment variables that are required but undocumented
- startup or service behavior that is hard to reproduce

Prefer explicit setup steps and reproducible local environments.

## Expected output

Good guidance should describe:

- which process or service is involved
- which file, path, or permission matters
- how the environment is configured
- how to reproduce and verify the fix
