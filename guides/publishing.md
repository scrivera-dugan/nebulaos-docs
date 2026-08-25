---
title: Publishing a site
description: How content gets from your working branch to your readers.
---

# Publishing a site

## The publish flow

1. Write or edit pages on a branch.
2. Open a change request.
3. A maintainer reviews and merges.
4. Larkspur builds the site and deploys it.

## Publishing from the CLI

```bash
larkspur publish --site my-docs
```

## What gets published

Only pages listed in `SUMMARY.md` are built. A page that exists on disk but
is missing from the summary is ignored by the builder — a common cause of
"my page isn't showing up."

## Scheduling

You can schedule a publish for a future time:

```bash
larkspur publish --at "2026-09-01T09:00:00Z"
```

Scheduling controls when a page *appears*. There is currently no
corresponding control for when a page comes down; to remove a page you
unpublish it manually.
