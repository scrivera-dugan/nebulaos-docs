---
title: Core concepts
description: Pages, spaces, sites, and the states a page moves through.
---

# Core concepts

## Sites, spaces, and pages

A **site** is what your readers visit. Each site contains one or more
**spaces**, and each space contains **pages**. A page is a single Markdown
file plus its frontmatter.

## Page states

Every page is in exactly one state:

| State | Meaning | Visible to readers |
|---|---|---|
| `draft` | Being written. Not built into the site. | No |
| `in_review` | Submitted for review by a maintainer. | No |
| `published` | Live on the site. | Yes |
| `unpublished` | Manually removed from the site. Content retained. | No |

A page moves `draft` → `in_review` → `published`. Once published, a page
remains in the `published` state until an author explicitly unpublishes it.

## Ownership

Each page has an owner, set at creation and changeable by any maintainer.
The owner receives notifications about review requests and broken links.
