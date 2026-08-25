---
title: FAQ
description: Common questions about Larkspur.
---

# FAQ

### Can I use my own domain?

Yes. See [Site settings](guides/site-settings.md).

### Do published pages ever expire?

No. Once a page is published it stays live until someone unpublishes or
deletes it. Larkspur will never take a page down on its own.

### Can I schedule when a page goes live?

Yes — `larkspur publish --at <timestamp>`. There is no equivalent for taking
a page down on a schedule.

### How do I find outdated content?

`larkspur audit --stale-after 180d` lists pages that have not been edited
recently. Acting on the results is manual.

### Is there a page limit?

Sites on the Team plan are limited to 5,000 published pages.

### Can readers see draft pages?

No. Only `published` pages are built into the site.
