---
object_id: list
name: "📋 List"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 4
zones: ["CORE", "PROGRESSION", "ACTION"]
---

# 📋 List Object

## 📖 Plain language description

“List / Danh sách — bullets or numbered items for steps, features, or links.”

## 🎯 Purpose

Structured scanning with proper list semantics (`ul`/`ol`).

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Các mục / Items` | lines | — | `[]` | One item per line |
| `Loại / Type` | enum | `bullet`, `numbered` | `bullet` | List style |
| `Mật độ / Density` | enum | `compact`, `comfortable` | `comfortable` | Line height |
| `Biểu tượng / Icon` | enum | `none`, `check` | `none` | Optional bullet flavor |

## 🧭 Explain tab content

```markdown
### What is a List?
A simple way to show multiple points without a long paragraph.

### When to use?
- 3–7 features
- Step-by-step onboarding
- Quick facts

### Real example
1. Book a call
2. Share your goals
3. Get a draft in 48 hours

### Tips
- Parallel wording (“verb first”) reads best.
- Avoid 15+ items—split into sections.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Type **Items** (one per line).
2. Choose **Type** (bullet/numbered).
3. Pick **Density**.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For List:
1. Map to semantic lists; don’t fake lists with divs.
2. Enforce max_instances: 4.
3. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Correct list role/elements in export
- [ ] Readable line length
- [ ] Max instances enforced
- [ ] Icons don’t replace semantics
- [ ] Focus order preserved if items are interactive
