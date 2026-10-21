# MavridisChristos.github.io

Research portfolio website of Christos Mavridis, built with [Jekyll](https://jekyllrb.com/).

## Usage

```bash
bundle exec jekyll serve --lsi
```

Requires Ruby (see `.ruby-version`) and Bundler. On first setup, install dependencies with:

```bash
bundle install
```

The site will be available at `http://127.0.0.1:4000`. Note that changes to `_config.yml` or files in `_plugins/` are not picked up by the live-reload watcher — restart the server to see those.

## About this repo

This site is built on [al-folio](https://github.com/alshedivat/al-folio), an open-source Jekyll theme for academics, kept up to date with upstream and customized on top:

- Content, CV, publications, and project data specific to this site
- Landing page redesigned with an academicpages-style sidebar (profile, contact info, social links) alongside the main content column
- Various layout, typography, and styling adjustments throughout

See the [al-folio repository](https://github.com/alshedivat/al-folio) for the base theme, its documentation, and license.
