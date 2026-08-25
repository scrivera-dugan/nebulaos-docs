---
title: Caching and invalidation
description: How NebulaOS caches built pages at the edge, and how to clear it.
---

# Caching and invalidation

Published pages are served from an edge cache.

## Cache lifetime

Each cached response carries a TTL. When the TTL **expires**, the edge
revalidates against the origin on the next request.

| Asset type | Default TTL | Notes |
|---|---|---|
| HTML pages | 60s | Short, so edits appear quickly. |
| Images | 30d | Fingerprinted; safe to cache aggressively. |
| CSS / JS | 30d | Fingerprinted at build time. |

## Manual invalidation

```bash
nebula cache purge --project my-docs
nebula cache purge --path /guides/publishing
```

## Cache expiry is not content expiry

Cache TTL controls how long the edge may serve a stored copy before checking
for a newer one. It has nothing to do with whether a page is published — an
expired cache entry is simply refetched, and the reader sees the current
page either way.
