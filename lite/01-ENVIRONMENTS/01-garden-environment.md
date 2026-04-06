---
environment_id: garden
name: "🌿 Minimal Garden"
version: "1.0.0"
phase: "lite"
max_objects: 8
zones: ["CORE", "ACTION", "TOOL", "PROGRESSION", "PROFILE"]
---

# 🌿 Minimal Garden Environment

## 📖 Narrative

“Step into your garden. Each object is a part of your story—gentle, clear, and easy to tend.”

_Nhấn bước vào khu vườn của bạn. Mỗi vật thể là một phần câu chuyện—nhẹ nhàng, rõ ràng, dễ chăm sóc._

## 🎨 Theme specification

### Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--primary` | `#4A7C59` | Main actions, headings |
| `--secondary` | `#F5F5DC` | Backgrounds |
| `--accent` | `#8B4513` | Highlights |
| `--text` | `#2D3748` | Body text |

### Typography

| Token | Value | Usage |
|-------|-------|-------|
| `--font-heading` | `Inter, system-ui, sans-serif` | Headings |
| `--font-body` | `Inter, system-ui, sans-serif` | Body |
| `--font-size-base` | `16px` | Minimum body size (accessibility) |

### Layout

```text
        [PROFILE]
          User

[TOOLS]  [CORE]  [ACTIONS]
Config   Main    Primary

      [PROGRESSION]
        Status
```

## 📦 Available objects (max 8)

| ID | Object | Zone | Description |
|----|--------|------|-------------|
| 01 | Text Block | CORE | Paragraphs and introductions |
| 02 | Image Card | CORE | Featured photo |
| 05 | Quote | CORE | Pull quote / motto |
| 06 | List | CORE | Bullet or numbered list |
| 09 | Divider | CORE | Soft section break |
| 12 | Button | ACTION | Primary action |
| 14 | Nav Menu | TOOL | Simple navigation |
| 17 | Profile | PROFILE | Name, role, portrait |

## 🤖 AI agent instructions

```text
When the user selects the Garden environment:
1. Apply theme colors from the table above.
2. Render five zones according to the layout specification.
3. Load only the objects listed in “Available objects” from the object catalog.
4. If the builder supports drag-and-drop, enable placement within allowed zones.
5. Enforce max 8 objects on the lite canvas.
6. On first load, show the narrative as helper text or a one-time welcome line.
```

## ✅ Validation checklist

- [ ] Theme colors applied correctly
- [ ] Five zones rendered
- [ ] Max 8 objects enforced
- [ ] Narrative displayed on first load (or equivalent onboarding)
- [ ] Accessibility: body text contrast ratio ≥ 4.5:1 for normal text
