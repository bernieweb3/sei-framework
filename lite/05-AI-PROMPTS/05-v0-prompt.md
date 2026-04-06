---
prompt_id: v0-sei-lite
agent: "v0"
version: "1.0.0"
phase: "lite"
---

# v0 prompt — SEI-Lite implementation

## Single prompt

Design a **UI kit + page** for a “SEI-Lite builder”:

- Left: zone outline (PROFILE / CORE / ACTION / TOOL / PROGRESSION).
- Center: canvas with max **8** object cards.
- Right: inspector with **tabs**: 🧭 Giải thích (selected by default) and ⚡ Thử.

Theme: import color tokens from `lite/01-ENVIRONMENTS/01-garden-environment.md` **or** let user toggle environment in a select; update tokens accordingly.

Components must map to:

- Text Block, Image Card, Button, Gallery (subset is OK for first iteration if you note assumptions).

Accessibility: focus rings, 16px body text, sensible `aria` on dialog.

## Deliverable format

- Generate component code appropriate to v0’s stack.
- Include short notes referencing SEI-Lite markdown paths for future expansion.
