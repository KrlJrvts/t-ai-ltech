---
name: retro
version: 0.0.1
description: |
  Generate a project retrospective from git history. Focus on work patterns,
  delivery quality, testing discipline, hotspots, and what should improve in
  the next study sprint.
allowed-tools:
  - Bash
  - Read
  - Write
  - Glob
---

# Retro

Generate a retrospective for a TalTech project, study sprint, or team work period.

## Goal

Explain:

- what was shipped
- where time went
- which files or areas churned most
- how testing and code quality looked
- what to keep doing
- what to change next

## Default window

Use the last 7 days unless the user specifies another period such as:

- `24h`
- `14d`
- `30d`

## Data to collect

Use git history to determine:

- commits
- contributors
- changed files
- hotspots
- rough test-to-production ratio
- session patterns based on commit timing

Use the local timezone unless the user requests a different one explicitly.

## Output sections

- summary metrics
- contributor breakdown
- hotspot files
- testing discipline
- strongest delivery
- risks or weak spots
- praise
- next-sprint improvements

## Tone

Be concrete.
Avoid startup hype.
Anchor conclusions in actual commit data.
