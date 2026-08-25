---
title: Authentication
description: API tokens, scopes, and request signing.
---

# Authentication

## API tokens

Create a token under **Settings → API tokens**. Pass it as a bearer token:

```http
Authorization: Bearer nb_live_...
```

## Token expiry

Tokens are issued with a fixed lifetime. When a token **expires**, requests
using it return `401 Unauthorized` with `code: "token_expired"`.

| Token type | Lifetime | Renewable |
|---|---|---|
| Personal | 90 days | Yes, from the dashboard. |
| Service | 1 year | Yes, via rotation. |
| Temporary | 1 hour | No — request a new one. |

Rotate a token before it expires to avoid downtime. Expired tokens cannot be
revived; issue a new one.

## Scopes

| Scope | Grants |
|---|---|
| `pages:read` | Read page metadata and content. |
| `pages:write` | Create, update, unpublish pages. |
| `projects:admin` | Manage project settings and webhooks. |

## Webhook signatures

Webhook requests are signed with your endpoint's signing secret using
HMAC-SHA256 over the raw request body.
