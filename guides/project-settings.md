---
title: Project settings
description: Configure visibility, domains, and defaults for a project.
---

# Project settings

Settings live under **Project → Settings** in the dashboard, or in
`nebula.yaml` for teams who prefer config-as-code.

## Visibility

| Setting | Description |
|---|---|
| `public` | Anyone with the URL can read the project. |
| `unlisted` | Reachable by URL, excluded from search engines. |
| `private` | Requires authentication. |

## Custom domain

Simply point a `CNAME` at `projects.nebulaos.dev`, then add the domain under
**Settings → Domain**.

## Content defaults

| Setting | Default | Description |
|---|---|---|
| `default_owner` | Project creator | Owner assigned to newly created pages. |
| `review_required` | `true` | Require approval before publishing. |
| `stale_after` | `180d` | Age at which `nebula audit` flags a page. |

Content defaults apply to pages created after the setting is changed;
existing pages keep their current values.
