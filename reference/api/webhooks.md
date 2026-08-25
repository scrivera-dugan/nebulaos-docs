---
title: Webhooks
description: Subscribe to page and site events.
---

# Webhooks

Register an endpoint under **Settings → Webhooks**. Larkspur POSTs a JSON
payload for each subscribed event.

## Event payload

```json
{
  "event": "page.published",
  "sent_at": "2026-08-01T12:00:00Z",
  "data": { "page_id": "pg_9c2f1a", "site_id": "st_41bd" }
}
```

## Events

| Event | Fires when |
|---|---|
| `page.created` | A new page is created in any state. |
| `page.published` | A page transitions to `published`. |
| `page.unpublished` | A page is manually unpublished. |
| `page.deleted` | A page is permanently removed. |
| `site.deployed` | A site build finishes successfully. |

## Retries

Failed deliveries retry with exponential backoff for up to 24 hours. A
delivery is considered failed if your endpoint does not return a 2xx within
10 seconds.

## Verifying signatures

Each request carries an `X-Larkspur-Signature` header. See
[Authentication](authentication.md).
