---
prompt_id: trae-sei-lite
agent: "Trae IDE"
version: "1.0.0"
phase: "lite"
---

# Trae IDE prompt — SEI-Lite implementation

## Context capsule

SEI-Lite is a **markdown specification framework** under `lite/`. Your job is to produce a working web app **outside** `lite/`.

## Build order

1. Environment picker (4 options) + token preview.
2. Object palette filtered by environment constraints.
3. Inspector modal (Explain / Try) fed by markdown content slices.
4. Serialization model (JSON) for user projects.
5. Export static HTML ZIP.

## Non-functional requirements

- Accessibility: see `lite/06-VALIDATION/02-accessibility-checklist.md`.
- Performance: see `lite/06-VALIDATION/03-performance-checklist.md`.

## Collaboration tip

Commit specs separately from generated app: `feat(lite): ...` vs `feat(app): ...`.
