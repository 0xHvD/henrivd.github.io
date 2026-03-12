# CLAUDE.md – henrivd-Blog

## Project Overview

Personal blog and toolbox of Henri van Dorsten, IT Security Consultant.
Live at: **https://henrivd.github.io**
Repository: `henrivd/henrivd.github.io`

**Stack:** Jekyll + [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) (remote theme, **air skin** – white/teal, inspired by merill.net) + GitHub Pages
**Language:** German (locale: `de-DE`)

---

## Directory Structure

```
_config.yml          # Jekyll + Minimal Mistakes configuration
_data/
  navigation.yml     # Main nav: Start, Blog, Tools, Über mich
_pages/
  about.md           # /about/
  blog.md            # /blog/  (paginated post listing)
  tools.md           # /tools/ (links to individual tools)
_posts/
  YYYY-MM-DD-slug.md # Blog posts
tools/
  <tool-name>/
    index.html       # Self-contained tool page
    app.js
    style.css
index.md             # Homepage (splash layout)
Gemfile              # github-pages gem + jekyll-include-cache + jekyll-paginate
```

---

## Running Locally

```bash
bundle install
bundle exec jekyll serve
# → http://localhost:4000
```

---

## Content Conventions

### Blog Posts (`_posts/`)

Filename: `YYYY-MM-DD-kebab-case-title.md`

```yaml
---
title: "Titel des Beitrags"
date: YYYY-MM-DD
categories:
  - Blog
tags:
  - IT-Security
  - Active Directory   # example tags
---
```

Default front matter (from `_config.yml`): `layout: single`, `author_profile: true`, `read_time: true`, `toc: true`, `toc_sticky: true`

### Pages (`_pages/`)

```yaml
---
title: "Seitentitel"
permalink: /slug/
layout: single
---
```

### Tools (`tools/<name>/`)

- Pure browser-based, **no server communication**
- Vanilla JS preferred; use `crypto.getRandomValues()` for any randomness
- Self-contained: own `index.html`, `app.js`, `style.css`
- After adding a tool, link it in `_pages/tools.md`

---

## Topics / Focus Areas

- Active Directory Security
- Tiering und privilegierte Identitäten
- Entra ID / Azure AD
- Incident Response Readiness

---

## Jekyll Plugins (active)

- `jekyll-paginate` (5 posts per page, path `/blog/page:num/`)
- `jekyll-sitemap`
- `jekyll-gist`
- `jekyll-feed`
- `jekyll-include-cache`

---

## Git Workflow

- Main branch: `main` (deployed to GitHub Pages)
- Commit early, commit often; no force-pushes to `main` without explicit confirmation
- `.gitignore` excludes: `_site/`, `.sass-cache/`, `.jekyll-cache/`, `.jekyll-metadata`, `vendor/`, `Gemfile.lock`, `.bundle/`
