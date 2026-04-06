---
object_id: code-block
name: "💻 Code Block"
category: "content"
version: "1.0.0"
phase: "lite"
max_instances: 4
zones: ["CORE", "TOOL"]
---

# 💻 Code Block Object

## 📖 Plain language description

“Code Block / Khối mã — show a snippet with optional language label for developers or tutorials.”

## 🎯 Purpose

Display monospace code with **copy button** (optional) and **syntax label**.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Mã / Code` | string | — | `""` | Source text |
| `Ngôn ngữ / Language` | string | — | `plaintext` | Label only (lite) |
| `Chủ đề / Theme` | enum | `light`, `dark` | `dark` | Background style |
| `Nút sao chép / Copy button` | boolean | — | `true` | Show copy control |
| `Bọc dòng / Wrap lines` | boolean | — | `false` | Wrap long lines |

## 🧭 Explain tab content

```markdown
### What is a Code Block?
Shows a piece of code or config so visitors can copy it accurately.

### When to use?
- Install commands
- API examples
- Embed snippets for portfolios

### Real example
`npm create vite@latest`

### Tips
- Don’t paste secrets (API keys).
- Keep snippets short; link to repo for full files.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Paste **Code**.
2. Set **Language** label.
3. Toggle **Copy** and **Wrap**.
4. **Apply** saves.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Code Block:
1. Escape content for HTML export; use `<pre><code>`.
2. Copy button should announce success to screen readers.
3. Enforce max_instances: 4.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Code is escaped safely in HTML
- [ ] Copy works keyboard-only
- [ ] Max instances enforced
- [ ] Horizontal scroll available when wrap off
- [ ] Contrast OK in both themes
