# Architecture — readme-guidelines

## Overview

readme-guidelines — чеклист, шаблон и LLM-reference для создания красивых GitHub README. Два языка: EN и RU. Содержит шаблоны (minimal + full), промпты для AI-генерации, рекомендации по заполнению About-секции репозитория.

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Format | Markdown |
| CI | GitHub Actions (README linting) |
| LLM | llms.txt / llms-full.txt (LLM reference) |

## Project Structure

```
├── README.md                    # Main README (EN)
├── README-ru.md                 # README (RU)
├── README_GUIDELINES.md         # Detailed guidelines (EN)
├── README_GUIDELINES-ru.md      # Detailed guidelines (RU)
├── TEMPLATE.md                  # Full README template
├── TEMPLATE-minimal.md          # Minimal README template
├── PROMPTS.md                   # AI prompts for README generation
├── ROADMAP.md                   # Development roadmap
├── llms.txt                     # LLM short reference
├── llms-full.txt                # LLM extended reference
└── LICENSE                      # CC BY-SA 4.0
```

## Key Concepts

- **Content-only repo** — нет кода, только документация
- **Dual language** — все документы на EN и RU
- **LLM-ready** — `llms.txt` и `llms-full.txt` для AI-помощников
- **Templates** — готовые шаблоны для быстрого старта
- **Prompts** — `PROMPTS.md` с инструкциями для AI-генерации README
- **About section** — рекомендации по Description, Website, Topics
