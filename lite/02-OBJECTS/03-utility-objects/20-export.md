---
object_id: export
name: "📦 Export"
category: "utility"
version: "1.0.0"
phase: "lite"
max_instances: 1
zones: ["TOOL", "ACTION", "PROGRESSION"]
---

# 📦 Export Object

## 📖 Plain language description

“Export / Xuất — start static HTML export or open deploy flow (Vercel per `04-EXPORT-DEPLOY`).”

## 🎯 Purpose

Bridge from editor to **ship**: triggers `export_completed` analytics when done.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Nhãn / Label` | string | — | `Export site` | Primary CTA label |
| `Định dạng / Format` | enum | `zip-html`, `vercel` | `zip-html` | Output path |
| `Ghi chú / Notes` | string | — | `""` | Post-export instructions for user |
| `Bao gồm / Include assets` | boolean | — | `true` | Images/fonts bundling |
| `Nén / Minify` | boolean | — | `true` | Basic minification toggle |

## 🧭 Explain tab content

```markdown
### Cái gì là Export? / What is Export?
It packages what you built so you can host it or hand it to someone.

### Khi nào cần? / When?
- You’re happy with the preview
- You want a real URL (deploy)
- You want a ZIP backup

### Ví dụ / Example
Export ZIP → upload to any static host.

### Mẹo / Tips
- Preview one more time on mobile width.
- Keep filenames simple (ASCII) to avoid host issues.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Choose **Format**.
2. Toggle **Include assets** + **Minify**.
3. Click **Run export** (simulation).
4. Read **Notes** aloud to user; **Apply** saves defaults.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Export:
1. Follow `lite/04-EXPORT-DEPLOY/01-static-html-export.md` for HTML output rules.
2. Fire `export_completed` on success (if Analytics enabled).
3. Enforce max_instances: 1.
4. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] Export output opens locally without broken relative paths
- [ ] User sees success/failure clearly
- [ ] Max instances enforced
- [ ] No secrets in exported folder
- [ ] Large assets warned before export
