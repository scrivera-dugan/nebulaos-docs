---
title: Pages API
description: Create, read, update, and unpublish pages over HTTP.
---

# Pages API

Base URL: `https://api.larkspur.dev/v1`

## The page object

```json
{
  "id": "pg_9c2f1a",
  "site_id": "st_41bd",
  "title": "Quickstart",
  "path": "/getting-started/quickstart",
  "state": "published",
  "owner": "docs-team",
  "created_at": "2026-02-11T09:14:00Z",
  "updated_at": "2026-07-30T16:02:11Z",
  "published_at": "2026-02-12T10:00:00Z"
}
```

| Field | Type | Description |
|---|---|---|
| `id` | string | Unique page identifier. |
| `state` | enum | `draft`, `in_review`, `published`, `unpublished`. |
| `owner` | string | Team or user handle. |
| `published_at` | timestamp | When the page went live. `null` if never published. |

## List pages

```http
GET /sites/{site_id}/pages?state=published
```

## Update a page

```http
PATCH /pages/{page_id}
```

Accepts `title`, `owner`, and `state`.

## Unpublish a page

```http
POST /pages/{page_id}/unpublish
```

Sets `state` to `unpublished`. The page stops being served immediately. Its
content is retained and it can be republished with `POST /pages/{id}/publish`.
