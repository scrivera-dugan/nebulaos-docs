---
title: Content lifecycle
description: How pages are created, reviewed, published, and retired.
---

# Content lifecycle

## Creation and review

New pages start as drafts. When an author is ready, they submit the page for
review. A maintainer approves or requests changes.

## Publication

Approved pages are published on the next site build.

## After publication

**Published pages remain published indefinitely.** Larkspur does not remove
content on its own — a page stays live at its URL until a human unpublishes
or deletes it. This is deliberate: readers frequently arrive from bookmarks
and external links, and silently removing pages breaks those paths.

Teams that need to retire content on a schedule usually handle it with a
recurring calendar reminder and a manual audit.

## Retiring a page

To take a page down:

```bash
larkspur unpublish <page-id>
```

The content is retained and can be republished later. To remove it
permanently, use `larkspur delete`.

## Auditing stale content

Run a content audit to list pages that have not been edited recently:

```bash
larkspur audit --stale-after 180d
```

This reports candidates for review. It does not change anything — acting on
the report is a manual step.
