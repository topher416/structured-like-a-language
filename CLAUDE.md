# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A GitHub Pages site publishing a long-form research brief: "Structured Like a Language: Transformer Architectures and the Instantiation of the Lacanian Unconscious." The brief argues that transformer LLMs instantiate the formal operations Lacan attributed to the unconscious — condensation, displacement, overdetermination, retroactive meaning-making — and proposes a multi-phase research plan to test that claim empirically.

## Architecture

This is a static Jekyll site with a custom layout (no theme gem). The full content pipeline is:

- `structured-like-a-language-full-brief.md` — the sole content source (~950 lines of research brief)
- `index.md` — entry point that uses `{% include_relative %}` to pull in the full brief
- `_layouts/default.html` — custom HTML layout with header, prose container, and footer
- `assets/css/style.css` — all styling via CSS custom properties (warm serif reading design)
- `_config.yml` — Jekyll config with `theme: null`, kramdown/GFM markdown, and `jekyll-seo-tag` plugin

There are no collections, no data files, no JavaScript, and no build tooling beyond Jekyll itself.

## Local Development

```bash
# One-time setup
bundle init
bundle add github-pages --group "jekyll_plugins"

# Serve locally
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000`.

## Deployment

Push to `main`. GitHub Pages deploys automatically from the root of the `main` branch.

## Git Account

This repo uses **topher416** — `Topher Rasmussen <topher416@gmail.com>`.

## Key Conventions

- `_config.yml` sets `theme: null` — all layout and styling is custom, not inherited from a gem theme.
- The CSS uses a warm, serif-first reading design (`Source Serif 4` / Georgia fallback) with CSS custom properties for colors. The `--accent` color is `#9f5f2e`.
- The layout wraps content in a `.prose` container (max 920px) with card-style styling. Any new pages should use the same `default` layout.
- The brief is a single monolithic Markdown file. Edits to the published content happen in `structured-like-a-language-full-brief.md`, not in `index.md`.
