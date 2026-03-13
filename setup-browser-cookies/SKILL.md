---
name: setup-browser-cookies
version: 0.0.1
description: |
  Import cookies from installed Chromium-family browsers into the persistent
  browse session. Supports Chrome, Edge, Arc, Brave, and Comet on macOS.
allowed-tools:
  - Bash
  - Read
---

# Setup Browser Cookies

Use this before QA or demo work that needs an authenticated browser session.

## Supported desktop browsers for direct cookie import

- Chrome
- Edge
- Arc
- Brave
- Comet

Firefox is not currently supported by direct desktop-cookie import. For Firefox-targeted testing, use manual login inside the `browse` session or import a cookie file if you already have one.

## Step 1: Find browse

```bash
B=$(browse/bin/find-browse 2>/dev/null)
```

If no binary is found, stop and tell the user to run `./setup`.

## Step 2: Choose import mode

### Interactive picker

```bash
$B cookie-import-browser
```

This opens a picker UI where the user can:

- choose a detected browser
- search domains
- import selected domains
- remove imported domains

Tell the user:

`Cookie picker opened. Select the domains you want to import, then tell me when you're done.`

### Direct domain import

If the user gives a browser and domain, use:

```bash
$B cookie-import-browser edge --domain github.com
```

## Step 3: Verify

After import, run:

```bash
$B cookies
```

Summarize the imported domains and counts for the user.

## Notes

- On macOS the first import may trigger a Keychain prompt.
- Cookie values are not shown in the picker UI.
- Imported cookies are immediately available in the current browse session.
