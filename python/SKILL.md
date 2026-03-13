---
name: python
version: 0.0.1
description: |
  Guidance for TalTech Python work including APIs, scripting, automation, and
  practical coursework. Focus on explicit structure, environments, packaging,
  data handling, and tests.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech Python

## Default stack bias

Prefer:

- FastAPI or Flask for web/API work
- explicit virtual environment setup
- pytest
- clear package structure
- standard library first when enough

## Environment and packaging standard

- document environment creation clearly
- keep dependency files minimal and accurate
- avoid hidden machine-specific assumptions
- prefer importable modules over random scripts when the codebase grows

## API and application rules

- keep request validation explicit
- separate transport concerns from business logic
- keep data models understandable
- avoid global mutable state unless the problem genuinely requires it

## Testing expectations

Protect:

- core transformations or calculations
- one API or CLI entry path
- one important failure path
- data parsing or persistence behavior

## Review checklist

Review for:

- hidden environment assumptions
- weak packaging
- script sprawl
- missing tests around data handling
- broad utility modules with mixed concerns
- implicit side effects at import time
- fragile file-path assumptions
