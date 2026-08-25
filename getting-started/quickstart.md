---
title: Quickstart
description: Publish your first NebulaOS project in about five minutes.
---

# Quickstart

This guide takes you from an empty directory to a published documentation project.

## 1. Install the CLI

```bash
npm install -g @nebulaos/cli
nebula login
```

## 2. Create a project

```bash
nebula init my-docs
cd my-docs
```

That's it — the scaffold is ready to edit.

This scaffolds a `nebula.yaml`, a `SUMMARY.md`, and a starter page.

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

When the pages look right, just publish:

```bash
nebula publish
```

Your project is live at `https://<your-project>.nebulaos.dev`. Once a page is
published it stays available at its URL until you unpublish or delete it.

## Next steps

- [Core concepts](core-concepts.md) explains how pages, spaces, and projects relate.
- [Content lifecycle](../guides/content-lifecycle.md) covers drafts and review.
