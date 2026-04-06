---
object_id: divider
name: "➖ Divider"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 8
zones: ["CORE", "PROGRESSION", "ACTION"]
---

# ➖ Divider Object

## 📖 Plain language description

“Divider / Đường phân cách — a visual break between sections.”

## 🎯 Purpose

Separate content without adding noise; keep **semantic** separation (avoid “layout-only hr abuse”).

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Kiểu / Style` | enum | `line`, `dashed`, `spaced` | `line` | Visual style |
| `Độ dày / Thickness` | enum | `thin`, `medium` | `thin` | Line weight |
| `Màu / Color` | color | — | `#E2E8F0` | Line color |
| `Biên / Margin` | enum | `sm`, `md`, `lg` | `md` | Vertical spacing |
| `Nhãn / Label` | string | — | `""` | Optional centered text |

## 🧭 Explain tab content

```markdown
### What is a Divider?
A subtle line or gap that tells the eye: “new section starts here.”

### When to use?
- Between long sections
- After a hero and before details
- Before a footer CTA

### Real example
A thin line before “Contact”.

### Tips
- Don’t stack many dividers—use whitespace instead.
- If you add a **Label**, keep it short.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Pick **Style** + **Thickness**.
2. Adjust **Color** (watch contrast on background).
3. Try optional **Label**.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Divider:
1. Prefer `<hr>` with an accessible name only when label exists; otherwise presentational rules per platform.
2. Enforce max_instances: 8.
3. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Not overused in one page
- [ ] Label (if any) readable
- [ ] Max instances enforced
- [ ] Works in high contrast themes
- [ ] Doesn’t break heading outline
