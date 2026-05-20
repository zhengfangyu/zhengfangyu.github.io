# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

- **Build/Preview locally**: `bundle exec jekyll serve` (serves at http://localhost:4000)
- **Build with dev config**: `bundle exec jekyll serve --config _config.dev.yml`
- **Build for production**: `bundle exec jekyll build`
- **Install dependencies**: `bundle install`
- **JS minification**: `npm run build:js` (uglifies JS assets)
- **Update GitHub Pages gem**: `bundle update github-pages`
- **Talk map generation**: Run `python talkmap.py` from the `_talks/` directory (requires `getorg` and `geopy`)
- **Publication markdown generator**: Jupyter notebooks in `markdown_generator/` (e.g., `publications.ipynb`, `talks.ipynb`)

## Project Structure

Jekyll-based academic personal website using the **Minimal Mistakes** theme, deployed via GitHub Pages.

### Key Directories

- **`_pages/`** — Core site pages (about, cv, full-publications, standards, teaching, talks, portfolio, etc.). The homepage is `_pages/about.md` (permalink: `/`).
- **`_publications/`** — Full publication list page (`Full publications.md`).
- **`_talks/`** — Talk markdown files with YAML front matter including `location` fields (used by talkmap).
- **`_teaching/`** — Teaching experience entries.
- **`_posts/`** — Blog posts (dated markdown files).
- **`_data/`** — Site data:
  - `navigation.yml` — Main navigation bar links (currently: Full Publications, Standards)
  - `authors.yml` — Author definitions (theme feature, not actively used here)
  - `ui-text.yml` — UI string translations
- **`_layouts/`** — Layout templates (single, archive, talk, splash, compress, default, archive-taxonomy).
- **`_includes/`** — Reusable HTML snippets (masthead, footer, analytics, comments, etc.).
- **`_sass/`** — SCSS partials for styling.
- **`assets/`** — Compiled CSS, fonts, JS, and publication PDFs (`assets/papers/`).
- **`images/`** — Site images and author portrait (`zhengfangyu_potrait.jpg`).
- **`talkmap/`** — Generated talk location map (Leaflet-based, output of `talkmap.py`).
- **`markdown_generator/`** — Jupyter notebooks and Python scripts to generate publication/talk markdown from TSV/BibTeX.
- **`files/`** — Miscellaneous downloadable files.

### Theme & Configuration

- Uses **Minimal Mistakes** Jekyll theme (v3.4.2), configured via `_config.yml`.
- GitHub Pages–compatible: `Gemfile` uses the `github-pages` gem with plugins (jekyll-feed, jekyll-sitemap, jemoji, jekyll-paginate, etc.).
- Markdown: kramdown with GFM input. Highlighter: rouge.
- Collections: `teaching`, `publications`, `portfolio`, `talks` (each with their own permalink pattern).
- Author info defined in `_config.yml` under `author:` (name, avatar, bio, social links).

### Content Updates

- **Publications**: Edit `_pages/about.md` for selected publications, or `_pages/full-publications.md` for the complete list. Publication PDFs go in `assets/papers/`.
- **Standards**: Edit `_pages/standards.md`.
- **Navigation**: Edit `_data/navigation.yml` to add/remove menu links.
- **Profile**: Edit the `author:` block in `_config.yml`.
- **New posts**: Add dated `.md` file to `_posts/` with proper YAML front matter.
