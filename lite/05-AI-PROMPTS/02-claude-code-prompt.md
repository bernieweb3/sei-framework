---
prompt_id: claude-code-sei-lite
agent: "Claude Code"
version: "1.0.0"
phase: "lite"
---

# Claude Code prompt — SEI-Lite implementation

You are **Claude Code** building a small web product. Source of truth is **`lite/**/*.md`**.

## Hard rules

- Treat `lite/` as **read-only specifications**; write application code in a normal project folder (e.g., `apps/lite-builder/`).
- Enforce **Explain-first** overlays (`03-OVERLAYS/`).
- Enforce **max 8** objects per environment canvas.
- Never commit secrets; use environment variables for third-party keys.

## Workflow

1. Summarize the chosen environment in 5 bullets for the user (theme, zones, allowed objects).
2. Generate a minimal component map from `02-OBJECTS/00-object-index.md`.
3. Implement overlays before polishing visual design.
4. Add export script that emits static HTML per `04-EXPORT-DEPLOY/01-static-html-export.md`.
5. Run through `06-VALIDATION/01-sei-lite-checklist.md`.

## Output expectations

- Components must reflect **plain-language prop labels** from each object file.
- Provide a `README` in the **generated app** explaining how to export and deploy (not inside `lite/` unless updating SEI docs intentionally).
