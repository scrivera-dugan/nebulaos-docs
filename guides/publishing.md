---
title: Publishing a project
description: How content gets from your working branch to your readers.
---

# Publishing a project

## The publish flow

1. Write or edit pages on a branch.
2. Open a change request.
3. A maintainer reviews and merges.
4. NebulaOS builds the project and deploys it.

## Publishing from the CLI

Simply run the publish command and NebulaOS handles the build:

```bash
nebula publish --project my-docs
```

## What gets published

Only pages listed in `SUMMARY.md` are built. A page that exists on disk but
is missing from the summary is ignored by the builder — a common cause of
"my page isn't showing up."

## Scheduling

You can schedule a publish for a future time — just pass a timestamp:

```bash
nebula publish --at "2026-09-01T09:00:00Z"
```

Scheduling controls when a page *appears*. There is currently no
corresponding control for when a page comes down; to remove a page you
unpublish it manually.
