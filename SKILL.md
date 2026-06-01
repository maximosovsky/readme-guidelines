---
name: readme-guidelines
description: >-
  Write or restyle a project's README to a beautiful, scannable GitHub standard:
  centered header, shields.io badges, tagline, emoji section nav, feature tables,
  collapsible <details>, GitHub Alerts, file tree, roadmap, contributing, license.
  Use when asked to create/improve a README, "make the README pretty", add badges,
  or set up the repo's About section. English-first README.md + optional translated
  README-<lang>.md with a language switcher. Reference stack-agnostic.
---

# Writing a beautiful GitHub README

Turn a bare or messy README into a scannable "cover page" that sells the project in
10 seconds and gives an LLM clean context. Stack-agnostic — the structure is the same
for a PHP library, a React app, or a CLI script.

Canonical checklist, templates and LLM reference live in this repo:
- `README_GUIDELINES.md` — full checklist (✅ use / ❌ avoid / structure) **load this first**
- `llms-full.txt` — same content packed for LLM context
- `TEMPLATE.md` — full README skeleton (apps, libraries)
- `TEMPLATE-minimal.md` — minimal skeleton (scripts, games, experiments)
- `PROMPTS.md` — ready prompts for AI generation

## Before writing — gather facts

Never invent details. Pull them from the actual project:
- **Name, tagline, concept** — what it does in one sentence + why it exists.
- **Tech stack & versions** — for badges and the Tech Stack table (read `package.json`,
  `composer.json`, lockfiles, imports).
- **Run command** — the real install/run steps (verify they work, no dead steps).
- **Repo URL, author, license** — from `git remote -v` and the `LICENSE` file. License is
  chosen by repo type: a **code project → MIT**; a **documentation/content project → CC BY-SA
  4.0**. Use one license that matches what the repo is — don't blend both. Match the badge and
  the License section to the actual `LICENSE` file.
- **Existing assets** — preview image/GIF? If none exists, leave an HTML-comment
  placeholder; never link a non-existent image (dead links kill trust).

## Choose a template

- Library / app / product → `TEMPLATE.md` (full structure below).
- Script / game / prototype → `TEMPLATE-minimal.md` (header + features + quick start + license).

## Structure (full README)

```
 1. Centered header + emoji title          <div align="center">
 2. Badges                                 status · license · stack (shields.io, style=for-the-badge)
 3. Tagline                                one bold line
 4. Language switcher                      [🇷🇺 Русская версия](README-ru.md)  (if translated)
 5. Inline nav                             Quick Start · Features · Tech Stack · Roadmap
 6. Preview image / GIF                    or an HTML-comment placeholder if none
    ---
 7. 💡 Concept                             blockquote + short explanation
 8. ✨ Features                            table (Feature | Description)
 9. 🚀 Quick Start                         3 real commands + <details> for env vars / advanced
10. 🏗️ Tech Stack                         table + <details> ASCII file tree
11. 🗺️ Roadmap                            checklist (done / planned)
12. 🤝 Contributing                        Fork → feature/name → PR
13. 📄 License + author                    author name links to LinkedIn; no © symbol
```

Plus two **root files for LLM discoverability** (mandatory, not part of the rendered
README — see below): `llms.txt` and `llms-full.txt`.

Use GitHub Alerts (`> [!NOTE]`, `> [!WARNING]`) for caveats, and `<details>` to hide
secondary info so the page stays short.

## Language policy (English-first)

Default README output is **English** unless the user asks otherwise.
- Primary file is always **`README.md` in English**.
- A translation goes in **`README-<lang>.md`** (e.g. `README-ru.md`).
- Put a language switcher near the top of **both** files:
  - in `README.md`: `[🇷🇺 Русская версия](README-ru.md)`
  - in `README-ru.md`: `[🇬🇧 English version](README.md)`
- Keep both versions structurally identical when you update one.

## Always generate llms.txt + llms-full.txt

Every project must ship two plain-text files at the repo root so LLMs can discover and
understand it. Omitting them is an anti-pattern.

- **`llms.txt`** — short card (~15 lines): `# Name`, one-line `>` description, `## About`
  paragraph, `Author / URL / License` list, `## Docs` link to the raw `llms-full.txt`.
- **`llms-full.txt`** — detailed reference (50–200 lines): overview, full feature list,
  architecture (file table), technical details, roadmap.

Keep them in sync with the README — when the README changes materially, update both.

## After writing — fill the repo About section

A `README.md` alone is not done. The repo's **About** (⚙️ on GitHub) must be set, or the
repo looks abandoned and won't surface in search:
- **Description** = the README tagline
- **Website** = live demo URL (omit if none)
- **Topics** = 5–10 lowercase keywords (tech stack + domain)

Set it via `gh` (confirm values with the user first — it edits the public repo):

```bash
gh repo edit <owner>/<repo> \
  --description "<tagline>" \
  --add-topic kw1,kw2,kw3,kw4,kw5
```

## Badges

shields.io, `style=for-the-badge`, with a logo where one exists:

```
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)
```

Logos: [simpleicons.org](https://simpleicons.org). Generator: [shields.io](https://shields.io).

## Avoid

- Wall of text with no formatting; no preview; over-long README with no `<details>`.
- No badges, no Quick Start, no license → looks unfinished / legally unclear.
- **Hardcoded secrets in examples** — even `sk_test_...` or a real token/phone/email
  unsettles reviewers. Use obvious placeholders (`+79990000000`, `12345`, `TOKEN=...`).
- Technical docs dumped in README → move to `ARCHITECTURE.md` / `MANUAL.md`.
- `©` symbol — just name + license is cleaner.
- Dead links (demo/docs/images) — verify before finishing.
- Empty About section.

## Quick check before finishing

- [ ] Centered header, badges, tagline, inline nav all present
- [ ] Quick Start commands are real and runnable
- [ ] No hardcoded secrets; placeholders only
- [ ] License matches the actual `LICENSE` file; author links to LinkedIn; no ©
- [ ] No dead links / missing images
- [ ] English `README.md` (+ translation with switcher if requested)
- [ ] `llms.txt` + `llms-full.txt` present at repo root and in sync with the README
- [ ] About section set (Description, Website, Topics) — or proposed to the user
