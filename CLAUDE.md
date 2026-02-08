# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A multi-page GitHub Pages research hub for "Structured Like a Language: Transformer Architectures and the Instantiation of the Lacanian Unconscious." The project argues that transformer LLMs instantiate the formal operations Lacan attributed to the unconscious — condensation, displacement, overdetermination, retroactive meaning-making — and is organized as a 5-phase, 9–12 month research plan with a dedicated page per deliverable.

## Architecture

This is a static Jekyll site with a custom layout (no theme gem).

### Site Structure

- `index.md` — hub/dashboard linking to all phases and deliverables
- `brief.md` — the full original research brief (uses `{% include_relative %}` to pull in the monolithic source)
- `structured-like-a-language-full-brief.md` — the sole content source for the brief (~950 lines)
- `progress.md` — phase-by-phase status tracker with timeline and checklists
- `phases/` — one markdown page per research deliverable:
  - `1-1-lacanian-specification.md` through `1-3-formal-mapping.md` (Phase 1: Theory)
  - `2-1-literature-review.md`, `2-2-objections.md` (Phase 2: Literature)
  - `3-1-predictions.md` through `3-3-lack.md` (Phase 3: Empirical)
  - `4-manuscript.md` (Phase 4: Manuscript)
  - `5-collaboration.md` (Phase 5: Review)

### Layout and Styling

- `_config.yml` — Jekyll config with `theme: null`, kramdown/GFM markdown, `jekyll-seo-tag` plugin, and `nav` data for site navigation
- `_layouts/default.html` — custom HTML layout with header, nav include, prose container, footer, and mobile nav toggle script
- `_includes/nav.html` — reusable navigation partial with dropdown menus driven by `site.nav` data in `_config.yml`
- `assets/css/style.css` — all styling via CSS custom properties (warm serif reading design)

### Primary Source Processing Pipeline

- `sources/PROCESSING-GUIDE.md` — full pipeline documentation for converting scanned PDFs and other formats into clean markdown
- `sources/SOURCE-REGISTRY.md` — index of all 26+ primary and secondary sources with processing status
- `sources/raw/` — original source files (gitignored — copyrighted material)
- `sources/processed/` — clean markdown transcriptions (gitignored)
- `sources/scripts/prompts/` — reusable prompts for vision-based transcription, assembly/cleanup, and verification

**Before processing any source:** Read `sources/PROCESSING-GUIDE.md` to identify the source type (A–E) and follow the corresponding pipeline. Read `sources/SOURCE-REGISTRY.md` to check status and update it when processing begins/completes.

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
- Navigation is data-driven: edit the `nav` key in `_config.yml` to add or reorder nav items. Dropdown children are supported.
- The CSS uses a warm, serif-first reading design (`Source Serif 4` / Georgia fallback) with CSS custom properties. The `--accent` color is `#9f5f2e`.
- The layout wraps content in a `.prose` container (max 920px) with card-style styling. All pages use the `default` layout.
- Phase status indicators use kramdown attribute syntax: `{: .phase-pending}`, `{: .phase-active}`, `{: .phase-complete}` on `##` headers. Update these as phases progress.
- The original brief lives in `structured-like-a-language-full-brief.md`. Edits to the published brief happen there, not in `brief.md` or `index.md`.
- Raw source files and processed transcriptions are gitignored. Only the processing guide, registry, and prompts are committed.
