---
object_id: gallery
name: "🖼️ Gallery"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 2
zones: ["CORE", "PROGRESSION"]
---

# 🖼️ Gallery Object

## 📖 Plain language description

“Gallery / Bộ sưu tập — a grid of images (and optional captions) for projects or products.”

## 🎯 Purpose

Show **multiple images** with keyboard-navigable lightbox (if implemented).

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Mục / Items` | list | — | `[]` | Each item: `{ imageUrl, alt, caption? }` |
| `Cột / Columns` | enum | `2`, `3`, `4` | `3` | Desktop grid columns |
| `Khoảng cách / Gap` | enum | `tight`, `normal`, `relaxed` | `normal` | Spacing |
| `Chế độ xem / Lightbox` | boolean | — | `true` | Open larger view on click |

## 🧭 Explain tab content

```markdown
### What is a Gallery?
A neat grid that showcases several photos at once.

### When to use?
- Portfolio projects
- Product photos
- Event highlights

### Real example
Three project screenshots with short captions.

### Tips
- Keep alt text unique per image.
- Limit items for speed (lite suggests ≤12 images per gallery instance).
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Add 3–6 **Items** (URL + alt).
2. Pick **Columns** and **Gap**.
3. Toggle **Lightbox**.
4. **Apply** saves layout.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Gallery:
1. Enforce max_instances: 2.
2. Lazy-load images; preserve aspect ratios.
3. Lightbox: trap focus while open; ESC closes.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Each image has alt (or decorative handling)
- [ ] Keyboard usable in lightbox
- [ ] Max instances enforced
- [ ] Reasonable item count for performance
- [ ] Visible focus states
