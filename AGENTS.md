# Repository Instructions

This is Nova Patch’s personal Jekyll site at `https://novapatch.ie`, with
writing, talks, research, and a few static project pages.

## Build and Generated Files

Use the Ruby version in `.ruby-version`. Build with:

```sh
bundle exec jekyll build
```

If `bundle` or `ruby` resolves to `/usr/bin/...`, the shell has not loaded
chruby correctly. For Codex or other automation shells, run the command through
interactive zsh so the existing `~/.zshrc` chruby setup is loaded:

```sh
zsh -ic 'bundle exec jekyll build'
```

Treat `_site/` as generated output. Edit source files instead.

## Sitemap Maintenance

When editing indexable pages, keep `sitemap.xml` in sync.

Update a page’s `<lastmod>` only when the edit is a significant update to that
page, following Google’s sitemap guidance. Significant updates generally include
changes to main content, page-specific structured data, or page-specific links
within the main content. Do not update `<lastmod>` for incidental edits such as
formatting-only changes, comments, build/config changes, shared navigation,
shared layout or component changes, site-wide style changes, typo-only fixes
that do not materially change meaning, or copyright/date boilerplate.

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

## Authorship and AI Assistance

This repository represents human-authored personal and public knowledge
management. The site owner’s primary focus is human knowledge management, not
AI-generated publication.

Generative AI may be used for Webmaster assistance, including editing support,
formatting, site maintenance, administrative text generation, metadata updates,
and other implementation or maintenance tasks. Do not treat the presence of
prose-style instructions as permission to generate primary site content on the
owner’s behalf.

When assisting with prose, preserve the owner’s meaning, voice, authorship, and
intent. Suggest or apply edits only as editorial or maintenance assistance
unless explicitly asked to draft new content.

## Prose Style

Apply these rules to the site owner’s English prose. Do not alter quoted text,
external titles, names, code, data formats, machine-readable metadata, or any
other text where exact wording or syntax matters.

Use Irish English (`en-IE`) spelling by default, with Oxford spelling
(`en-GB-oed`) overrides where Oxford spelling differs from standard British
English. In practice, prefer `-ize`, `-ization`, and `-yze` forms when Oxford
spelling calls for them, while otherwise following Irish/British usage.
Reference: https://en.wikipedia.org/wiki/Oxford_spelling

Write dates in natural-language prose in the usual Irish format, e.g.
`10 June 2026`. Use ISO 8601 dates such as `2026-06-10` where technically
appropriate, including structured data, filenames, front matter, sitemaps,
machine-readable metadata, and code.

In natural-language prose, use these Unicode quotation mark characters:

- `‘` U+2018 LEFT SINGLE QUOTATION MARK for opening single quotation marks.
- `’` U+2019 RIGHT SINGLE QUOTATION MARK for apostrophes and closing single
  quotation marks.
- `“` U+201C LEFT DOUBLE QUOTATION MARK for opening double quotation marks.
- `”` U+201D RIGHT DOUBLE QUOTATION MARK for closing double quotation marks.

Preserve ASCII apostrophe U+0027 and quotation mark U+0022 where they are
required by code, data formats, or markup syntax.

Use literal UTF-8 characters instead of HTML character entity references
whenever the literal character is allowed by the surrounding HTML or XHTML
syntax. Use entity references only when they are technically required for
conforming markup or to avoid changing how the markup is parsed.

This rule also applies to intentional Unicode spacing characters such as
non-breaking spaces. Prefer semantic markup or CSS when spacing behaviour is
presentational; when the character itself is content, use the literal UTF-8
character unless an entity reference is required for conforming markup.

Prefer sparse punctuation in prose. Commas, semicolons, colons, and em dashes
are all allowed, but omit them when the sentence remains clear without them.
Use commas lightly, avoid semicolons unless they genuinely improve clarity, and
prefer plain sentence rhythm over heavily marked structure.

Use en dashes and em dashes according to *The Chicago Manual of Style*. Use an
en dash for numeric ranges, date ranges, and relationships such as
`Dublin–London`. Use an em dash only for a true break in thought or
parenthetical interruption. Do not use em dashes as a default sentence joiner.
