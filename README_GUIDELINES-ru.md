# Принципы красивого README на GitHub

## ✅ Что использовать

| Приём | Что делает | Пример |
|-------|-----------|--------|
| **Центрированный заголовок** | `<div align="center">` — логотип + название по центру, создаёт «обложку» | ⏳ LifeLine / 🔍 xyzz.me |
| **Shields.io бейджи** | Яркие цветные плашки со статусом, лицензией, стеком | `![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react)` |
| **Emoji в заголовках секций** | Визуальная навигация — глаз цепляется за иконки | 💡 Concept · ✨ Features · 🚀 Quick Start |
| **Tagline (слоган)** | Одна жирная строка под названием — суть проекта за 1 предложение | *"See your entire life on paper"* |
| **Превью-картинка** | Сразу показывает, как выглядит продукт | `<img src="preview.png" width="600">` |
| **Таблицы фич** | Структурированный список возможностей, легко сканировать | Feature \| Description |
| **Collapsible секции** | `<details>` — прячут второстепенную info (env vars, build, лекции) | Не перегружают README |
| **Блок-цитата** | `>` — философия / концепция проекта, визуально выделяется | *"Lines and structures are a language..."* |
| **Горизонтальные разделители** | `---` между секциями — чёткое визуальное разделение | |
| **ASCII-дерево структуры** | Мгновенный обзор архитектуры в коде | `client/ ├── pages/` |
| **Inline навигация** | Ссылки-якоря под заголовком — быстрый доступ к секциям | `Quick Start · Features · Docs` |
| **Animated GIF / видео** | Демонстрация работы лучше скриншота — показывает flow | `![demo](demo.gif)` |
| **Contributing секция** | Привлекает контрибьюторов, задаёт стандарт: fork → branch → PR | Fork → `feature/name` → PR |
| **Roadmap** | Показывает, что проект живой и развивается | `- [ ] Feature A  - [x] Feature B` |
| **GitHub Alerts** | `> [!NOTE]` / `> [!WARNING]` — цветные блоки вместо обычных цитат | Поддержка с 2023, рендерятся на GitHub |
| **Table of Contents** | Навигация по секциям для длинных README (или inline-ссылки) | Для README > 5 секций |
| **Без знака ©** | Не использовать символ копирайта — чище и современнее. Имя автора — всегда ссылка на LinkedIn | `[Maxim Osovsky](https://linkedin.com/in/osovsky). Licensed under CC BY-SA 4.0.` |
| **GitHub About** | Описание + URL + Topics в секции About репо (⚙️) — влияет на поиск и первое впечатление | Description = слоган, Topics = `react`, `calendar` и т.д. |

## ❌ Чего избегать

- **Основной `README.md` не на английском** — README всегда на английском. Переводы НЕ создаём автоматически: `README-<lang>.md` (с переключателем языка) добавляем только по явному запросу
- **Стена текста** без форматирования — никто не читает сплошной текст
- **Нет картинки/превью** — не понятно, как выглядит проект
- **Слишком длинный README** без `<details>` для второстепенных секций
- **Нет бейджей** — выглядит как незаконченный проект
- **Нет Quick Start** — люди уходят, если не понятно, как запустить
- **Техническая документация в README** — выносить в ARCHITECTURE.md, MANUAL.md
- **Захардкоженные секреты** в примерах — даже `sk_test_...` смущает ревьюеров
- **Нет лицензии** — юридически непонятно, можно ли использовать код
- **Dead links** — битые ссылки на demo/docs убивают доверие, проверять перед пушем
- **Знак ©** — не использовать, просто имя + лицензия выглядит чище
- **Пустая секция About** — нет описания, URL и Topics. Репо выглядит заброшенным, не появляется в поиске

## 📐 Структура идеального README

```
 1. Центрированный заголовок + логотип
 2. Бейджи (статус, лицензия, стек)
 3. Слоган (1 строка)
 4. Переключатель языка (если есть перевод): [🇷🇺 Русская версия](README-ru.md) ↔ [🇬🇧 English version](README.md)
 5. Inline навигация (Quick Start · Features · Docs)
 6. Превью-скриншот / GIF
    ---
 7. 💡 Concept / Идея (блок-цитата + пояснение)
    ---
 8. ✨ Features (таблица)
    ---
 9. 🚀 Quick Start (3 строки кода)
    <details> Продвинутая настройка </details>
    <details> Environment variables </details>
    ---
10. 🏗️ Tech Stack (таблица + дерево файлов)
    ---
11. 🗺️ Roadmap (чеклист планов)
    ---
12. 🤝 Contributing (fork → branch → PR)
    ---
13. 📄 License + автор
```

## 🔗 Полезные ресурсы

- [shields.io](https://shields.io) — генератор бейджей
- [Simple Icons](https://simpleicons.org) — логотипы для бейджей
- [readme.so](https://readme.so) — визуальный конструктор README
- [GitHub Docs: Basic formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [GitHub Alerts syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#alerts) — `[!NOTE]`, `[!WARNING]` и др.
- [Badgen](https://badgen.net) — альтернатива shields.io, быстрее
- [Contributor Covenant](https://www.contributor-covenant.org) — стандарт Code of Conduct для open-source
