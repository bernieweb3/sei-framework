---
object_id: text-block
name: "📝 Text Block"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 5
zones: ["CORE", "ACTION", "PROFILE", "PROGRESSION"]
---

# 📝 Text Block Object

## 📖 Plain language description

“Text Block / Khối chữ — add readable paragraphs, headings, or short labels people can scan quickly.”

## 🎯 Purpose

Let users add and edit visible text on the page while keeping **minimum 16px** body size for accessibility.

## 🔧 Props (plain language — EN + VN labels)

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Nội dung / Content` | string | — | `""` | Visible text (supports line breaks) |
| `Cỡ chữ / Size` | enum | `small`, `medium`, `large` | `medium` | Visual scale (still ≥16px for body) |
| `Màu chữ / Text color` | color | hex / rgb | `#2D3748` | Foreground |
| `Căn lề / Align` | enum | `left`, `center`, `right` | `left` | Alignment |
| `Kiểu đậm / Weight style` | enum | `normal`, `bold`, `italic` | `normal` | Emphasis |

## 🧭 Explain tab content

```markdown
### What is a Text Block? / Khối chữ là gì?
It is the simplest way to add words to your page: intro, explanation, or a short label.

### When to use? / Khi nào dùng?
- Personal intro / Giới thiệu bản thân
- Product or service summary / Mô tả sản phẩm
- A short “what happens next” note / Nói rõ bước tiếp theo

### Real example / Ví dụ
“Hi, I’m Alex. I help small teams ship clear websites in under two weeks.”

### Tips / Mẹo
- Keep blocks short (3–6 lines) unless it’s an article section.
- Use `large` sparingly for titles only.
- Prefer left alignment for long reading text.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Type in **Content / Nội dung**.
2. Choose **Size / Cỡ chữ** and **Align / Căn lề**.
3. Watch the **Live preview** update.
4. Click **Áp dụng / Apply** to save; **Reset** restores defaults.

[Live Preview Area]
[Reset] [Áp dụng / Apply]
```

## 🤖 AI agent instructions

```text
When the user picks Text Block:
1. Show the props table with bilingual labels.
2. Open overlay: default tab Explain (Giải thích).
3. Enforce max_instances: 5 on the lite canvas.
4. Generate markup with utility classes (e.g., Tailwind) but ensure computed body font-size ≥ 16px.
5. If content is empty, show non-destructive placeholder copy in the editor only—not in exported static HTML unless user chose “publish placeholder”.
```

## ✅ Validation checklist

- [ ] Props names are plain language (VN and/or EN)
- [ ] Explain tab uses simple wording
- [ ] Try tab describes preview + reset + apply
- [ ] Max instances enforced
- [ ] Body text ≥ 16px
