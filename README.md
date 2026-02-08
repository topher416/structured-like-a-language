# Structured Like a Language

A cross-disciplinary research project connecting Lacanian psychoanalysis and transformer AI through testable, falsifiable structural claims.

This repository is a GitHub Pages site that publishes a long-form research brief from Markdown.

## What this repo contains

- `structured-like-a-language-full-brief.md`: the source brief text
- `index.md`: the homepage entry point for GitHub Pages
- `_layouts/default.html`: custom page layout
- `assets/css/style.css`: custom visual styling
- `_config.yml`: Jekyll site configuration

## GitHub Pages setup

1. Push this repository to GitHub.
2. In GitHub, open `Settings` > `Pages`.
3. Under `Build and deployment`, set `Source` to `Deploy from a branch`.
4. Select your default branch (usually `main`) and folder `/ (root)`.
5. Save, then wait for the site to build.

Your site URL will appear in the Pages settings after deployment.

## Local preview (optional)

If you want to preview locally with Jekyll:

```bash
bundle init
bundle add github-pages --group "jekyll_plugins"
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000`.
