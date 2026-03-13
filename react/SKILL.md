---
name: react
version: 0.0.1
description: |
  React guidance for TalTech projects. Focus on component boundaries, state
  ownership, effects discipline, routing, forms, and code that stays teachable.
allowed-tools:
  - Read
  - Grep
  - Glob
---

# TalTech React

## Architecture bias

Prefer:

- local state by default
- small composable components
- explicit data flow
- minimal global state

## React review checklist

Review for:

- unnecessary effects
- derived state bugs
- oversized components
- context or store overuse

## State and effects rules

- keep state close to where it is used
- derive values during render when state is unnecessary
- use effects for external synchronization, not ordinary computation
- avoid context for data that only two or three levels need

## UI structure expectations

- keep forms explicit
- keep loading and error states visible
- separate page-level orchestration from reusable UI pieces

## Testing expectations

Protect:

- one important user interaction
- one loading or error state
- one page-level happy path
