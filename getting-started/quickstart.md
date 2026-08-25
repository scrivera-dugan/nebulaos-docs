---
title: Quickstart
description: Publish your first Larkspur site in about five minutes.
---

# Quickstart

This guide takes you from an empty directory to a published documentation site.

## 1. Install the CLI

```bash
npm install -g @larkspur/cli
larkspur login
```

## 2. Create a site

```bash
larkspur init my-docs
cd my-docs
```

This scaffolds a `larkspur.yaml`, a `SUMMARY.md`, and a starter page.

## 3. Write a page

Every page is Markdown with frontmatter:

```markdown
---
title: Hello
description: My first page.
---

# Hello

Welcome to my docs.
```

## 4. Publish

```bash
larkspur publish
```

Your site is live at `https://<your-site>.larkspur.dev`. Once a page is
published it stays available at its URL until you unpublish or delete it.

## Next steps

- [Core concepts](core-concepts.md) explains how pages, spaces, and sites relate.
- [Content lifecycle](../guides/content-lifecycle.md) covers drafts and review.
