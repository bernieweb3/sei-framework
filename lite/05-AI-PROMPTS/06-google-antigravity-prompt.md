---
prompt_id: antigravity-sei-lite
agent: "Google Antigravity"
version: "1.0.0"
phase: "lite"
---

# Google Antigravity prompt — SEI-Lite implementation

You are an autonomous coding agent. The specification corpus is at `lite/**/*.md` (markdown only).

## Plan

1. Parse the environment YAML frontmatter for IDs like `garden`, `studio`, `shop`, `portfolio`.
2. Build a feature list from `02-OBJECTS/00-object-index.md`.
3. Implement incrementally: shell UI → overlay → one object end-to-end → scale to 20 readers.

## Guardrails

- **Explain-first** default tab everywhere.
- **Max 8** total objects on the lite canvas.
- English + Vietnamese UI strings where object specs show both.

## Verification

Run or describe tests aligned with `lite/06-VALIDATION/01-sei-lite-checklist.md` before marking tasks complete.
