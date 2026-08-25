---
title: CLI reference
description: Every nebula command and its flags.
---

# CLI reference

## `nebula init`

Scaffold a new project in the current directory.

## `nebula dev`

Serve the project locally with hot reload on `http://localhost:4400`.

| Flag | Default | Description |
|---|---|---|
| `--port` | `4400` | Port to listen on. |
| `--open` | `false` | Open a browser on start. |

## `nebula publish`

Build and deploy the project.

| Flag | Default | Description |
|---|---|---|
| `--project` | current | Project to publish to. |
| `--at` | now | Schedule the publish for an ISO 8601 timestamp. |
| `--dry-run` | `false` | Build without deploying. |

## `nebula unpublish`

Remove a published page from the project. Content is retained.

```bash
nebula unpublish <page-id>
```

## `nebula audit`

Report pages that may need attention.

| Flag | Default | Description |
|---|---|---|
| `--stale-after` | `180d` | Flag pages not edited within this window. |
| `--json` | `false` | Emit machine-readable output. |

## `nebula cache purge`

Invalidate edge cache entries. See [Caching](../guides/caching.md).
