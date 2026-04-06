---
environment_id: portfolio
name: "👔 Professional Portfolio"
version: "1.0.0"
phase: "lite"
max_objects: 8
zones: ["CORE", "ACTION", "TOOL", "PROGRESSION", "PROFILE"]
---

# 👔 Professional Portfolio Environment

## 📖 Narrative

“A crisp handshake in digital form: who you are, proof of work, and the next step to talk.”

_Một cái bắt tay rõ ràng trên mạng: bạn là ai, bằng chứng công việc, và bước tiếp theo để trao đời._

## 🎨 Theme specification

### Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--primary` | `#1D4ED8` | Links, primary button |
| `--secondary` | `#F8FAFC` | Background |
| `--accent` | `#0F172A` | Headings, emphasis |
| `--text` | `#334155` | Body |

### Typography

| Token | Value | Usage |
|-------|-------|-------|
| `--font-heading` | `Inter, system-ui, sans-serif` | Headings |
| `--font-body` | `Inter, system-ui, sans-serif` | Body |
| `--font-size-base` | `16px` | Minimum body size |

### Layout

```text
        [PROFILE]
       Headline

[TOOL]    [CORE]     [ACTION]
 Nav     Case study   Hire me

      [PROGRESSION]
      Timeline / CV
```

## 📦 Available objects (max 8)

| ID | Object | Zone | Description |
|----|--------|------|-------------|
| 01 | Text Block | CORE | Bio / summary |
| 02 | Image Card | CORE | Headshot or hero |
| 04 | Gallery | CORE | Case studies |
| 07 | Table | CORE | Skills matrix |
| 11 | Contact Form | ACTION | Inquiry |
| 12 | Button | ACTION | Download resume |
| 14 | Nav Menu | TOOL | Sections |
| 19 | Share | TOOL | Share profile link |

## 🤖 AI agent instructions

```text
When the user selects the Professional Portfolio environment:
1. Lead with PROFILE + CORE: name, role, one-paragraph bio, strongest proof.
2. PROGRESSION can show timeline as a simple vertical list (not necessarily a separate object if Text Block + List suffices—keep within 8 objects total).
3. ACTION: one primary “contact” path; secondary may be calendly/link style via Button or Link spec.
4. Enforce max 8 objects.
5. Prefer WCAG AA contrast; avoid light gray on white for body text.
```

## ✅ Validation checklist

- [ ] Contact path tested end-to-end
- [ ] Resume or external links open in safe, labeled way
- [ ] Max 8 objects enforced
- [ ] Heading order is logical (h1 → h2)
- [ ] Images have alt text guidance in object specs
