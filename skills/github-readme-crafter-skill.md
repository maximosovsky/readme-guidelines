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
- User needs README for a new repo

## Steps

1. **Gather inputs.** Ask for critical items, infer the rest from context:
   - **Always ask:** Project name, one-line description, main features
   - **Infer from repo files:** Tech stack from `package.json`, `requirements.txt`, `Cargo.toml`, etc. Quick start commands from scripts/build files. Env vars from `.env.example`. Project structure from file tree.
   - **Ask only if not inferrable:** Author name, LinkedIn URL, roadmap items, license choice
   - **Default:** License = CC BY-SA 4.0 if not specified

2. **Read guidelines.** Check `maximosovsky/readme-guidelines` first — it contains the latest authoritative standards. If a local `README_GUIDELINES.md` is also available in context, apply it as project-specific overrides. Otherwise use the hard rules below.

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
   - Add 2–4 shields.io badges: stack, version, license. Always use `style=for-the-badge` and `&logo=` parameter.
    - License badge: `![License](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey?style=for-the-badge&logo=creativecommons)`

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
   - `## 🚀 Quick Start` — max 4 shell commands to go from zero to running. Include env vars in `<details>` block inside this section if needed.
   - `## 🏗️ Tech Stack` — table: Layer | Technology. Follow with ASCII file tree in `<details>` block inside this section.
   - `## 🗺️ Roadmap` — checklist: `- [x] Done` / `- [ ] Planned`
   - `## 🤝 Contributing` — Fork → `feature/name` → PR
   - `## 📄 License` — `[Author](LinkedIn). Licensed under [CC BY-SA 4.0](...).`

7. **Audit pass.** Before returning, verify:

   **Structure & Visuals**
   - [ ] Centered header with badges
   - [ ] Tagline under title
   - [ ] Concept blockquote present
   - [ ] `---` horizontal dividers between every major section
   - [ ] Env vars hidden in `<details>`

    **Content & Correctness**
    - [ ] Quick Start ≤ 4 commands
    - [ ] No `©` symbol anywhere
    - [ ] License links to author LinkedIn
    - [ ] Roadmap uses `- [x]` / `- [ ]` syntax
    - [ ] Language is English unless user explicitly requested otherwise
    - [ ] Section headings remain in English even if prose is translated

   **Links & Extras**
   - [ ] All external links are HTTPS and alive (spot-check)
   - [ ] `llms.txt` and `llms-full.txt` offered or generated
   - [ ] GitHub About section set (Description, Topics) — always in English
   - [ ] GitHub About section verified live (gh repo view or web check)

8. **Return the complete README.md** as a single code block. Offer to also write `llms.txt` and `llms-full.txt` if the user wants LLM-ready docs.

9. **Suggest CI setup.** If the user maintains the repo long-term, offer adding `.github/workflows/readme-lint.yml` from the guidelines to auto-check dead links.

10. **Set GitHub About.** Use `gh repo edit` to set: Description = English tagline from README, Website = demo URL, Topics = 5–10 lowercase tech keywords. If `gh` is unavailable, instruct the user to set it manually. Verify it exists with `gh repo view` or by checking the repo page. Do not mark the task complete until About is confirmed set.

## Hard rules

If the user explicitly requests to violate a hard rule, comply but append a `> [!WARNING]` blockquote explaining which guideline was overridden and why it is discouraged.

- **Centered header is mandatory.** `<div align="center">` with emoji + title + badges + tagline.
- **Quick Start = 4 commands max.** `git clone ... && cd ... && npm install && npm run dev` counts as 4 logical steps. If more setup is needed, hide it in `<details>`.
- **Environment variables always in `<details>`**. Never show `.env` setup inline if there are more than 2 variables.
- **No `©` symbol.** Use `[Author Name](https://linkedin.com/in/...). Licensed under [CC BY-SA 4.0](...).`
- **No wall of text.** Every section must have formatting: tables, lists, code blocks, or collapsible `<details>`.
- **Preview image or GIF.** If user has none, insert placeholder: `<img src="docs/preview.png" width="600">` and note "add screenshot here".
- **Badges for every major dependency.** If project uses React, Node, Python, PostgreSQL — each gets a badge. If a technology has no logo in shields.io/simpleicons, use a generic text badge: `![Tech](https://img.shields.io/badge/Tech_Name-grey?style=for-the-badge)`. Never omit a badge for a listed dependency.
- **Table of contents** for READMEs with > 5 top-level sections (`##` headings). Inline anchor links under header are enough for shorter ones.
- **Horizontal dividers.** Separate every major section with `---`.
- **GitHub Alerts.** Use `> [!NOTE]` / `> [!WARNING]` for important callouts instead of plain blockquotes where appropriate.
- **GitHub About section (always in English).** After pushing README, set repo About: Description = English tagline, Website = demo URL, Topics = 5–10 lowercase keywords. Use `gh repo edit` if CLI is available. If About is missing or empty, create it. Do not proceed until About is confirmed set.
- **Language.** Default to English. If the user writes in another language, this does NOT constitute an explicit request — always ask "Should the README be in English or [language]?". Only switch if confirmed. If the user explicitly requests another language, translate all prose (tagline, concept, descriptions) but keep section headings and technical terms in English: `Quick Start`, `Features`, `Tech Stack`, `Contributing`, `License`, etc.

## Anti-patterns (skill will refuse)

When refusing, explain why the request violates guidelines and suggest the correct approach.

**Content Quality**
- Writing a README without badges
- Using `©` in the license section
- Leaving "TODO" or "coming soon" in features
- Generic taglines like "A modern web application" — must be specific
- Putting more than 4 commands in Quick Start without `<details>`
- Writing README prose in non-English without explicit user request
- Translating section headings (`Quick Start`, `Features`, etc.) to non-English

**Structure**
- Writing technical architecture docs inside README (move to `ARCHITECTURE.md`)
- No `<details>` for secondary info (env vars, build steps, file tree)
- No roadmap or no contributing section

**Setup & Automation**
- Hardcoding secrets in `.env.example` values (use `YOUR_TOKEN_HERE`)
- No `llms.txt` + `llms-full.txt` in repo root
- No CI checks for dead links
- No GitHub About section filled (Description, URL, Topics)
- GitHub About section written in non-English
- GitHub About section not verified after setting

## Resources

- `https://github.com/maximosovsky/readme-guidelines` — full guidelines with templates
- `https://github.com/maximosovsky/readme-guidelines/blob/main/TEMPLATE.md` — full README template
- `https://github.com/maximosovsky/readme-guidelines/blob/main/TEMPLATE-minimal.md` — minimal template for small projects
- `https://github.com/maximosovsky/readme-guidelines/blob/main/PROMPTS.md` — ready-to-use LLM prompts
- `https://shields.io` — badge generator
- `https://simpleicons.org` — logos for badges
- `https://llmstxt.org` — llms.txt standard

## Related skills

- `tech-writer` — for writing ARCHITECTURE.md, API docs, manuals
- `repo-auditor` — for checking an existing repo against guidelines

## Validation checklist for human reviewers

Before marking this skill as "good", verify with these prompts:

1. **"Write a README for a Python FastAPI + PostgreSQL todo API"** — check centered header, badges, Quick Start ≤4 commands, no ©.
2. **"Rewrite this README: [paste a wall-of-text README]"** — check it added formatting, tables, collapsible sections.
3. **"Audit my README"** on a README missing badges — check it flags the issue and proposes fixes.
4. **"Write README for a Python CLI tool"** — check language consistency, emoji headers.
5. **Manual contradiction check** — scan the generated skill for: (a) any rule that directly contradicts another rule, (b) ambiguous phrasing like "if needed" without defining the condition, (c) requirements that depend on external tools not guaranteed to exist.
