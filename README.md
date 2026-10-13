# Jincheng Guan's Academic Homepage

Personal academic homepage at <https://gjc2.github.io/>, built with Hugo and
[PaperMod](https://github.com/adityatelange/hugo-PaperMod).

## Edit the site

- `content/_index.md`: biography, research, publications, news, and contact details.
- `hugo.toml`: name, navigation, social links, theme settings, and metadata.
- `images/profile.jpg`: original profile photo.
- `files/CV.pdf` and `files/CV.tex`: original CV and its source.
- `layouts/home.html`: displays PaperMod's profile above the homepage content.
- `assets/css/extended/academic.css`: small responsive layout adjustments.

The existing `/images/…` and `/files/…` URLs, homepage section anchors, and
`/feed.xml` URL are preserved. Hugo mounts the original images and files as
static content; no duplicate copy is needed.

## Preview and build

Install Hugo **0.167.0** (the standard edition is sufficient), then run:

```sh
hugo server
```

Open the local URL printed by Hugo. To build the production site:

```sh
hugo --gc --minify --panicOnWarning
```

The generated website is written to `public/`.

## Deployment

`.github/workflows/deploy.yml` builds pull requests for validation and deploys
pushes to `main` to GitHub Pages. The repository's Pages source must be **GitHub
Actions**, as in the existing deployment setup. The CV and other assets remain
unchanged.

## Theme provenance

PaperMod is vendored under `themes/PaperMod` at upstream commit
`d3768854d00ad003b0a8dbdba254ce9224377a01`. Its runtime assets, templates,
translations, metadata, and MIT license are retained without modification.
Vendoring makes both local and CI builds independent of a theme download.
Site-specific overrides live outside the theme directory. The copies of
`baseof.html`, `rss.xml`, and the Open Graph partial in `layouts/` only replace
Hugo's deprecated language properties with `Direction` and `Locale`, so the
pinned Hugo version builds without deprecation warnings.

The previous Jekyll/Academic Pages theme was removed as part of this migration;
the original license remains in `LICENSE`.
