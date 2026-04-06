---
object_id: link
name: "🔗 Link"
category: "interaction"
version: "1.0.0"
phase: "lite"
max_instances: 10
zones: ["CORE", "ACTION", "TOOL", "PROFILE"]
---

# 🔗 Link Object

## 📖 Plain language description

“Link / Liên kết — inline or standalone text navigation to another page or section.”

## 🎯 Purpose

Predictable navigation with **underline or clear affordance** and **skip-safe external link** behavior.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Văn bản / Text` | string | — | `Learn more` | Anchor text |
| `URL / Href` | url | — | `""` | Destination |
| `Kiểu / Style` | enum | `inline`, `standalone` | `inline` | Presentation |
| `Mở tab mới / New tab` | boolean | — | `false` | External browsing |
| `Đến mục / Hash target` | string | — | `""` | In-page section id |

## 🧭 Explain tab content

```markdown
### What is a Link?
A tap or click that takes you somewhere else—another page, PDF, or section.

### When to use?
- “Read more” after a summary
- Social profiles
- Footer legal pages

### Real example
Text: “View case study” → `/work/shopify-clone`.

### Tips
- Avoid “click here”—use descriptive text.
- For downloads, include file type/size in nearby text when possible.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Set **Text** + **URL** (or **Hash target**).
2. Toggle **New tab** for external examples.
3. Pick **Style**.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Link:
1. If new tab, add accessible hint (visible text or `sr-only`).
2. Combine hash with base path carefully in static export.
3. Enforce max_instances: 10.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Descriptive link text
- [ ] External link security attrs when needed
- [ ] Max instances enforced
- [ ] Visited/focus/hover styles distinct
- [ ] Works with keyboard
