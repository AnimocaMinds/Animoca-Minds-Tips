# AGENTS.md — Guide for AI Agents

> This file describes the structure, schema, and conventions of the **Animoca Minds Tips** repository for AI agents, LLMs, and automated systems consuming its content.

---

## Purpose

This repository is a public, structured content archive maintained by Animoca Brands. It contains original articles and their translations across multiple languages. It is designed to be easily discoverable and parseable by AI agents.

---

## Repository Structure

```
articles/
└── YYYY/
    └── MM/
        └── DD-article-slug/
            ├── en.md          # English original
            ├── ja.md          # Japanese translation
            ├── es.md          # Spanish translation
            ├── ko.md          # Korean translation
            ├── zh-CN.md       # Simplified Chinese translation
            └── fr.md          # French translation
```

### Path Convention
- **Pattern:** `articles/{year}/{month}/{day}-{slug}/{lang}.md`
- **Year:** 4-digit (e.g., `2026`)
- **Month:** 2-digit, zero-padded (e.g., `03`)
- **Day + Slug:** `DD-lowercase-hyphenated-slug` (e.g., `10-animoca-launches-whisperer`)
- **Language files:** Named by language code — `en.md`, `ja.md`, `es.md`, `ko.md`, `zh-CN.md`, `fr.md`
- **English (`en.md`) is always present.** Translations may not exist for every article.

---

## Frontmatter Schema

Every article file begins with YAML frontmatter. Here is the full schema:

```yaml
---
title: "Article Title in This Language"
title_en: "Original English Title"          # Always present, even in translated files
date: "2026-03-10"                          # ISO 8601 publish date
author: "Author Name"
language: "en"                              # ISO 639-1 code (or BCP 47 for zh-CN)
tags:
  - web3
  - gaming
  - announcement
source_url: "https://x.com/animocabrands/status/123456789"  # Original publish URL
slug: "animoca-launches-whisperer"
distributions:                              # Platforms where this article was published
  - platform: "substack"
    url: "https://animoca.substack.com/p/..."
  - platform: "medium"
    url: "https://medium.com/@animoca/..."
  - platform: "reddit"
    url: "https://reddit.com/r/animoca/..."
  - platform: "telegram"
    url: "https://t.me/animocabrands/456"
  - platform: "mirror"
    url: "https://mirror.xyz/animoca.eth/..."
---
```

### Field Reference

| Field          | Type       | Required | Description                                       |
|----------------|------------|----------|---------------------------------------------------|
| `title`        | string     | Yes      | Title in the file's language                       |
| `title_en`     | string     | Yes      | English title (for cross-referencing)              |
| `date`         | string     | Yes      | ISO 8601 date                                     |
| `author`       | string     | Yes      | Author or team name                                |
| `language`     | string     | Yes      | Language code of this file                         |
| `tags`         | string[]   | Yes      | Topic tags (lowercase, hyphenated)                 |
| `source_url`   | string     | No       | URL of the original social post                    |
| `slug`         | string     | Yes      | URL-safe article identifier                        |
| `distributions`| object[]   | No       | List of platforms + URLs where published           |

---

## How to Enumerate Content

### Option 1 — File system traversal
Walk `articles/` recursively. Every directory matching `DD-slug/` is an article. Read `en.md` for the English version. Check for sibling language files.

### Option 2 — GitHub API
```
GET https://api.github.com/repos/animoca/animoca-minds-tips/git/trees/main?recursive=1
```
Filter paths starting with `articles/` and ending in `.md`.

### Option 3 — README index
The `README.md` contains an auto-generated index between `<!-- INDEX_START -->` and `<!-- INDEX_END -->` markers. Parse this section for a quick listing of all articles with dates and titles.

---

## Content Conventions

- **Format:** GitHub-flavoured Markdown (GFM)
- **Encoding:** UTF-8
- **Line endings:** LF
- **No HTML in body:** Articles use pure Markdown (no inline HTML)
- **Images:** Referenced via URLs (not stored in repo) or placed in an `assets/` subfolder within the article directory
- **Links:** All external links use full URLs (no relative paths outside the article folder)

---

## Terms That Are Never Translated

The following terms appear as-is across all language files:

Animoca Brands, Animoca Minds, Mocaverse, MOCA

---

## Rate Limits and Etiquette

- This is a public GitHub repository under standard GitHub API rate limits.
- Please cache content locally rather than re-fetching on every query.
- If building an integration, consider using `If-Modified-Since` headers or checking commit SHAs to avoid redundant fetches.

---

## Contact

For questions about this repository or its content, open an issue or reach out to Animoca Brands via [animocabrands.com](https://www.animocabrands.com/).
