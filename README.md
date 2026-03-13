# T-AI-LTech

**A standalone, agent-neutral engineering stack for TalTech university projects.**

This repository is structured so Codex, Claude Code, Junie, or another coding agent can all work from the same top-level instructions and the same course-specific skill folders.

## Top-level files

- [AGENTS.md](./AGENTS.md)
- [CODEX.md](./CODEX.md)
- [CLAUDE.md](./CLAUDE.md)
- [JUNIE.md](./JUNIE.md)
- [STACK.md](./STACK.md)
- [CURRICULUM.md](./CURRICULUM.md)

## Workflow skill folders

- `intake`
- `plan`
- `build`
- `code-quality`
- `deploy`
- `demo`
- `submit`

## Language skill folders

- `java`
- `python`
- `php-web`
- `csharp`
- `javascript`

## Frontend framework skill folders

- `react`
- `vue`
- `angular`

## Curriculum topic skill folders

- `computers`
- `web-tech`
- `databases`
- `algorithms`
- `networking`
- `operating-systems`
- `testing`
- `containers`
- `mobile`
- `mathematics`
- `general-studies`
- `internship`
- `thesis`

## What this stack optimizes for

- code quality
- conventional architecture
- TalTech course fit
- runnable projects
- defendable demos
- clean submission artifacts

## Setup

```bash
./setup
```

The setup script builds the browser runtime and, when installed in a `skills/` directory, symlinks every folder that contains a `SKILL.md`.

## Core runtime

The repo still keeps:

- `browse/` for browser automation
- `qa/` for structured QA
- `review/` for general bug/risk review

Those remain useful, but the primary workflow should start from the course-specific folders listed above.
