# Browser Runtime

This document describes the `browse` runtime used by T-AI-LTech.

## What it is

`browse` is a compiled CLI that talks to a persistent Playwright-backed browser server over localhost.

It is used for:

- QA passes
- demo verification
- screenshots
- smoke testing
- login/session reuse
- browser-based debugging

## Browser engines

The runtime can launch different engines through `BROWSE_BROWSER`.

Supported values:

- `chromium` - default
- `chrome` - Playwright Chromium with the Chrome channel
- `edge` - Playwright Chromium with the Edge channel
- `firefox` - Playwright Firefox

Example:

```bash
BROWSE_BROWSER=firefox ./setup
BROWSE_BROWSER=firefox browse goto https://example.com
```

## Important compatibility note

The runtime itself can launch Chromium, Chrome, Edge, or Firefox.

Cookie import from a real desktop browser is currently limited to Chromium-family browsers:

- Chrome
- Edge
- Arc
- Brave
- Comet

Firefox sessions are still testable, but authenticated Firefox flows currently require:

- manual login in the `browse` session, or
- importing cookies from a file if you already have them in supported format

## Runtime model

`browse` uses a daemon model:

1. CLI command starts or connects to the local server
2. server launches the selected Playwright browser
3. commands run against the persistent session
4. cookies, tabs, and state persist between commands
5. the server shuts down after idle timeout

## Command groups

| Group | Commands |
| --- | --- |
| Navigation | `goto`, `back`, `forward`, `reload`, `url` |
| Read | `text`, `html`, `links`, `forms`, `accessibility` |
| Interaction | `click`, `fill`, `select`, `hover`, `type`, `press`, `scroll`, `wait`, `viewport`, `upload` |
| Assertions | `is`, `css`, `attrs`, `js`, `eval` |
| Debug | `console`, `network`, `dialog`, `cookies`, `storage`, `perf` |
| Visual | `snapshot`, `screenshot`, `pdf`, `responsive` |
| Session | `cookie-import`, `cookie-import-browser`, `header`, `useragent` |
| Tabs | `tabs`, `tab`, `newtab`, `closetab` |
| Meta | `status`, `stop`, `restart`, `chain`, `diff` |

## Finding the binary

Use:

```bash
browse/bin/find-browse
```

That helper prefers:

1. the local repo build
2. a project-local skills install
3. a user-level skills install

It no longer depends on a hardcoded parent folder name.

## Setup

```bash
./setup
```

Optional browser selection:

```bash
BROWSE_BROWSER=chromium ./setup
BROWSE_BROWSER=chrome ./setup
BROWSE_BROWSER=edge ./setup
BROWSE_BROWSER=firefox ./setup
```

What `setup` does:

- ensures Bun is available
- installs dependencies
- builds `browse/dist/browse`
- installs the selected Playwright browser support
- validates that the selected browser launches
- registers any skill folders if the repo is installed inside a skills directory

## Core usage patterns

### Smoke-check a page

```bash
B=$(browse/bin/find-browse)
$B goto https://example.com
$B text
$B console --errors
$B is visible "body"
```

### Test a user flow

```bash
$B goto https://example.com/login
$B snapshot -i
$B fill @e3 "user@example.com"
$B fill @e4 "password"
$B click @e5
$B snapshot -D
```

### Check responsiveness

```bash
$B responsive /tmp/example-layout
```

### Collect evidence

```bash
$B snapshot -i -a -o /tmp/annotated.png
$B screenshot /tmp/plain.png
$B console
```

## Snapshot system

`snapshot` is the main interaction primitive.

Important flags:

- `-i` interactive elements only
- `-c` compact output
- `-d N` depth limit
- `-s <selector>` scope to subtree
- `-D` diff against previous snapshot
- `-a` annotated screenshot with refs
- `-o <path>` output path
- `-C` cursor-interactive element scan

Refs produced by snapshots can be reused:

- `@eN` for accessible interactive elements
- `@cN` for cursor-interactive elements that the accessibility tree misses

## State persistence

Within a live server session, `browse` persists:

- cookies
- local storage
- tabs
- session state
- last snapshot baseline

This is why it is useful for QA and demos rather than single isolated browser calls.

## Environment variables

| Variable | Purpose |
| --- | --- |
| `BROWSE_BROWSER` | Browser engine: `chromium`, `chrome`, `edge`, `firefox` |
| `BROWSE_PORT` | Fixed browse server port |
| `CONDUCTOR_PORT` | Workspace-derived browse port |
| `BROWSE_IDLE_TIMEOUT` | Idle shutdown timeout in milliseconds |
| `BROWSE_STATE_FILE` | State file location |
| `BROWSE_SERVER_SCRIPT` | Override server script path |

## Notes for agents

- Use the `browse` CLI instead of Chrome MCP-style tools.
- Prefer `snapshot -i` before interacting.
- Use `snapshot -D` after important actions.
- For Firefox coverage, set `BROWSE_BROWSER=firefox` before launching the session.
- For Chrome/Edge-specific checks, use the corresponding browser setting before launching the session.
