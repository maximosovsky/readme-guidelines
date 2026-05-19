---
name: readme-crafter
description: Generate a professional GitHub README following the readme-guidelines standard. Produces centered headers, shields.io badges, feature tables, quick start, tech stack, roadmap, and license sections. Use when the user asks to write, rewrite, improve, or audit a README.md.
---

# README Crafter

Generate GitHub READMEs that follow proven structure from `readme-guidelines` (centered header, badges, tagline, concept, features, quick start, tech stack, roadmap, contributing, license).

## When to use

- User says "write a README for my project"
- User says "rewrite README" or "improve README"
- User pastes a draft README and asks to upgrade it
- User asks to audit an existing README against best practices
- User needs README in Russian or English for a new repo

## Steps

1. **Gather inputs.** Ask or infer:
   - Project name + one-line description
   - Tech stack (languages, frameworks, runtime versions)
   - Main features (3–8 bullets)
   - Quick start commands (clone → install → run)
   - Environment variables if any
   - Project structure / file tree
   - Roadmap items (completed + planned)
   - Author name + LinkedIn URL
   - License (default: CC BY-SA 4.0)

2. **Read guidelines.** If `maximosovsky/readme-guidelines` or `README_GUIDELINES.md` is available in context, read it for the latest rules. Otherwise use the hard rules below.

3. **Build the header block.**
   ```markdown
   <div align="center">

   # {emoji} {Project Name}

   ![{Tech}](https://img.shields.io/badge/...)
   ![License](...)

   **{One-line tagline}**

   </div>
   ```
   - Pick an emoji relevant to the domain (🔐 for auth, 🤖 for AI, 📊 for data, etc.)
   - Add 2–4 shields.io badges: stack, version, license, status.

4. **Write the concept blockquote.**
   ```markdown
   > {Why does this project exist? What problem does it solve in 1–2 sentences?}
   ```

5. **Add inline navigation.**
   ```markdown
   <div align="center">
     <a href="#-quick-start">Quick Start</a> ·
     <a href="#-features">Features</a> ·
     <a href="#-tech-stack">Tech Stack</a> ·
     ...
   </div>
   ```

6. **Compose sections in order:**
   - `## 💡 Concept` — expanded explanation, target audience, what makes it unique
   - `## ✨ Features` — table with emoji prefixes: `| 🔐 Feature | Description |`
   - `## 🚀 Quick Start` — max 3 shell commands to go from zero to running
   - `## ⚙️ Environment Variables` — inside `<details>` block, table with Required/No
   - `## 🏗️ Tech Stack` — table: Layer | Technology
   - `## 📁 Project Structure` — inside `<details>` block, ASCII tree
   - `## 🗺️ Roadmap` — checklist: `- [x] Done` / `- [ ] Planned`
   - `## 🤝 Contributing` — Fork → `feature/name` → PR
   - `## 📄 License` — `[Author](LinkedIn). Licensed under [CC BY-SA 4.0](...).`

7. **Audit pass.** Before returning, verify:
   - [ ] Centered header with badges
   - [ ] Tagline under title
   - [ ] Concept blockquote present
   - [ ] Quick Start ≤ 3 commands
   - [ ] Env vars hidden in `<details>`
   - [ ] No `©` symbol anywhere
   - [ ] License links to author LinkedIn
   - [ ] Roadmap uses `- [x]` / `- [ ]` syntax
   - [ ] All external links are HTTPS and alive (spot-check)

8. **Return the complete README.md** as a single code block. Offer to also write `llms.txt` and `llms-full.txt` if the user wants LLM-ready docs.

## Hard rules

- **Centered header is mandatory.** `<div align="center">` with emoji + title + badges + tagline.
- **Quick Start = 3 commands max.** `git clone ... && cd ... && npm install && npm run dev` counts as 3 logical steps. If more setup is needed, hide it in `<details>`.
- **Environment variables always in `<details>`**. Never show `.env` setup inline if there are more than 2 variables.
- **No `©` symbol.** Use `[Author Name](https://linkedin.com/in/...). Licensed under [CC BY-SA 4.0](...).`
- **Language = project language.** If the project is Russian-facing, write README in Russian. If global/English-facing, write in English. Mixed is acceptable only for code terms.
- **No wall of text.** Every section must have formatting: tables, lists, code blocks, or collapsible `<details>`.
- **Preview image or GIF.** If user has none, insert placeholder: `<img src="docs/preview.png" width="600">` and note "add screenshot here".
- **Badges for every major dependency.** If project uses React, Node, Python, PostgreSQL — each gets a badge.
- **Table of contents** for READMEs with > 5 sections. Inline anchor links under header are enough for shorter ones.

## Anti-patterns (skill will refuse)

- Writing a README without badges
- Putting more than 3 commands in Quick Start without `<details>`
- Using `©` in the license section
- Leaving "TODO" or "coming soon" in features
- Hardcoding secrets in `.env.example` values (use `YOUR_TOKEN_HERE`)
- Writing technical architecture docs inside README (move to `ARCHITECTURE.md`)
- No `<details>` for secondary info (env vars, build steps, file tree)
- Generic taglines like "A modern web application" — must be specific
- No roadmap or no contributing section

## Resources

- `https://github.com/maximosovsky/readme-guidelines` — full guidelines with templates
- `https://shields.io` — badge generator
- `https://simpleicons.org` — logos for badges
- `https://llmstxt.org` — llms.txt standard

## Related skills

- `tech-writer` — for writing ARCHITECTURE.md, API docs, manuals
- `repo-auditor` — for checking an existing repo against guidelines

## Validation checklist for human reviewers

Before marking this skill as "good", verify with these prompts:

1. **"Write a README for a Python FastAPI + PostgreSQL todo API"** — check centered header, badges, Quick Start ≤3 commands, no ©.
2. **"Rewrite this README: [paste a wall-of-text README]"** — check it added formatting, tables, collapsible sections.
3. **"Audit my README"** on a README missing badges — check it flags the issue and proposes fixes.
4. **"Write README in Russian for a Telegram bot on aiogram"** — check language consistency, emoji headers.
5. Open `SKILL.md` in VS Code with Chat Customizations Evaluations extension — run "Analyze Prompt", expect 0 contradictions and 0 semantic ambiguities.