T-AI-LTech — How To Run

This file explains how to use this repository as a standalone local skill stack and project workflow kit.

1. What this repository is

This repository is a local agent-support stack for TalTech university projects.

It gives you:

- top-level instructions for agents
- workflow skill folders
- language and curriculum-topic skill folders
- a local browser runtime for QA, demos, and screenshots

Main entry files:

- AGENTS.md
- CODEX.md
- CLAUDE.md
- JUNIE.md
- STACK.md
- CURRICULUM.md
- SKILL.md

2. Folder structure you will use

Workflow:

- intake
- plan
- build
- code-quality
- deploy
- demo
- submit

Languages:

- java
- python
- php-web
- csharp
- javascript

Frontend:

- react
- vue
- angular

Curriculum topics:

- computers
- web-tech
- databases
- algorithms
- networking
- operating-systems
- testing
- containers
- mobile
- mathematics
- general-studies
- internship
- thesis

3. Basic local setup

From the repository root:

```bash
./setup
```

What setup does:

- checks that Bun exists
- installs dependencies
- builds the browse binary
- installs browser support for the selected Playwright browser
- links skill folders if the repo is installed inside a skills directory

Optional browser selection:

```bash
BROWSE_BROWSER=chromium ./setup
BROWSE_BROWSER=chrome ./setup
BROWSE_BROWSER=edge ./setup
BROWSE_BROWSER=firefox ./setup
```

4. If Bun is missing

Install Bun first, then rerun setup.

Example:

```bash
curl -fsSL https://bun.sh/install | bash
```

Then restart your shell and run:

```bash
./setup
```

5. How to use the browser runtime

Find the binary:

```bash
browse/bin/find-browse
```

Example usage:

```bash
B=$(browse/bin/find-browse)
$B goto https://example.com
$B snapshot -i
$B console --errors
$B screenshot /tmp/example.png
```

Use Firefox:

```bash
BROWSE_BROWSER=firefox $B goto https://example.com
```

Note:

- cookie import from real desktop browsers currently supports Chromium-family browsers only
- Firefox can still be used for manual-login testing

6. How to use the workflow

Typical order:

1. read AGENTS.md
2. use intake for assignment analysis
3. use plan for architecture
4. use build for implementation
5. use code-quality for review
6. use deploy for deployment or demo setup
7. use demo for verification
8. use submit for final submission packaging

Examples:

- assignment brief -> intake
- architecture review -> plan
- coding task -> build
- PR review -> code-quality or review
- browser verification -> browse or qa
- final hand-in docs -> submit

7. How to use this in Codex

Open the repository in Codex.

Tell Codex to read:

- AGENTS.md
- CODEX.md
- README.md
- STACK.md
- CURRICULUM.md

Then direct it to the correct folder, for example:

- "Use build and java to implement this Spring Boot coursework task."
- "Use plan and databases to design the persistence layer."
- "Use code-quality and javascript to review this frontend."

Recommended habit:

- keep the repo open as a separate helper workspace
- keep your actual university project in its own repo or worktree
- ask Codex to apply the standards and workflow from this stack to the project repo

8. How to use this in Claude Code

If you use Claude Code with a skills directory, place this repo inside your local skills folder.

Example structure:

```text
~/.claude/skills/t-ai-ltech/
```

Then run:

```bash
cd ~/.claude/skills/t-ai-ltech
./setup
```

Claude Code can then discover folders containing SKILL.md files.

Recommended Claude flow:

- tell Claude to read AGENTS.md first
- tell it which folder skill to follow
- point it to the actual project repository you want worked on

9. How to use this in Junie

Open the repository and point Junie to:

- AGENTS.md
- JUNIE.md
- README.md

Then tell it to use the matching folder for the task.

Examples:

- "Follow intake and plan for this assignment."
- "Follow python and testing for this FastAPI project."
- "Follow submit and thesis for my final write-up."

10. How to use this in JetBrains IDEs

Works well in:

- IntelliJ IDEA
- WebStorm
- PyCharm
- PhpStorm
- Rider

Recommended approach:

1. Open this repository as a reference workspace.
2. Open your actual course project in a second window or second project.
3. Keep this stack visible for prompts, standards, and skill selection.

Useful patterns:

- IntelliJ IDEA for Java projects with `java`, `databases`, `testing`
- PyCharm for Python projects with `python`, `testing`, `deploy`
- PhpStorm for PHP/web projects with `php-web`, `web-tech`, `databases`
- WebStorm for JS frontend projects with `javascript`, `react` or `vue` or `angular`
- Rider for C# projects with `csharp`, `databases`, `testing`

11. How to use this in VS Code

Open the repository as one workspace folder.
Open your course project as another workspace folder if needed.

Recommended use:

- this repo = process, standards, prompts
- project repo = implementation target

12. Recommended daily usage

Before coding:

- read AGENTS.md
- read the relevant language folder
- read the relevant workflow folder

During coding:

- keep scope small
- keep the main demo path working
- add tests on the critical path

Before submission:

- run code-quality
- run review
- run qa or browse if there is a UI
- run submit

13. Suggested project mappings

Java backend:

- intake
- plan
- java
- databases
- testing
- deploy

Python API:

- intake
- plan
- python
- testing
- deploy

PHP web app:

- intake
- plan
- php-web
- web-tech
- databases
- deploy

C# web app:

- intake
- plan
- csharp
- databases
- testing

JavaScript frontend:

- intake
- plan
- javascript
- react or vue or angular
- web-tech
- qa
- demo

Thesis or internship:

- intake
- plan
- thesis or internship
- submit

14. Validation checklist

After setup, confirm:

```bash
cat VERSION
browse/bin/find-browse
```

If browse is found, test:

```bash
B=$(browse/bin/find-browse)
$B goto https://example.com
$B text
```

15. Known current limitations

- direct cookie import is Chromium-family only
- build and tests require Bun
- this stack gives guidance and local tooling, not project-specific code by itself

16. Best way to work with it

Do not treat this repository as your actual course project.

Treat it as:

- a standards repo
- a workflow repo
- a prompt/skill repo
- a QA browser helper repo

Then use it on top of your real project repositories.
