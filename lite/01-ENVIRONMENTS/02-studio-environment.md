---
environment_id: studio
name: "🎨 Creative Studio"
version: "1.0.0"
phase: "lite"
max_objects: 8
zones: ["CORE", "ACTION", "TOOL", "PROGRESSION", "PROFILE"]
---

# 🎨 Creative Studio Environment

## 📖 Narrative

“This is your studio wall: big visuals, bold statements, and experiments on display.”

_Đây là tường studio của bạn: hình ảnh lớn, lời nhắn mạnh mẽ, và những thử nghiệm được trưng bày._

## 🎨 Theme specification

### Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--primary` | `#6D28D9` | Actions, focus |
| `--secondary` | `#F5F3FF` | Surfaces |
| `--accent` | `#F59E0B` | Highlights |
| `--text` | `#111827` | Body text |

### Typography

| Token | Value | Usage |
|-------|-------|-------|
| `--font-heading` | `DM Sans, Inter, system-ui, sans-serif` | Headings |
| `--font-body` | `Inter, system-ui, sans-serif` | Body |
| `--font-size-base` | `16px` | Minimum body size |

### Layout

```text
[PROFILE]     [TOOLS]
  Artist       Search

        [CORE]
      Showcase

[ACTIONS]   [PROGRESSION]
 CTA         Case studies / steps
```

## 📦 Available objects (max 8)

| ID | Object | Zone | Description |
|----|--------|------|-------------|
| 01 | Text Block | CORE | Statement / manifesto |
| 03 | Video Player | CORE | Showreel or clip |
| 04 | Gallery | CORE | Project grid |
| 08 | Code Block | CORE | Snippet / creative tech |
| 12 | Button | ACTION | Book / contact |
| 13 | Link | ACTION | External portfolio |
| 15 | Search Bar | TOOL | Filter projects (optional) |
| 16 | Settings | TOOL | Theme or density |

## 🤖 AI agent instructions

```text
When the user selects the Studio environment:
1. Apply the purple/amber theme with generous whitespace OR intentional asymmetry (pick one and stay consistent).
2. Prioritize CORE as a “hero collage”: gallery and/or video first.
3. Allow ACTION zone to hold one primary and one secondary CTA max.
4. Enforce max 8 objects.
5. Default overlay tab must be Explain (Giải thích) for every object.
```

## ✅ Validation checklist

- [ ] Theme tokens applied
- [ ] Five zones present
- [ ] Max 8 objects enforced
- [ ] Motion (if any) respects `prefers-reduced-motion`
- [ ] Focus visible on interactive elements
