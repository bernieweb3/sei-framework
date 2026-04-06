---
object_id: share
name: "📤 Share"
category: "utility"
version: "1.0.0"
phase: "lite"
max_instances: 2
zones: ["TOOL", "ACTION"]
---

# 📤 Share Object

## 📖 Plain language description

“Share / Chia sẻ — copy link or native share for the current page.”

## 🎯 Purpose

Low-friction sharing with **Web Share API** fallback to **copy**.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Nhãn / Label` | string | — | `Share` | Button text |
| `Tiêu đề / Share title` | string | — | `""` | Share sheet title |
| `Mô tả / Share text` | string | — | `""` | Optional description |
| `URL / Canonical URL` | url | — | `""` | Defaults to current page in app |
| `Hiển thị / Style` | enum | `button`, `icon` | `button` | Presentation |

## 🧭 Explain tab content

```markdown
### What is Share?
Helps visitors send your page to someone else quickly.

### When to use?
- After a strong quote or portfolio piece
- Launch pages
- Event invites

### Real example
Tap Share → Messages with link + title.

### Tips
- Always test “copy link” fallback on desktop.
- Don’t surprise-share; require a click.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Set **Label** and optional **Share title/text**.
2. Optionally override **Canonical URL** in preview.
3. Click **Share** (simulated) or **Copy**.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Share:
1. Use Web Share when secure context + support; else copy + toast/announcement.
2. Enforce max_instances: 2.
3. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Keyboard accessible
- [ ] Success announced to AT on copy
- [ ] Max instances enforced
- [ ] Shared URL is canonical when SEO matters
- [ ] No clipboard access without gesture
