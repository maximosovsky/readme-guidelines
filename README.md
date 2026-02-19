<div align="center">

# 📐 README Guidelines

![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![License](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey?style=for-the-badge)

**Checklist and template for crafting beautiful GitHub READMEs**

[🇷🇺 Русская версия](README-ru.md)

</div>

> A good README is a book cover. If it's boring, nobody opens the project. This guide gathers proven techniques that make READMEs professional and eye-catching.

---

## ✅ What to Use

| Technique | What it Does | Example |
|-----------|-------------|---------|
| **Centered header** | `<div align="center">` — logo + title centered, creates a "cover" | ⏳ LifeLine / 🔍 xyzz.me |
| **Shields.io badges** | Bright colored badges with status, license, tech stack | `![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react)` |
| **Emoji section headers** | Visual navigation — eyes catch icons instantly | 💡 Concept · ✨ Features · 🚀 Quick Start |
| **Tagline** | One bold line under the title — project essence in 1 sentence | *"See your entire life on paper"* |
| **Preview image** | Instantly shows what the product looks like | `<img src="preview.png" width="600">` |
| **Feature tables** | Structured feature list, easy to scan | Feature \| Description |
| **Collapsible sections** | `<details>` — hides secondary info (env vars, build, lectures) | Keeps README uncluttered |
| **Blockquote** | `>` — project philosophy / concept, visually stands out | *"Lines and structures are a language..."* |
| **Horizontal dividers** | `---` between sections — clear visual separation | |
| **ASCII tree structure** | Instant architecture overview in code | `client/ ├── pages/` |
| **Inline navigation** | Anchor links under header — quick access to sections | `Quick Start · Features · Docs` |
| **Animated GIF / video** | Demo in action beats a screenshot — shows the flow | `![demo](demo.gif)` |
| **Contributing section** | Attracts contributors, sets standards: fork → branch → PR | Fork → `feature/name` → PR |
| **Roadmap** | Shows the project is alive and evolving | `- [ ] Feature A  - [x] Feature B` |
| **GitHub Alerts** | `> [!NOTE]` / `> [!WARNING]` — colored blocks instead of plain quotes | Supported since 2023, rendered on GitHub |
| **Table of Contents** | Section navigation for long READMEs (or inline links) | For READMEs > 5 sections |
| **No © sign** | Don't use the copyright symbol — cleaner and more modern. Author name always links to LinkedIn | `[Maxim Osovsky](https://linkedin.com/in/osovsky). Licensed under CC BY-SA 4.0.` |
| **llms.txt files** | Machine-readable project summary for LLMs — `llms.txt` (short) + `llms-full.txt` (detailed) | [llms.txt standard](https://llmstxt.org/) |
| **CI link checker** | GitHub Actions workflow that auto-checks for dead links and markdown errors on every push | Free, runs on GitHub servers |

---

## ❌ What to Avoid

- **Wall of text** without formatting — nobody reads unformatted prose
- **No image/preview** — unclear what the project looks like
- **Too-long README** without `<details>` for secondary sections
- **No badges** — looks like an unfinished project
- **No Quick Start** — people leave if they can't figure out how to run it
- **Technical docs in README** — move to ARCHITECTURE.md, MANUAL.md
- **Hardcoded secrets** in examples — even `sk_test_...` alarms reviewers
- **No license** — legally unclear whether the code can be used
- **Dead links** — broken links to demo/docs kill trust, verify before pushing
- **© sign** — don't use it, just name + license looks cleaner
- **No llms.txt** — LLMs can't discover or understand the project without machine-readable docs
- **No CI checks** — dead links and broken badges go unnoticed until someone reports them

---

## 🔄 CI: Auto-Check Your README

> Optional but recommended. Add one file to your repo and GitHub will check every README on push — free, no servers needed.

<details>
<summary>📋 Ready-to-use workflow (click to expand)</summary>

Create `.github/workflows/readme-lint.yml`:

```yaml
name: README Lint
on: [push, pull_request]
jobs:
  links:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: lycheeverse/lychee-action@v1
        with:
          args: --verbose *.md
  markdown:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: DavidAnson/markdownlint-cli2-action@v16
        with:
          globs: "*.md"
```

**What it checks:**
- 🔗 Dead links (URLs returning 404)
- 🏷️ Broken badge images
- 📝 Markdown syntax errors
- ✅ Result: green checkmark or red X on your repo page

**Cost:** $0 for public repos, 2 000 free minutes/month for private.

</details>

---

## 📐 Ideal README Structure

```
 1. Centered header + logo
 2. Badges (status, license, stack)
 3. Tagline (1 line)
 4. Inline navigation (Quick Start · Features · Docs)
 5. Preview screenshot / GIF
    ---
 6. 💡 Concept (blockquote + explanation)
    ---
 7. ✨ Features (table)
    ---
 8. 🚀 Quick Start (3 lines of code)
    <details> Advanced setup </details>
    <details> Environment variables </details>
    ---
 9. 🏗️ Tech Stack (table + file tree)
    ---
10. 🗺️ Roadmap (task checklist)
    ---
11. 🤝 Contributing (fork → branch → PR)
    ---
12. 📄 License + author
13. llms.txt + llms-full.txt (root, plain text)
```

---

## 🔗 Useful Resources

| Resource | Description |
|----------|-------------|
| [shields.io](https://shields.io) | Badge generator |
| [Simple Icons](https://simpleicons.org) | Logos for badges |
| [readme.so](https://readme.so) | Visual README builder |
| [GitHub Docs: Formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) | Official documentation |
| [GitHub Alerts](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#alerts) | `[!NOTE]`, `[!WARNING]` etc. |
| [Badgen](https://badgen.net) | shields.io alternative |
| [Contributor Covenant](https://www.contributor-covenant.org) | Code of Conduct standard |
| [llms.txt](https://llmstxt.org/) | Standard for LLM-readable project docs |

---

## 📋 Template

> **Start here** — copy, rename to `README.md`, fill in the `{PLACEHOLDERS}`.

➡️ **[TEMPLATE.md](TEMPLATE.md)**

---

## 🏆 Real-World Examples

Projects built with these guidelines:

| Project | What it is | README |
|---------|-----------|--------|
| **WallPlan** | Multi-year wall calendar generator | [View](https://github.com/maximosovsky/wallplan) |
| **LifeLine** | Lifetime visualization on paper | [View](https://github.com/maximosovsky/lifeline) |
| **DelayedPopup** | Chat-like popup with Stripe payments | [View](https://github.com/maximosovsky/DelayedPopup) |
| **TeleInviter** | Telegram meeting scheduler bot | [View](https://github.com/maximosovsky/teleinviter) |

---

## 🤖 LLM-Ready Docs

| File | Purpose |
|------|---------|
| [llms.txt](llms.txt) | Short project card for LLM discovery |
| [llms-full.txt](llms-full.txt) | Complete guidelines as LLM instruction |
| [README_GUIDELINES.md](README_GUIDELINES.md) | Structured rules for AI-assisted README generation |

---

<div align="center">

## 🗺️ Roadmap

[README audit for all repositories →](ROADMAP.md)

---

## 🤝 Contributing

Fork → `feature/name` → PR

Add your discoveries to the techniques table!

---

## 📄 License

[Maxim Osovsky](https://www.linkedin.com/in/osovsky/). Licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

</div>
