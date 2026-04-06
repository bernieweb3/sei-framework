---
object_id: video-player
name: "▶️ Video Player"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 3
zones: ["CORE", "ACTION"]
---

# ▶️ Video Player Object

## 📖 Plain language description

“Video Player / Trình phát video — embed a hosted video (YouTube/Vimeo/etc.) or a direct file URL.”

## 🎯 Purpose

Show video with **caption support**, **keyboard controls**, and **poster** where applicable.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Nguồn / Source` | url | — | `""` | Embed URL or file URL |
| `Loại / Provider` | enum | `embed`, `file` | `embed` | Playback mode |
| `Tiêu đề / Title` | string | — | `""` | Accessible name |
| `Ảnh bìa / Poster` | url | — | `""` | Thumbnail before play (file mode) |
| `Tự phát / Autoplay` | boolean | — | `false` | Muted autoplay only if platform allows |

## 🧭 Explain tab content

```markdown
### What is the Video Player?
It places a video in your page so visitors can watch without leaving.

### When to use?
- Product demo
- Short introduction (“About me”)
- Tutorial clip

### Real example
Title: “2-minute product tour”.

### Tips
- Avoid loud autoplay; if autoplay, keep muted and respect reduced motion policies.
- Always provide a title for screen reader context.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Paste **Source**.
2. Choose **Provider**.
3. Set **Title** (recommended).
4. Preview play/pause; **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Video Player:
1. Prefer privacy-enhanced embed parameters when available (platform-specific).
2. Provide keyboard-focusable play overlay for custom skins.
3. Enforce max_instances: 3.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Title/aria-label present
- [ ] Autoplay policy safe (muted + user-gesture where needed)
- [ ] Max instances enforced
- [ ] Captions documented if host provides them
- [ ] No seizure-inducing flashes in custom controls
