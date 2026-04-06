---
tab_id: explain
name: "Giải thích (Explain)"
version: "1.0.0"
phase: "lite"
---

# Explain tab — specification

## Goals

- Reduce anxiety for users **40–45** and **international** readers.
- Teach **meaning** before exposing **controls**.

## Required sections (per object)

| Section | Required | Notes |
|---------|----------|-------|
| “What is this?” / “… là gì?” | ✅ | 2–3 sentences max |
| “When to use?” / “Khi nào dùng?” | ✅ | 3 bullets typical |
| “Real example” / “Ví dụ” | ✅ | Quoted/plain snippet |
| “Tips” / “Mẹo” | ✅ | 2–4 bullets |
| Estimated time | ✅ | e.g., “~2 phút / ~2 min” |

## Voice and tone

- **Short sentences.** One idea per line.
- **Bilingual headings** where the product serves VN + global users.
- Avoid framework names unless the user already chose a stack.

## Localization pattern

At minimum, provide:

- Vietnamese **or** English body in each object file.
- SEI-Lite encourages **both** in headings for high-sensitivity UI (buttons, errors).

## Accessibility

- Tab role: `role="tab"`, selected state `aria-selected`.
- Panel: `role="tabpanel"` tied with `aria-labelledby`.

## 🤖 AI agent instructions

```text
When rendering Explain tab from markdown:
1. Convert headings to h3/h4 consistently (avoid skipping levels).
2. Keep bullets ≤ 7 per list.
3. Surface "Estimated time" near the top on first open (optional UX enhancement).
```

## ✅ Validation checklist

- [ ] All required sections present for the object
- [ ] No wall of text (> ~120 words without a break)
- [ ] Reading level ~Grade 6–8 in English
- [ ] No shame language (“obvious”, “just easy”)
