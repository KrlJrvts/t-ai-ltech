# T-AI-LTech

This repository is a top-level, agent-neutral engineering workspace for TalTech `IADB17` IT Systems Development work.

Use these instructions with Codex, Claude Code, Junie, or any other coding agent that can read repository files.

## Mission

Build student projects that are:

- aligned with the TalTech curriculum
- correct and maintainable
- easy to explain during a demo or defense
- runnable from a clean checkout
- testable and reviewable
- deployable when the assignment expects it
- documented to grading standard

## Working rules

- Prefer teachable solutions over clever ones.
- Prefer conventional structure over custom architecture.
- Prefer one strong vertical slice over many unfinished features.
- Prefer code quality over superficial feature count.
- Respect the existing repository unless it is clearly the wrong foundation.

## Default stack rules

- Java: Spring Boot, Maven or Gradle, JUnit, simple SQL persistence
- Python: FastAPI or Flask, pytest, venv or uv, simple SQL persistence
- PHP: Laravel when appropriate, otherwise explicit clean PHP structure
- C#: ASP.NET Core, xUnit or NUnit, simple data layer
- JavaScript frontend: React, Vue, or Angular depending on the repo or assignment

Do not introduce a framework or service that the student cannot explain under questioning.

## Required outcome for any project

Every finished project should have:

- run instructions
- test instructions
- documented environment variables
- a short architecture summary
- a demo path
- known limitations
- requirement or rubric mapping

## Top-level guides

- `CODEX.md`
- `CLAUDE.md`
- `JUNIE.md`
- `STACK.md`
- `CURRICULUM.md`

## Skill folders

Workflow skills:

- `intake/`
- `plan/`
- `build/`
- `code-quality/`
- `deploy/`
- `demo/`
- `submit/`

Language skills:

- `java/`
- `python/`
- `php-web/`
- `csharp/`
- `javascript/`

Frontend framework skills:

- `react/`
- `vue/`
- `angular/`

Curriculum topic skills:

- `computers/`
- `web-tech/`
- `databases/`
- `algorithms/`
- `networking/`
- `operating-systems/`
- `testing/`
- `containers/`
- `mobile/`
- `mathematics/`
- `general-studies/`
- `internship/`
- `thesis/`

The browser runtime and generic review tools from the base repo remain available, but the TalTech folders are the primary interface.
