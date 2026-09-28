# NebulaOS documentation style guide

This guide sets the rules for every page in the NebulaOS docs. It is based on
common industry practice (Google and Microsoft developer documentation style)
and trimmed to what matters for this site.

Each rule has an ID and a severity so reviewers and tools can cite it:

| Severity | Meaning |
|---|---|
| **Error** | Must be fixed before publishing. |
| **Warning** | Should be fixed unless there is a clear reason not to. |
| **Suggestion** | Improves the page; use judgment. |

---

## 1. Voice and tone

### VOICE-1: Address the reader as "you" — Warning

Write in second person. Don't use "we" to mean NebulaOS, and don't use "the
user" when you mean the reader.

- ✅ You can schedule a publish for a future time.
- ❌ The user can schedule a publish for a future time.

### VOICE-2: Use active voice and present tense — Warning

Say who does what, as it happens now. Avoid "will" for normal product
behavior.

- ✅ NebulaOS builds the project and deploys it.
- ❌ The project will be built and deployed.

### VOICE-3: Don't minimize difficulty — Error

Never use words that tell the reader a task is easy. If the reader struggles,
these words make them feel at fault, and they add nothing when the task
really is easy.

Banned: **simply**, **just**, **easy**, **easily**, **obviously**, **of
course**, **straightforward**, **that's it**.

- ✅ Run the publish command:
- ❌ Simply run the publish command:
- ❌ When the pages look right, just publish:

### VOICE-4: Avoid time-relative language — Warning

Don't use words that go stale: **currently**, **now**, **new**, **soon**,
**at the moment**, **as of this writing**. Describe how the product works;
put history in the [Changelog](changelog.md).

- ✅ There is no control for when a page comes down.
- ❌ There is currently no control for when a page comes down.

### VOICE-5: Be direct and concise — Suggestion

Cut filler (**please**, **in order to**, **basically**, **note that**). Keep
sentences under about 25 words. One idea per sentence.

---

## 2. Terminology

Use NebulaOS product terms exactly and consistently. A reader who sees two
words assumes they mean two different things.

### TERM-1: Use the approved product terms — Error

| Use | Don't use | Notes |
|---|---|---|
| project | site, docs site | The thing readers visit. |
| space | section, book | A container of pages inside a project. |
| page | doc, article, document | A single Markdown file plus frontmatter. |
| maintainer | reviewer, approver | The role that approves and publishes. |
| change request | pull request, PR, merge request | When referring to NebulaOS itself. Git terms are fine when talking about Git. |
| unpublish | take down, remove, hide | For changing a page to the `unpublished` state. |
| delete | remove, destroy | Only for permanent removal. |
| NebulaOS | Nebula, NebulaOs, nebula | `nebula` is correct only as the CLI command, in code format. |

- ✅ Every page needs a `title` and a `description`.
- ❌ Every doc needs a `title` and a `description`.

### TERM-2: Use page states exactly as defined — Error

Page states are listed in [Core concepts](getting-started/core-concepts.md),
which is the source of truth. When you name a state, format it as code
(`published`, not "live"). Don't use a state in one page that Core concepts
doesn't define. When a feature adds a state, update Core concepts in the same
change request.

### TERM-3: Say what kind of expiry you mean — Warning

"Expire" applies to several things in NebulaOS: cache entries, API tokens, and
any page-level behavior the product defines. Always name the subject ("the
cache entry expires", "the token expires"), and never use "expire" as a
synonym for unpublish or delete.

---

## 3. Structure

### STRUCT-1: Every page has frontmatter — Error

Every page starts with YAML frontmatter containing `title` and `description`.
The description is one sentence, in sentence case, ending with a period.

### STRUCT-2: One H1, matching the title — Error

Each page has exactly one `#` heading, and it matches the frontmatter `title`.
Don't skip heading levels (for example `##` straight to `####`).

### STRUCT-3: Headings use sentence case — Warning

Capitalize only the first word and proper nouns.

- ✅ `## Custom domain`
- ❌ `## Custom Domain`

Task headings start with a verb in the base form ("Install the CLI", not
"Installing the CLI"). Don't end headings with punctuation. FAQ questions are
the exception and end with a question mark.

### STRUCT-4: Introduce before you conclude — Warning

Explain what a step did or produced *before* telling the reader they're done.
Confirmation lines ("The scaffold is ready to edit.") come after the
explanation, never before it.

### STRUCT-5: Use numbered lists for sequences — Suggestion

Use a numbered list when order matters and a bulleted list when it doesn't.
Each step is one action. Start each step with an imperative verb.

### STRUCT-6: Keep procedures on one page — Suggestion

A reader should be able to complete a task without leaving the page. Link out
for background, not for required steps.

---

## 4. Formatting

### FMT-1: Code formatting for literal values — Error

Use `code` formatting for commands, flags, file names, paths, config keys,
field names, API endpoints, HTTP status codes, and enum values.

- ✅ Set `review_required` to `false` in `nebula.yaml`.
- ❌ Set review_required to false in nebula.yaml.

### FMT-2: Label every code block with a language — Warning

Use `bash` for shell commands, `yaml`, `json`, `http`, or `markdown` as
appropriate. Don't include a `$` prompt in commands the reader copies.

### FMT-3: Use one placeholder style — Warning

Write placeholders in angle brackets, lowercase, with hyphens:
`<page-id>`, `<project-id>`, `<timestamp>`. In API paths, use the same form
(`/pages/<page-id>`), not `{page_id}`.

### FMT-4: Bold for UI elements, arrows for paths — Warning

Format UI labels in **bold**, exactly as they appear in the dashboard. Separate
navigation steps with →, and give the full path from a top-level menu.

- ✅ Go to **Project → Settings → Domain**.
- ❌ Go to Settings > Domain.

### FMT-5: Tables have a header and consistent cells — Suggestion

Every table has a header row. Description cells are sentences that start with
a capital letter and end with a period, or are all fragments without periods.
Don't mix the two in one table.

### FMT-6: Use em dashes sparingly — Suggestion

Prefer a period, colon, or parentheses. If you use an em dash (—), use no more
than one per paragraph.

---

## 5. Links

### LINK-1: Link text describes the destination — Error

Link text matches the target page's title, or clearly describes it. Never use
"here", "this page", or "click here".

- ✅ See [Caching and invalidation](guides/caching.md).
- ❌ See [Caching](guides/caching.md).
- ❌ For details, click [here](guides/caching.md).

### LINK-2: Use relative links to pages in this repository — Error

Link to other pages with relative paths to the `.md` file, not to the
published URL. Every linked page must exist and be listed in `SUMMARY.md`.

---

## 6. Numbers, dates, and units

### NUM-1: Numbers — Suggestion

Spell out zero through nine in prose; use numerals for 10 and above, and
always for measurements, versions, and limits. Use a comma in numbers of four
or more digits (5,000).

### NUM-2: Dates and times — Warning

Use ISO 8601 in code, examples, and the changelog (`2026-08-14`,
`2026-09-01T09:00:00Z`). In prose, write "August 14, 2026". Always give times
in UTC.

### NUM-3: Units and durations — Suggestion

Put a space between a number and its unit in prose (200 MB, 60 seconds). In
tables and config values, use the compact form the product accepts (`60s`,
`30d`, `180d`) and format it as code.

---

## 7. Accuracy

### ACC-1: Don't contradict other pages — Error

A product behavior must be described the same way on every page. If two pages
disagree, fix both and check the [Changelog](changelog.md) for which one is
current. When a change request adds or changes a feature, search the whole
project for pages that describe the old behavior and update them in the same
change request.

### ACC-2: Don't promise what the product doesn't do — Error

Don't describe features, flags, commands, or states that aren't in the
[CLI reference](reference/cli.md), [Configuration](reference/configuration.md),
or API reference. Absolute claims ("never", "always", "indefinitely") must be
true.

---

## Quick checklist

Before opening a change request, check that the page:

- [ ] Has `title` and `description` frontmatter and one matching H1 (STRUCT-1, STRUCT-2)
- [ ] Uses sentence-case headings (STRUCT-3)
- [ ] Contains none of: simply, just, easy, easily, obviously, that's it (VOICE-3)
- [ ] Contains none of: currently, soon, new, at the moment (VOICE-4)
- [ ] Says *project*, *page*, *maintainer*, and *unpublish*, never *site*, *doc*, *reviewer*, or *take down* (TERM-1)
- [ ] Formats commands, paths, keys, and states as code (FMT-1)
- [ ] Uses `<lowercase-hyphen>` placeholders (FMT-3)
- [ ] Has link text that matches the target page title (LINK-1)
- [ ] Agrees with every other page that describes the same behavior (ACC-1)
