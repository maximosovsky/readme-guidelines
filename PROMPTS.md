# 🤖 LLM Prompts for README Generation

Ready-to-use prompts for AI-assisted README creation. Copy, paste, adapt.

---

## 1. Generate a README from scratch

```
You have the file README_GUIDELINES.md loaded. Generate a complete README.md
for my project:

- Name: {project name}
- What it does: {one sentence}
- Tech stack: {e.g. React, Node.js, PostgreSQL}
- Key features: {list 3-5 features}

Follow the structure and formatting rules exactly. Use shields.io badges
with style=for-the-badge. Add emoji to section headers. Include a Quick Start
section with 3 lines of code. End with license:
[Maxim Osovsky](https://linkedin.com/in/osovsky). Licensed under CC BY-SA 4.0.
```

---

## 2. Audit an existing README

```
You have the file README_GUIDELINES.md loaded. Here is my current README:

{paste your README}

Compare it against the guidelines. List what's missing, what should be
removed, and what should be reformatted. Give me a score from 1-10.
```

---

## 3. Generate llms.txt files

```
You have the file README_GUIDELINES.md loaded. Generate llms.txt (short card,
~15 lines) and llms-full.txt (detailed, 50-200 lines) for my project:

- Name: {project name}
- URL: {project url}
- Author: {name} ({wikidata url})
- License: CC BY-SA 4.0
- Features: {paste features or describe the project}
- Architecture: {paste file list or describe}
```

---

## 4. Improve a feature table

```
Here are my project's features as bullet points:

{paste bullets}

Convert them into a markdown table with columns: Feature | Description.
Make descriptions concise (1 line each). Add emoji to feature names
where appropriate.
```

---

## 5. Generate badges

```
Generate shields.io badges (style=for-the-badge) for this tech stack:
{e.g. React 18, TypeScript, Node.js 20, PostgreSQL, TailwindCSS 3}

Use appropriate colors and logos from simpleicons.org.
Format: ![Name](url)
```

---

## 6. Create a minimal README

```
You have TEMPLATE-minimal.md loaded. Generate a short README for a small
project:

- Name: {name}
- What it does: {one sentence}
- Tech: {language/framework}
- How to run: {command}

Keep it under 40 lines. No collapsible sections, no file tree.
```

---

## Tips

- Always load `README_GUIDELINES.md` or `llms-full.txt` as context first
- Specify your language if you want non-English output
- Ask for iterations: *"Make the tagline punchier"*, *"Add 2 more features"*
- For large projects, generate section by section
