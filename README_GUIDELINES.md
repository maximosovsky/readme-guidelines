# README Guidelines — LLM Reference

Use these rules when generating or reviewing a GitHub README.

## Structure (in order)

1. `<div align="center">` — project emoji + name as `# heading`, shields.io badges (`style=for-the-badge`), bold one-line tagline, `</div>`
2. Blockquote `>` — project concept / philosophy, 1–2 sentences
3. `<div align="center">` — preview image or GIF (`width="600"`), inline nav links (`Quick Start · Features · Docs`), `</div>`
4. `---`
5. `## 💡 Concept` — expanded explanation of the idea
6. `---`
7. `## ✨ Features` — markdown table: Feature | Description
8. `---`
9. `## 🚀 Quick Start` — 3–5 lines of code to run the project. Use `<details>` for advanced config and env variables
10. `---`
11. `## 🏗️ Tech Stack` — markdown table: Layer | Technology. Follow with ASCII file tree in a code block
12. `---`
13. `## 🗺️ Roadmap` — checklist: `- [ ]` planned, `- [x]` done
14. `---`
15. `## 🤝 Contributing` — Fork → `feature/name` → PR
16. `---`
17. `## 📄 License` — `[Author Name](https://linkedin.com/in/profile). Licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).`
18. `llms.txt` + `llms-full.txt` — plain text files at root for LLM discoverability
19. **GitHub About** — fill in the repo About section (⚙️ gear icon): `Description` = tagline from README, `Website` = live demo URL, `Topics` = 5–10 lowercase keywords for discoverability

## Formatting Rules

- Use `---` horizontal dividers between every major section
- Use emoji prefixes on all `##` headings
- Badges: always `style=for-the-badge` with `&logo=` parameter
- License badge: `![License](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey?style=for-the-badge)`
- Author name in license: always a clickable link to LinkedIn, never GitHub
- Never use the © copyright symbol
- Use `<details><summary>` for secondary info (env vars, build steps, advanced config)
- Feature lists: prefer tables over bullet lists
- File tree: use ASCII art in a fenced code block
- If README has > 5 sections: add inline nav links under the header
- If project has a screenshot: embed it centered, `width="600"` or smaller
- About section: Description = README tagline, Website = demo URL, Topics = 5–10 lowercase keywords (tech stack + domain)

## Anti-Patterns (never do)

- Wall of text without formatting
- No preview image
- No badges
- No Quick Start section
- Hardcoded secrets in examples (even `sk_test_...`)
- Missing license
- Dead links — verify all URLs
- Technical architecture docs in README — use separate ARCHITECTURE.md
- © symbol — use plain `Author Name. Licensed under ...`
- Empty About section — no description, no URL, no topics. Repo looks abandoned and won't appear in search

## Badge Examples

```markdown
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-20-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![License](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey?style=for-the-badge)
```

## License Block Template

```markdown
## 📄 License

[Author Name](https://www.linkedin.com/in/profile/). Licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
```
