---
object_id: search-bar
name: "🔎 Search Bar"
category: "interaction"
version: "1.0.0"
phase: "lite"
max_instances: 2
zones: ["TOOL", "CORE"]
---

# 🔎 Search Bar Object

## 📖 Plain language description

“Search Bar / Thanh tìm kiếm — filter gallery/items client-side or send query to backend.”

## 🎯 Purpose

Search UX with **label**, **clear button**, and debounced input (implementation detail).

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Nhãn / Label` | string | — | `Search` | Accessible label |
| `Gợi ý / Placeholder` | string | — | `Try “blue”` | Hint only (not a label) |
| `Chế độ / Mode` | enum | `client`, `server` | `client` | Where filtering happens |
| `Tham số / Query param` | string | — | `q` | For server mode URLs |
| `Trễ / Debounce ms` | number | — | `200` | Input delay |

## 🧭 Explain tab content

```markdown
### What is a Search Bar?
A quick filter—typed text narrows what you show.

### When to use?
- Product grid
- Portfolio filtering (titles/tags)
- FAQ list (lite)

### Real example
Type “photo” to show only photo projects.

### Tips
- Always provide a real **Label**, not only placeholder.
- Announce “no results” accessibly.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Set **Label** + **Placeholder**.
2. Choose **Mode** (client preview might use sample data).
3. Adjust **Debounce** if laggy.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Search Bar:
1. Connect input with visible label.
2. Client mode: filter without full page reload when possible.
3. Enforce max_instances: 2.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Labeled input
- [ ] Results/update region for screen readers (implementation)
- [ ] Max instances enforced
- [ ] Esc clears or closes as applicable
- [ ] No search on single key choke (debounce)
