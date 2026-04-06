---
prompt_id: lovable-sei-lite
agent: "Lovable"
version: "1.0.0"
phase: "lite"
---

# Lovable prompt — SEI-Lite implementation

Paste this as your **system-level project brief** in Lovable. Attach or paste key specs from `lite/`.

## Mission

Build a **friendly mini-site builder** that: (1) loads one SEI-Lite environment, (2) places up to **8** objects, (3) opens an **Explain-first** inspector for each object, (4) exports static HTML.

## Design

- Pull colors/typography from the selected environment markdown frontmatter + tables.
- Large tap targets, calm spacing—optimize for readers **40–45** and international users.

## Constraints

- Default overlay tab: **Giải thích / Explain**.
- Props UI uses labels from object specs (VN + EN where provided).
- Avoid jargon in empty states.

## Shipping

- Provide **Export ZIP** flow matching `lite/04-EXPORT-DEPLOY/01-static-html-export.md`.
- Optional: **Deploy** button that documents Vercel steps (`02-vercel-deploy.md`), without embedding tokens.
