---
object_id: button
name: "🔘 Button"
category: "interaction"
version: "1.0.0"
phase: "lite"
max_instances: 6
zones: ["ACTION", "CORE"]
---

# 🔘 Button Object

## 📖 Plain language description

“Button / Nút — the main clickable action: navigate, submit, or trigger behavior.”

## 🎯 Purpose

Clear CTA with **visible focus**, **touch target ≥44px** where possible.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Nhãn / Label` | string | — | `Continue` | Button text |
| `Biến thể / Variant` | enum | `primary`, `secondary`, `ghost` | `primary` | Style |
| `Hành động / Action` | enum | `link`, `submit`, `custom` | `link` | Behavior type |
| `URL / Href` | url | — | `#` | If action is link |
| `Kích thước / Size` | enum | `sm`, `md`, `lg` | `md` | Size (still meet touch target) |
| `Mở tab mới / New tab` | boolean | — | `false` | For external links |

## 🧭 Explain tab content

```markdown
### Nút là gì? / What is a Button?
A clear invitation: “click this to do the next step.”

### Khi nào dùng? / When to use?
- Buy, Book, Contact
- Download resume
- Go to pricing

### Ví dụ / Example
Primary: “Book a 15-minute call”.

### Mẹo / Tips
- One primary button per section when possible.
- If opening a new tab, warn visually (“opens in new tab”).
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Edit **Label**.
2. Pick **Variant** + **Size**.
3. Choose **Action**; set **URL** if linking.
4. Preview focus ring; **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Button:
1. Use `<button>` for on-page actions; `<a>` for navigation unless framework dictates otherwise.
2. External links: `rel="noopener noreferrer"` when `target="_blank"`.
3. Enforce max_instances: 6.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Focus visible
- [ ] Name/label descriptive
- [ ] Max instances enforced
- [ ] Loading/disabled states if async
- [ ] Sufficient contrast for variant
