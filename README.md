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
