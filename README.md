# novapatch.ie / patch.github.io

© 2010–2026 Nova Patch

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/) (CC BY-SA 4.0).

## Authorship and AI Assistance

This repository represents human knowledge management. I use generative AI for Webmaster assistance, including editing support, formatting, site maintenance, metadata updates, and administrative text generation. Primary site content remains human-authored.

## Development

Use the Ruby version in `.ruby-version`, then build with:

```sh
bundle exec jekyll build
```

Deployment to GitHub Pages is handled by GitHub Actions in `.github/workflows/jekyll.yml`. The workflow installs the bundled Ruby dependencies and uploads the generated `_site/` artifact to Pages.
