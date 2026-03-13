---
name: php-web
version: 0.0.1
description: |
  Guidance for TalTech web development work in PHP. Focus on boring structure,
  request handling, validation, database hygiene, and code the student can
  explain without hand-waving.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech PHP Web

## Default stack bias

Prefer:

- Laravel when framework use is allowed
- otherwise explicit routing, validation, rendering, and data access layers
- prepared statements or ORM defaults instead of raw unsafe queries
- clear env and setup docs

## Structure standard

Do not mix these carelessly:

- routing
- request validation
- business logic
- HTML rendering
- data access

If using plain PHP, keep the boundaries explicit even without a framework.

## Security and data rules

- validate request input explicitly
- escape output where relevant
- avoid inline unsafe SQL
- do not keep secrets or connection details in tracked files

## Testing expectations

At minimum, cover:

- the main submission flow
- one validation failure
- one data or persistence boundary

## Review checklist

Review for:

- mixed HTML, SQL, and business logic
- missing validation
- weak database boundaries
- deployment assumptions that only work locally
- hidden routing behavior
- duplicated request handling code
- brittle form or session logic
