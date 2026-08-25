---
title: Site settings
description: Configure visibility, domains, and defaults for a site.
---

# Site settings

Settings live under **Site → Settings** in the dashboard, or in
`larkspur.yaml` for teams who prefer config-as-code.

## Visibility

| Setting | Description |
|---|---|
| `public` | Anyone with the URL can read the site. |
| `unlisted` | Reachable by URL, excluded from search engines. |
| `private` | Requires authentication. |

## Custom domain

Point a `CNAME` at `sites.larkspur.dev`, then add the domain under
**Settings → Domain**.

## Content defaults

| Setting | Default | Description |
|---|---|---|
| `default_owner` | Site creator | Owner assigned to newly created pages. |
| `review_required` | `true` | Require approval before publishing. |
| `stale_after` | `180d` | Age at which `larkspur audit` flags a page. |

Content defaults apply to pages created after the setting is changed;
existing pages keep their current values.
