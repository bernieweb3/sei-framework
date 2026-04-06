---
object_id: contact-form
name: "✉️ Contact Form"
category: "interaction"
version: "1.0.0"
phase: "lite"
max_instances: 2
zones: ["ACTION", "CORE"]
---

# ✉️ Contact Form Object

## 📖 Plain language description

“Contact Form / Biểu mẫu liên hệ — collect name, email, and message with clear errors.”

## 🎯 Purpose

Accessible lead capture: **labels**, **errors**, **honeypot optional**, no placeholder-only labels.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Tiêu đề / Title` | string | — | `Contact me` | Heading text |
| `Trường / Fields` | multiselect | `name`, `email`, `message`, `phone` | `name,email,message` | Included inputs |
| `Nút gửi / Submit label` | string | — | `Send` | Button text |
| `Endpoint / Action URL` | url | — | `""` | Where form posts (implementation) |
| `Thông báo thành công / Success message` | string | — | `Thanks! We’ll reply soon.` | After submit |

## 🧭 Explain tab content

```markdown
### What is a Contact Form?
A simple way for visitors to message you without opening email manually.

### When to use?
- Service bookings
- Project inquiries
- Support requests

### Real example
Name + Email + Message → sends to your inbox or backend.

### Tips
- Ask only what you need (fewer fields = more completions).
- Show errors next to the field, not only color.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Set **Title** and **Submit label**.
2. Toggle **Fields**.
3. Try invalid email in preview to see error pattern.
4. **Apply** saves configuration.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Contact Form:
1. Associate labels with inputs via `for`/`id`.
2. Show `aria-invalid` + text on errors.
3. Enforce max_instances: 2.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Labels present for all fields
- [ ] Keyboard submit works
- [ ] Max instances enforced
- [ ] Success/failure messaging accessible
- [ ] Spam basics documented (rate limit, honeypot, captcha policy)
