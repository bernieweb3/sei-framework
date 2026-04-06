---
object_id: spacer
name: "⬜ Spacer"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 8
zones: ["CORE", "ACTION", "TOOL", "PROFILE", "PROGRESSION"]
---

# ⬜ Spacer Object

## 📖 Plain language description

“Spacer / Khoảng trống — controlled vertical (or horizontal) space between objects.”

## 🎯 Purpose

Tune rhythm; prefer tokens over magic numbers when generating CSS.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Hướng / Direction` | enum | `vertical`, `horizontal` | `vertical` | Spacer axis |
| `Kích cỡ / Size` | enum | `xs`, `sm`, `md`, `lg`, `xl` | `md` | Step scale |
| `Hiển thị / Visible on` | enum | `all`, `desktop-only`, `mobile-only` | `all` | Responsive visibility |
| `Ghi chú / Note` | string | — | `""` | Editor-only note (not exported) |

## 🧭 Explain tab content

```markdown
### What is a Spacer?
Breathing room. It prevents sections from feeling cramped.

### When to use?
- After a dense gallery
- Before a primary button
- Around a hero image

### Real example
`md` vertical spacer between intro and features.

### Tips
- Use fewer spacers by fixing layout grid gaps first.
- **Note** is for you in the editor—keep it out of public HTML.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Choose **Direction**.
2. Pick **Size** and watch preview shift.
3. Optional: **Visible on** breakpoint behavior.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Spacer:
1. Implement as margin/padding utilities; avoid empty interactive elements.
2. Do not export **Note** to static HTML.
3. Enforce max_instances: 8.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] No focusable spacer elements
- [ ] Responsive behavior matches prop
- [ ] Max instances enforced
- [ ] Doesn’t cause overflow bugs
- [ ] Exported HTML stays clean (no editor notes)
