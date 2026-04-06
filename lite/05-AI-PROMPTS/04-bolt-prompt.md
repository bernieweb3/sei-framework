---
prompt_id: bolt-sei-lite
agent: "Bolt.new"
version: "1.0.0"
phase: "lite"
---

# Bolt.new prompt — SEI-Lite implementation

## Prompt body (paste into Bolt)

Build a **static-first** mini-site builder using the SEI-Lite specifications:

1. Read environment markdown for theme + 5 zones + allowed object IDs.
2. Implement a canvas with drag placeholders (if easy) or ordered stack.
3. Each object opens a **modal** with tabs: **Explain** (default) and **Try**.
4. Object props panels must use **plain-language labels** from the markdown tables.
5. Cap total objects at **8** per SEI-Lite rules.
6. Add **Export** to download `dist/` folder structure per `lite/04-EXPORT-DEPLOY/01-static-html-export.md`.

## Tech hints

- Prefer React + Vite or Next static export—Bolt chooses, but keep JS small.
- Use CSS variables for tokens from the environment file.

## QA

Before finishing, verify keyboard Tab order in overlays and forms.
