# Repository Instructions

## Sitemap Maintenance

When editing indexable pages, keep `sitemap.xml` in sync.

Update a page’s `<lastmod>` only when the edit is a significant update to that
page, following Google’s sitemap guidance. Significant updates generally include
changes to main content, structured data, or links on the page. Do not update
`<lastmod>` for incidental edits such as formatting-only changes, comments,
build/config changes that do not alter the rendered page, typo-only fixes that
do not materially change meaning, or copyright/date boilerplate.

Use the current local date in `YYYY-MM-DD` format when a `<lastmod>` update is
warranted.

When adding a new indexable page:

1. Add a new `<url>` entry to `sitemap.xml`.
2. Use the canonical absolute URL under `https://novapatch.ie`.
3. Set `<lastmod>` to the page’s publication date, or the current local date if
   no separate publication date is known.
4. Preserve the existing sitemap sort order:
   - `/en/` first.
   - The localized About pages next, grouped together with their `xhtml:link`
     alternates.
   - Remaining `/en/...` pages sorted alphabetically by URL.
   - If adding sitemap-covered pages outside those groups, place them after the
     existing grouped entries and sort them alphabetically by URL within their
     path group unless the surrounding sitemap has established a more specific
     order.

For localized pages with alternates, include the same reciprocal
`xhtml:link rel="alternate"` block on every URL in that alternate set.

Reference: Google Search Central says Google uses `<lastmod>` when it is
consistently and verifiably accurate, and that it should reflect the last
significant update to the page.

## Prose Style

In natural-language prose, use the Unicode quotation mark characters
appropriate for English (en) text:

- `‘` U+2018 LEFT SINGLE QUOTATION MARK for opening single quotation marks.
- `’` U+2019 RIGHT SINGLE QUOTATION MARK for apostrophes and closing single
  quotation marks.
- `“` U+201C LEFT DOUBLE QUOTATION MARK for opening double quotation marks.
- `”` U+201D RIGHT DOUBLE QUOTATION MARK for closing double quotation marks.

Preserve ASCII apostrophe U+0027 and quotation mark U+0022 where they are
required by code, data formats, or markup syntax.
