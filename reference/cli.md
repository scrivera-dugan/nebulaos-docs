---
title: CLI reference
description: Every larkspur command and its flags.
---

# CLI reference

## `larkspur init`

Scaffold a new site in the current directory.

## `larkspur dev`

Serve the site locally with hot reload on `http://localhost:4400`.

| Flag | Default | Description |
|---|---|---|
| `--port` | `4400` | Port to listen on. |
| `--open` | `false` | Open a browser on start. |

## `larkspur publish`

Build and deploy the site.

| Flag | Default | Description |
|---|---|---|
| `--site` | current | Site to publish to. |
| `--at` | now | Schedule the publish for an ISO 8601 timestamp. |
| `--dry-run` | `false` | Build without deploying. |

## `larkspur unpublish`

Remove a published page from the site. Content is retained.

```bash
larkspur unpublish <page-id>
```

## `larkspur audit`

Report pages that may need attention.

| Flag | Default | Description |
|---|---|---|
| `--stale-after` | `180d` | Flag pages not edited within this window. |
| `--json` | `false` | Emit machine-readable output. |

## `larkspur cache purge`

Invalidate edge cache entries. See [Caching](../guides/caching.md).
