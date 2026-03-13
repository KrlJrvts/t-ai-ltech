---
name: java
version: 0.0.1
description: |
  Guidance for TalTech Java coursework and Java web projects. Focus on
  conventional Spring Boot structure, explicit boundaries, testing, data flow,
  and maintainable backend code that a student can defend.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech Java

## Default stack bias

Prefer:

- Spring Boot
- Maven or Gradle
- clear controller/service/repository boundaries
- JUnit tests on business logic
- simple SQL persistence

## Project structure standard

Prefer a structure where responsibilities are obvious:

- controllers for request mapping and HTTP concerns
- services for business logic
- repositories or data access for persistence
- DTOs or request models for API boundaries
- configuration kept minimal and explicit

Avoid hiding business logic inside controllers or entity classes.

## Data and validation rules

- validate requests explicitly
- keep entity boundaries clear
- avoid exposing persistence models directly when the API shape differs
- keep transaction boundaries deliberate

## Testing expectations

At minimum, protect:

- core business logic
- one persistence boundary
- one request or controller path
- one validation failure

## Review checklist

Review for:

- oversized services
- weak validation
- hidden transaction issues
- poor DTO or entity boundaries
- controller bloat
- repository methods that encode too much business logic
- fragile exception handling

## Anti-patterns

- too many service layers for simple coursework
- magic annotations with no explanation
- heavy framework customizations the student cannot explain
- exposing entities directly when it leaks persistence concerns
