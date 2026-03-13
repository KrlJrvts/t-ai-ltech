---
name: angular
version: 0.0.1
description: |
  Angular guidance for TalTech projects. Focus on understandable RxJS usage,
  service boundaries, component structure, routing, and stable forms.
allowed-tools:
  - Read
  - Grep
  - Glob
---

# TalTech Angular

## Architecture bias

Prefer:

- clear service and component boundaries
- conventional Angular structure
- reactive flows that are easy to reason about
- forms that are explicit and testable

## Angular review checklist

Review for:

- subscription leaks
- giant shared services
- component bloat
- template logic that should live in code

## RxJS and service rules

- keep observable chains readable
- avoid service classes that become dumping grounds
- keep transformation logic named and isolated
- make subscription ownership explicit

## Component and form expectations

- forms should be explicit and testable
- page components should coordinate, not absorb all business logic
- template logic should stay simple

## Testing expectations

Protect:

- one service-level logic path
- one form validation path
- one routed user flow
