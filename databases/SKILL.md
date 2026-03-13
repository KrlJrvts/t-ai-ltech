---
name: databases
version: 0.0.1
description: |
  Guidance for TalTech database work. Focus on schema design, queries,
  migrations, integrity, indexing, and keeping persistence logic understandable.
allowed-tools:
  - Read
  - Grep
  - Glob
---

# TalTech Databases

## Focus areas

- clear schema design
- key constraints and relations
- query correctness
- migration safety
- keeping ORM usage understandable

## Data-modeling expectations

- identify primary entities clearly
- define relations deliberately
- keep nullability meaningful
- avoid storing derived values unless justified

## Review checklist

Review for:

- data integrity issues
- bad joins
- missing indexes on obvious hot paths
- confusing ownership of persistence logic
- ORM use that hides important query behavior
- migrations that are hard to reason about

## Expected output

Good guidance or review should include:

- the entity or table model being assumed
- the constraint or relationship that matters
- where integrity can break
- the safest correction or schema adjustment
