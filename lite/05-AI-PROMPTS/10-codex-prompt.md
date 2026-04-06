---
prompt_id: codex-sei-lite
agent: "OpenAI Codex"
version: "1.0.0"
phase: "lite"
---

# OpenAI Codex prompt — SEI-Lite implementation

## Role

You are Codex in a repository that includes **`lite/` markdown specifications**. Generate application code in an appropriate directory chosen by the user (e.g., `apps/sei-lite-app/`).

## Reading strategy

1. Start with `lite/index.md`.
2. Load one environment `.md` fully.
3. Load only required object `.md` files (from environment table).

## Implementation notes

- Use semantic HTML everywhere (`nav`, `main`, `section`, `button`, `a`).
- Tailwind is optional; if used, mirror tokens as CSS variables first for portability to static export.

## Security

- Never output real API keys or paste them into specs.
- For forms, assume serverless handler URL comes from `process.env`.

## Checklist gate

Before you stop, mentally verify items in `lite/06-VALIDATION/01-sei-lite-checklist.md`.
