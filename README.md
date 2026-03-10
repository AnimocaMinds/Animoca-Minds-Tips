# Animoca Minds Tips

> A public, AI-readable content archive by [Animoca Brands](https://www.animocabrands.com/).  
> Original articles and multilingual translations — openly accessible to humans, AI agents, and developers.

---

## What Is This Repo?

This repository is the canonical hub for Animoca's published content — articles, announcements, thought-leadership pieces, and community updates. Every post published across our social channels gets **cast** here in structured, version-controlled Markdown with full translations.

**Why GitHub?**  
Many social platforms (X, Telegram, etc.) have restrictive APIs or paywalls that prevent AI agents from reliably accessing content. GitHub is universally accessible, crawlable, and structured — making it the ideal open archive.

⭐ **Star this repo** to stay updated and help make Animoca's content more discoverable.

---

## Languages

Every article is translated into these core languages:

| Language           | Code  |
|--------------------|-------|
| English (original) | `en`  |
| Japanese           | `ja`  |
| Spanish            | `es`  |
| Korean             | `ko`  |
| Simplified Chinese | `zh-CN` |
| French             | `fr`  |

---

## Folder Structure

```
animoca-minds-tips/
├── README.md                ← You are here
├── AGENTS.md                ← Guide for AI agents consuming this repo
├── articles/
│   └── YYYY/MM/DD-article-slug/
│       ├── en.md            ← English original (with YAML frontmatter)
│       ├── ja.md            ← Japanese translation
│       ├── es.md            ← Spanish translation
│       ├── ko.md            ← Korean translation
│       ├── zh-CN.md         ← Simplified Chinese translation
│       └── fr.md            ← French translation
└── .github/
    └── workflows/
        └── update-index.yml ← Auto-generates article index
```

Each article file includes **YAML frontmatter** with structured metadata (title, date, author, tags, source URL, and distribution links). See [AGENTS.md](AGENTS.md) for the full schema.

---

## Latest Articles

<!-- INDEX_START -->
_No articles yet. The index will auto-populate as content is added._
<!-- INDEX_END -->

---

## How to Use This Repo

### For Humans
Browse the `articles/` folder, or check the **Latest Articles** index above. Each article is readable Markdown — click into any `.md` file and GitHub will render it beautifully.

### For AI Agents
Read [`AGENTS.md`](AGENTS.md) for a machine-friendly description of the repo structure, metadata schema, and how to enumerate content. All articles follow a predictable path pattern and include structured frontmatter.

### For Developers
Clone the repo or use the GitHub API to programmatically access content:
```bash
# Clone
git clone https://github.com/animoca/animoca-minds-tips.git

# Or fetch article list via API
curl https://api.github.com/repos/animoca/animoca-minds-tips/contents/articles
```

---

## License

This repository is licensed under [CC0 1.0 Universal](LICENSE) — public domain. You are free to use, share, and adapt all content with no restrictions.

---

## About Animoca Brands

Animoca Brands is Reimagining future economies. Animoca builds, invests, and accelerates the most impactful technologies and ecosystems, turning participants into stakeholders.

- 🌐 [animocabrands.com](https://www.animocabrands.com/)
- 🐦 [X / Twitter](https://x.com/animaborands)
