---
object_id: image-card
name: "🖼️ Image Card"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 6
zones: ["CORE", "PROFILE"]
---

# 🖼️ Image Card Object

## 📖 Plain language description

“Image Card / Thẻ hình — show one photo with optional caption; great for heroes and portraits.”

## 🎯 Purpose

Display a single image responsively with **alt text** for accessibility.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Hình ảnh / Image URL` | url | — | `""` | Image source |
| `Mô tả ảnh / Alt text` | string | — | `""` | Screen reader description (required for meaningful images) |
| `Chú thích / Caption` | string | — | `""` | Optional visible caption |
| `Tỷ lệ / Aspect` | enum | `auto`, `1:1`, `4:3`, `16:9` | `auto` | Cropping frame |
| `Bo góc / Radius` | enum | `none`, `md`, `full` | `md` | Corner rounding |

## 🧭 Explain tab content

```markdown
### What is an Image Card?
One focused picture with optional caption—like a framed photo on a wall.

### When to use?
- Profile photo
- Product hero image
- A single “proof” screenshot

### Real example
Alt text: “Alex smiling at a laptop in a bright office.”

### Tips
- Write alt text like you describe the photo to a friend on a phone call.
- If purely decorative, mark decorative in implementation (empty alt + aria-hidden rules per platform).
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Paste an **Image URL** (or pick from asset library if your app has one).
2. Add **Alt text**—preview should warn if missing for non-decorative images.
3. Tune **Aspect** and **Radius**.
4. **Apply** saves; **Reset** clears inputs.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
When the user picks Image Card:
1. Require alt text unless user marks image as decorative.
2. Use responsive `img`/`picture` patterns; avoid layout shift (width/height hints).
3. Enforce max_instances: 6.
4. Overlay default tab: Explain.
```

## ✅ Validation checklist

- [ ] Alt text rule documented and enforced in UI
- [ ] Captions don’t duplicate alt unless intentional
- [ ] Max instances enforced
- [ ] Images lazy-load where appropriate
- [ ] Contrast for caption text on background
