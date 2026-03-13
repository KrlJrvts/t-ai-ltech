---
name: submit
version: 0.0.1
description: |
  Package a TalTech project for grading with setup docs, architecture summary,
  requirement mapping, demo path, evidence, and known limitations. The goal is
  to make the grader's job easy and remove follow-up questions.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Write
  - Edit
---

# TalTech Submit

Make the grader's job easy.

## Submission standard

Assume the grader has limited time and zero hidden context.
The submission should answer immediately:

- what this project does
- how it maps to the assignment
- how to run it
- how to test it
- what to demo
- where it is limited

## Required sections

- what the project is
- how to run it
- architecture summary
- requirement or rubric mapping
- demo path
- known limitations
- future work

## Strong requirement mapping

For each requirement or rubric line, map it to:

- feature or implementation area
- proof or evidence
- file, screen, or command if relevant

If a requirement is only partially satisfied, say so directly.

## Documentation expectations

The final project docs should include:

- installation steps
- dependency list if non-obvious
- environment variables
- test command
- build command
- deploy link or local fallback
- demo order

## Final review checklist

Before calling the project submission-ready, verify:

- setup instructions are complete
- the architecture description is understandable
- the requirement mapping is explicit
- known limitations are honest
- future work is clearly separated from missing required work

If anything is unclear to a grader, fix the docs before calling it finished.
