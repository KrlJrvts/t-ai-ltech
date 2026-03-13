---
name: deploy
version: 0.0.1
description: |
  Choose the simplest viable deployment or demo setup for a TalTech project,
  verify the main flow, document the fallback path, and avoid infrastructure
  choices that are too complex for coursework.
allowed-tools:
  - Bash
  - Read
  - Write
  - Edit
  - Grep
  - Glob
---

# TalTech Deploy

Choose the simplest deployment story that fits the assignment.

## Deployment selection order

Prefer in this order:

1. local-only demo if the assignment does not require hosting
2. static hosting for static frontends
3. managed frontend hosting for SPA or SSR apps
4. managed app hosting for server-side apps
5. container platform only when the course explicitly expects it

## Platform bias

Typical safe choices:

- GitHub Pages for static sites
- Netlify or Vercel for frontend-heavy projects
- Render or Railway for simple full-stack projects
- Docker or OpenShift only when the course calls for container deployment

## Required deployment review

- build command
- start command
- required env vars
- database or state needs
- public URL or local fallback
- smoke-test path
- rollback or demo fallback

## Pre-flight checklist

Before calling the deployment ready, confirm:

- dependencies install from a clean checkout
- production build actually succeeds
- startup does not depend on undocumented local state
- seed data or demo data is available when needed
- the main path works in the deployed or demo environment

## Required output

Always provide:

### 1. Deployment recommendation

Name the platform and explain why it is the right tradeoff.

### 2. Required configuration

List:

- build command
- runtime command
- environment variables
- database or storage setup
- domain or public URL if relevant

### 3. Gaps blocking deployment

Be explicit about missing pieces.

### 4. Smoke-test checklist

List the small set of checks that must pass before demo or submission.

### 5. Rollback or fallback plan

Explain what the student should do if the deployment breaks shortly before demo.

## Review standard

Prefer teachable platforms and boring infrastructure.
If the infrastructure looks harder than the assignment itself, challenge it.
