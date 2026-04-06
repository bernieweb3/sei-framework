---
object_id: quote
name: "💬 Quote"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 4
zones: ["CORE", "PROGRESSION"]
---

# 💬 Quote Object

## 📖 Plain language description

“Quote / Trích dẫn — highlight a testimonial or motto with attribution.”

## 🎯 Purpose

Present quoted text as a **semantic blockquote** with optional cite link.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Trích dẫn / Quote text` | string | — | `""` | Main quote |
| `Tác giả / Author` | string | — | `""` | Who said it |
| `Chức danh / Role` | string | — | `""` | Optional context |
| `Kiểu / Style` | enum | `minimal`, `card`, `large` | `card` | Visual treatment |
| `Liên kết nguồn / Source URL` | url | — | `""` | Optional citation URL |

## 🧭 Explain tab content

```markdown
### What is a Quote?
A emphasized snippet—often social proof or a guiding principle.

### When to use?
- Customer testimonial
- Mission statement excerpt
- Review highlight

### Real example
“Shipping was clear and fast.” — Jamie, small business owner.

### Tips
- Keep quotes short and specific.
- Always attribute when claiming a real person said it.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Enter **Quote text**.
2. Add **Author** + optional **Role**.
3. Choose **Style**.
4. Preview; **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Quote:
1. Use semantic `<blockquote>` + `<cite>` patterns in HTML export.
2. Enforce max_instances: 4.
3. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Attribution visible when author provided
- [ ] Style preserves readability (contrast)
- [ ] Max instances enforced
- [ ] Source URL opens safely (`rel` attributes as needed)
- [ ] Screen reader announces quote appropriately
