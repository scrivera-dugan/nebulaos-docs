---
title: Configuration
description: The larkspur.yaml file reference.
---

# Configuration

`larkspur.yaml` lives at the root of your docs repository.

```yaml
site: my-docs
visibility: public
domain: docs.example.com

content:
  default_owner: docs-team
  review_required: true
  stale_after: 180d

build:
  summary: SUMMARY.md
  ignore:
    - drafts/**
```

## `content`

| Key | Type | Default | Description |
|---|---|---|---|
| `default_owner` | string | site creator | Owner for new pages. |
| `review_required` | boolean | `true` | Require approval before publish. |
| `stale_after` | duration | `180d` | Age at which `audit` flags a page. |

## `build`

| Key | Type | Default | Description |
|---|---|---|---|
| `summary` | path | `SUMMARY.md` | Table of contents file. |
| `ignore` | glob[] | `[]` | Paths excluded from the build. |

Durations accept `d`, `h`, and `m` suffixes.
