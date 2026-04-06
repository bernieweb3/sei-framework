---
object_id: table
name: "📊 Table"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 3
zones: ["CORE", "PROGRESSION"]
---

# 📊 Table Object

## 📖 Plain language description

“Table / Bảng — compare plans, sizes, or skills in rows and columns.”

## 🎯 Purpose

Data comparison with **header cells** and responsive overflow.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Tiêu đề cột / Column headers` | csv-line | — | `Feature,A,B` | Header row |
| `Hàng / Rows` | csv-lines | — | `[]` | One CSV line per row |
| `Kiểu / Style` | enum | `simple`, `striped` | `simple` | Visual style |
| `Chú thích / Caption` | string | — | `""` | Table caption (recommended) |

## 🧭 Explain tab content

```markdown
### What is a Table?
A grid for side-by-side comparison—great when paragraphs would hide the differences.

### When to use?
- Pricing tiers (lite)
- Size chart
- Skill levels

### Real example
Caption: “Plan comparison” with columns Free / Pro.

### Tips
- Keep columns ≤4 for mobile readability.
- Provide **Caption** for screen readers.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Enter **Column headers**.
2. Add a few **Rows**.
3. Pick **Style** and optional **Caption**.
4. Preview scroll on small screens; **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Table:
1. Use `<table>`, `<thead>`, `<tbody>`, `<th scope="col">`.
2. Wrap with horizontal scroll on narrow viewports.
3. Enforce max_instances: 3.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Header cells are `<th>`
- [ ] Caption present when table is meaningful
- [ ] Max instances enforced
- [ ] Mobile overflow accessible (scroll + focus)
- [ ] Zebra stripes don’t harm contrast
