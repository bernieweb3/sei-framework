---
system_id: overlay-system
name: "Explain-First Overlay System"
version: "1.0.0"
phase: "lite"
---

# 🧭 Explain-first overlay system

## 🎯 Philosophy

**“Hiểu trước — Làm sau.”**  
**“Understand first — act second.”**

Older and international users should **never** land on controls before they know what an object does.

## 📐 Architecture

```text
┌─────────────────────────┐
│   OVERLAY CONTAINER     │
├─────────────────────────┤
│ [🧭 Giải thích] [⚡ Thử]│ ← Tabs
├─────────────────────────┤
│                         │
│   TAB CONTENT AREA      │
│                         │
├─────────────────────────┤
│ [❌ Đóng] [💾 Lưu]      │ ← Actions
└─────────────────────────┘
```

## 📋 Tab specifications

### Tab 1: 🧭 Giải thích (Explain)

**Purpose:** Help the user understand **before** editing.

**Content requirements:**

- Plain language (Vietnamese and/or simple English)
- Avoid unexplained jargon
- Text-based “visual example” (describe what it looks like)
- **Why this matters** (implicit in “When to use?” sections)
- **Estimated time** to complete edits (e.g., “~2 minutes”)

**Template:**

```markdown
### [Object Name] là gì?
[2–3 simple sentences]

### Khi nào dùng?
- Use case 1
- Use case 2
- Use case 3

### Ví dụ thực tế:
"[A short real example]"

### Mẹo hay:
• Tip 1
• Tip 2
• Tip 3
```

### Tab 2: ⚡ Thử ngay (Try)

**Purpose:** Safe practice with live preview.

**Content requirements:**

- Interactive sandbox (inputs tied to preview)
- Real-time preview when possible
- One-click reset
- Save and close
- Validation feedback (inline errors)

**Template:**

```markdown
### Interactive sandbox

[Bước 1: Action]
[Control]

[Bước 2: Action]
[Control]

[Live Preview Area]

[Reset] [Áp dụng / Apply]
```

## 🤖 AI agent instructions

```text
When a user activates any object:
1. Open a modal / drawer overlay.
2. Default selected tab MUST be "🧭 Giải thích".
3. Load Explain and Try bodies from that object’s markdown spec.
4. Support keyboard tab order: tabs → panel → primary actions.
5. Emit overlay_opened { object_id } if analytics is enabled.
6. ESC closes; focus returns to invoking control.
```

## ✅ Validation checklist

- [ ] Default tab is Giải thích / Explain
- [ ] Plain language in Explain
- [ ] Try tab describes sandbox + reset + apply
- [ ] Keyboard navigation works
- [ ] Focus trap while open (modal pattern)
