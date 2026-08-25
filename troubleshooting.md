---
title: Troubleshooting
description: Fixes for the problems support sees most often.
---

# Troubleshooting

## My page isn't showing up

Check that it is listed in `SUMMARY.md`. Pages not in the summary are
excluded from the build.

## My edit isn't live yet

HTML responses are cached for 60 seconds at the edge. Wait a minute, or run
`nebula cache purge --path /your/page`.

## A page I expected to be live is missing

Check the page's state with `GET /pages/{id}`. If it shows `unpublished`,
someone removed it manually — check the project audit log under
**Settings → Activity**.

## Build fails with "missing frontmatter"

Every page needs `title` and `description`. Run `nebula lint` locally.

## 401 on API calls

Your token may have expired. See [Authentication](reference/api/authentication.md).
