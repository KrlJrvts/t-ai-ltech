---
name: csharp
version: 0.0.1
description: |
  Guidance for TalTech C# and ASP.NET coursework. Focus on conventional
  structure, maintainable services, clear HTTP boundaries, testing, and simple
  deployment.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech C#

## Default stack bias

Prefer:

- ASP.NET Core
- clear MVC or Web API structure
- xUnit or NUnit
- simple, explicit dependency boundaries

## Structure standard

Prefer:

- controllers that stay thin
- services that hold business rules
- request and response models where API boundaries matter
- data access that is explicit enough to reason about

## Data and validation rules

- validate input explicitly
- avoid pushing business rules into controllers
- avoid broad services with mixed responsibilities
- keep entity and DTO roles clear

## Testing expectations

Protect:

- one critical controller or endpoint path
- business logic in the service layer
- one validation or failure branch

## Review checklist

Review for:

- over-abstracted service layers
- controller bloat
- brittle entity mappings
- missing test coverage on the main flow
- DI used for ceremony rather than clarity
- exception handling that leaks internal failures badly
