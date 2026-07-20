# Repository Instructions

Nova Patch’s personal Jekyll site lives at <https://novapatch.ie>. It contains human-authored writing, talks, research, and static project pages.

## Build

Use the Ruby version in `.ruby-version`. Build with `bundle exec jekyll build`; in Codex or other automation shells, use `zsh -ic 'bundle exec jekyll build'` if `ruby` or `bundle` resolves to `/usr/bin/...`, because chruby has not loaded. Treat `_site/` as generated output and edit source files instead.

GitHub Pages deploys through `.github/workflows/jekyll.yml`, which installs the bundle and uploads `_site/`. Keep Pages on the GitHub Actions source. Do not rewrite modern Sass, including `@use`, for legacy Pages compatibility unless deployment intentionally moves back to the branch builder.

## Sitemap

When editing indexable pages, keep `sitemap.xml` in sync. Update `<lastmod>` only for significant page-specific changes: main content, page-specific structured data, or page-specific links. Do not update it for formatting, comments, build/config changes, shared layouts/navigation/styles, minor typo fixes, or copyright/date boilerplate. Use the current local date in `YYYY-MM-DD` when an update is warranted.

When adding a new indexable page, add a `<url>` with the canonical `https://novapatch.ie` URL and a `<lastmod>` from the publication date, or today if none is known. Preserve sitemap order: `/en/` first; localized About pages grouped with reciprocal `xhtml:link` alternates; remaining `/en/...` pages alphabetically; other path groups after existing grouped entries, alphabetically unless local order says otherwise.

## Authorship

Primary site content is human-authored unless explicitly requested otherwise. Use AI only for webmaster, editing, formatting, metadata, and maintenance help. Preserve the owner’s meaning, voice, authorship, and intent.

## Prose Style

Apply this only to the owner’s English prose. Do not change exact text in quotes, titles, names, code, data formats, metadata, or syntax-sensitive markup.

Use paragraph-as-block Markdown: one soft-wrapped source block per paragraph, blank lines between paragraphs. Keep hard line breaks only when structurally meaningful. Treat block HTML in Markdown as an HTML island and preserve its indentation, child text, and continuation attributes.

Use Irish English with Oxford spelling where it differs: prefer `-ize`, `-ization`, and `-yze`, otherwise Irish/British usage. Write prose dates as `10 June 2026`; use ISO dates for filenames, front matter, sitemaps, structured data, code, and other machine-readable text.

In natural prose, use Unicode quotes: `‘` and `’`, including apostrophes; `“` and `”`. Preserve ASCII `'` and `"` where code, data, or markup requires them.

Use literal UTF-8 characters, including intentional spacing characters, whenever valid in the surrounding HTML/XHTML. Use entities only when required for conforming markup or to preserve parsing.

Prefer sparse punctuation. Use en dashes for ranges and relationships such as `Dublin–London`. Use em dashes only for true breaks in thought, not as default sentence joiners.

## Token Use

Keep always-loaded instructions concise. Prefer targeted file reads and avoid adding broad standing guidance for work that can instead be requested after meaningful change batches.
