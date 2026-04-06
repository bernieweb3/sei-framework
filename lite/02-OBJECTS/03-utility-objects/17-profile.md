---
object_id: profile
name: "👤 Profile"
category: "utility"
version: "1.0.0"
phase: "lite"
max_instances: 1
zones: ["PROFILE"]
---

# 👤 Profile Object

## 📖 Plain language description

“Profile / Hồ sơ — name, role, portrait, and one-line promise in the PROFILE zone.”

## 🎯 Purpose

Identity anchor for the page; pairs with **Image Card** only if portrait is separate—avoid duplicate portraits.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Tên / Name` | string | — | `Your name` | Display name |
| `Vai trò / Role` | string | — | `""` | Title / occupation |
| `Một dòng / Tagline` | string | — | `""` | Short promise |
| `Ảnh / Avatar URL` | url | — | `""` | Optional round avatar |
| `Liên kết / Social links` | list | — | `[]` | `{ label, url }` small links |

## 🧭 Explain tab content

```markdown
### What is Profile?
The “who is this?” answer at a glance.

### When to use?
- Personal sites
- Consultant landing pages
- Creator mini homepages

### Real example
“Jamie Nguyen — Product designer — I turn messy ideas into shippable UI.”

### Tips
- Tagline should be one line on mobile.
- Limit social links to 3–4 max.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Fill **Name**, **Role**, **Tagline**.
2. Optional **Avatar URL**.
3. Add 2 **Social links** and preview.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Profile:
1. Avatar requires alt text = Name (or decorative handling if duplicated nearby).
2. Enforce max_instances: 1.
3. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Heading level sensible (often h1 for name on home)
- [ ] Social links have visible labels
- [ ] Max instances enforced
- [ ] Works without avatar gracefully
- [ ] Color contrast on tagline
