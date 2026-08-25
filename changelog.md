---
title: Changelog
description: What shipped, newest first.
---

# Changelog

## 2026-08-14

- `nebula audit` gained a `--json` flag for machine-readable output.
- Fixed a build failure when `SUMMARY.md` contained Windows line endings.

## 2026-07-30

- Added the `page.deleted` webhook event.
- Personal API token lifetime raised from 30 to 90 days.

## 2026-07-02

- Scheduled publishing: `nebula publish --at <timestamp>`.
- Project settings now support `unlisted` visibility.

## 2026-06-18

- New `nebula audit --stale-after` command for finding outdated pages.
- Improved edge cache invalidation latency.
