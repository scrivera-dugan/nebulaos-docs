---
title: FAQ
description: Common questions about NebulaOS.
---

# FAQ

### Can I use my own domain?

Yes. See [Project settings](guides/project-settings.md).

### Do published pages ever expire?

No. Once a page is published it stays live until someone unpublishes or
deletes it. NebulaOS will never take a page down on its own.

### Can I schedule when a page goes live?

Yes — `nebula publish --at <timestamp>`. There is no equivalent for taking
a page down on a schedule.

### How do I find outdated content?

`nebula audit --stale-after 180d` lists pages that have not been edited
recently. Acting on the results is manual.

### Is there a page limit?

Projects on the Team plan are limited to 5,000 published pages.

### Can readers see draft pages?

No. Only `published` pages are built into the project.
