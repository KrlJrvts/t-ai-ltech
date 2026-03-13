---
name: vue
version: 0.0.1
description: |
  Vue guidance for TalTech projects. Focus on clean component boundaries,
  composables, reactive state discipline, routing, forms, and readable
  templates.
allowed-tools:
  - Read
  - Grep
  - Glob
---

# TalTech Vue

## Architecture bias

Prefer:

- focused composables
- readable templates
- clear props and emits boundaries
- simple reactive ownership

## Vue review checklist

Review for:

- business logic buried in templates
- duplicated reactive state
- hidden mutation
- composables that are too broad

## Reactive-state rules

- keep ownership of reactive state obvious
- avoid creating multiple sources of truth
- keep composables focused on genuinely shared logic
- use watchers sparingly and deliberately

## Template and component expectations

- templates should remain readable
- event and prop contracts should be clear
- page containers should orchestrate data, not every small component

## Testing expectations

Protect:

- one key component interaction
- one loading or validation state
- one page-level user flow
