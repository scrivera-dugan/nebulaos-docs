---
title: Core concepts
description: Pages, spaces, projects, and the states a page moves through.
---

# Core concepts

## Projects, spaces, and pages

A **project** is what your readers visit. Each project contains one or more
**spaces**, and each space contains **pages**. A page is a single Markdown
file plus its frontmatter.

## Page states

Every page is in exactly one state:

| State | Meaning | Visible to readers |
|---|---|---|
| `draft` | Being written. Not built into the project. | No |
| `in_review` | Submitted for review by a maintainer. | No |
| `published` | Live on the project. | Yes |
| `unpublished` | Manually removed from the project. Content retained. | No |

A page moves `draft` → `in_review` → `published`. Once published, a page
remains in the `published` state until an author explicitly unpublishes it.

## Ownership

Each page has an owner, set at creation and changeable by any maintainer.
The owner receives notifications about review requests and broken links.
