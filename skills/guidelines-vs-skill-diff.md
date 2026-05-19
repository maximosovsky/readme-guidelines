# Сравнение: readme-guidelines ↔ github-readme-crafter-skill

## Что есть в guidelines, но пропущено в skill

| # | Элемент из guidelines | Где в guidelines | Что делать со skill |
|---|----------------------|------------------|---------------------|
| 1 | **GitHub Alerts** (`> [!NOTE]`, `> [!WARNING]`) | Техника в таблице "What to Use" | Добавить в Hard rules: использовать alerts для важных примечаний |
| 2 | **Animated GIF / video** | Техника в таблице "What to Use" | Расширить "Preview image": требовать GIF для интерактивных проектов |
| 3 | **CI link checker** (workflow `.github/workflows/readme-lint.yml`) | Отдельная секция с готовым YAML | Добавить шаг: "Предложи добавить CI workflow для проверки ссылок" |
| 4 | **GitHub About section** (Description, URL, Topics) | Техника в таблице "What to Use" | Добавить в Hard rules: заполнять About = tagline, topics = keywords |
| 5 | **Templates** (TEMPLATE.md, TEMPLATE-minimal.md) | Секция "Templates" | Добавить шаг: выбирать template под проект (full vs minimal) |
| 6 | **Real-World Examples** | Секция с 5 примерами | Добавить в Resources ссылки на примеры |
| 7 | **PROMPTS.md** | Секция "LLM-Ready Docs" | Добавить в Resources |
| 8 | **README_GUIDELINES.md** как отдельный файл | Секция "LLM-Ready Docs" | Уточнить, что читать этот файл если он есть в контексте |
| 9 | **Horizontal dividers** (`---`) | Техника в таблице "What to Use" | Добавить в Hard rules: разделять основные секции `---` |
| 10 | **No llms.txt** в "What to Avoid" | Anti-pattern | Добавить в Anti-patterns: отсутствие llms.txt |

---

## Что есть в skill, но не в guidelines (это нормально — skill расширяет)

| # | Элемент из skill | Зачем нужно |
|---|-----------------|-------------|
| 1 | **When to use** триггеры | AI понимает, когда активировать скилл |
| 2 | **Steps 1–8** пошагово | AI следует алгоритму, а не интуиции |
| 3 | **Audit pass** с чеклистом | Самопроверка перед выдачей результата |
| 4 | **Anti-patterns (skill will refuse)** | Жёсткие запреты — AI откажется делать плохо |
| 5 | **Related skills** | Навигация на смежные скиллы |
| 6 | **Validation checklist** | Как человек проверит, что скилл работает |
| 7 | **Language = project language** | Правило выбора языка (ru/en) |

---

## Различия в формулировках одного и того же

| Тема | Как в guidelines | Как в skill | Статус |
|------|-----------------|-------------|--------|
| Концепция | Blockquote `>` с философией | "Concept blockquote" — почему проект существует | ✅ Ок, но skill уже конкретнее |
| Quick Start | "3 lines of code" | "max 3 shell commands" | ✅ Ок, эквивалентно |
| Env vars | В `<details>` | В `<details>`, >2 vars обязательно | ✅ Ок, skill конкретнее |
| License | "No © sign, link to LinkedIn" | Hard rule: No `©`, use `[Author](LinkedIn)` | ✅ Ок, skill формализовал |
| Badges | "Bright colored badges" | "2–4 shields.io badges for stack/version/license/status" | ✅ Ок, skill конкретнее |
| Roadmap | "Shows project is alive" | Checklist `- [x] Done` / `- [ ] Planned` | ✅ Ок, skill конкретнее |
| Table of contents | "For READMEs > 5 sections" | "Inline anchor links enough for shorter ones" | ✅ Ок, эквивалентно |

---

## Рекомендации: что дополнить в skill

### 1. Добавить в Steps (после шага 8):
```markdown
9. **Suggest CI setup.** If user maintains repo long-term, offer `.github/workflows/readme-lint.yml` from guidelines to auto-check dead links.
10. **Remind about GitHub About.** Tell user to set: Description = tagline, Website = demo URL, Topics = tech keywords.
```

### 2. Добавить в Hard rules:
- **Horizontal dividers:** Separate major sections with `---`.
- **GitHub Alerts:** Use `> [!NOTE]` / `> [!WARNING]` for important callouts instead of plain blockquotes.
- **GitHub About:** Set repo About section after pushing README.

### 3. Добавить в Anti-patterns:
- No `llms.txt` + `llms-full.txt` in repo root.
- No CI checks for dead links.
- No GitHub About section filled.

### 4. Добавить в Resources:
- `https://github.com/maximosovsky/readme-guidelines/blob/main/TEMPLATE.md`
- `https://github.com/maximosovsky/readme-guidelines/blob/main/TEMPLATE-minimal.md`
- `https://github.com/maximosovsky/readme-guidelines/blob/main/PROMPTS.md`

### 5. Уточнить Step 2:
```markdown
2. **Read guidelines.** If `maximosovsky/readme-guidelines` or `README_GUIDELINES.md` is available in context, read it. Prefer `README_GUIDELINES.md` for structured AI rules. Otherwise use the hard rules below.