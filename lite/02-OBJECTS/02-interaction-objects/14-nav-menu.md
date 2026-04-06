---
object_id: nav-menu
name: "🧭 Nav Menu"
category: "interaction"
version: "1.0.0"
phase: "lite"
max_instances: 2
zones: ["TOOL", "PROFILE"]
---

# 🧭 Nav Menu Object

## 📖 Plain language description

“Nav Menu / Menu điều hướng — top links to sections or pages, mobile-friendly.”

## 🎯 Purpose

Site navigation with **landmark** semantics and **responsive collapse**.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Mục / Items` | list | — | `[]` | `{ label, href \| hash }` |
| `Logo chữ / Brand text` | string | — | `My Site` | Text logo |
| `Căn / Align` | enum | `left`, `center`, `space` | `space` | Desktop layout |
| `Nút mobile / Mobile toggle label` | string | — | `Menu` | Accessible toggle name |
| `Sticky / Dính trên cùng` | boolean | — | `false` | Sticky header |

## 🧭 Explain tab content

```markdown
### What is a Nav Menu?
The map at the top: where to go without scrolling endlessly.

### When to use?
- 3–6 main sections
- Mini sites and one-pagers

### Real example
Home · Work · About · Contact.

### Tips
- Keep item labels short.
- Ensure mobile menu traps focus while open (if modal pattern).
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Add **Items** (label + target).
2. Set **Brand text**.
3. Preview mobile toggle.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Nav Menu:
1. Wrap with `<nav aria-label="Primary">` (or localized).
2. Mobile: toggle `aria-expanded`.
3. Enforce max_instances: 2.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Landmark + label
- [ ] Keyboard operable mobile menu
- [ ] Max instances enforced
- [ ] Current page indication (aria-current) when applicable
- [ ] Sufficient touch targets
