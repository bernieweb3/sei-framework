---
object_id: settings
name: "⚙️ Settings"
category: "utility"
version: "1.0.0"
phase: "lite"
max_instances: 1
zones: ["TOOL", "PROFILE"]
---

# ⚙️ Settings Object

## 📖 Plain language description

“Settings / Cài đặt — theme, language, and density preferences for your mini-site.”

## 🎯 Purpose

User preferences stored in **localStorage** or similar; must respect **system theme** and **`prefers-reduced-motion`**.

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Chế độ màu / Theme` | enum | `system`, `light`, `dark` | `system` | Color scheme |
| `Ngôn ngữ / Language` | enum | `en`, `vi`, `auto` | `auto` | UI language |
| `Mật độ / Density` | enum | `cozy`, `compact` | `cozy` | Spacing scale |
| `Giảm chuyển động / Reduce motion` | enum | `system`, `on`, `off` | `system` | Motion preference |
| `Hiển thị / Placement` | enum | `icon`, `menu` | `icon` | How users open settings |

## 🧭 Explain tab content

```markdown
### What is Settings?
A small control panel so visitors can make the page easier to read.

### When to use?
- Dark mode for night reading
- Larger spacing for readability
- Language switching (if you implement copy sets)

### Real example
Theme: System → follows phone light/dark automatically.

### Tips
- Default to **system**—less guessing.
- Never hide critical content behind settings-only states.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Flip **Theme** and watch instant preview.
2. Toggle **Density**.
3. Try **Reduce motion** = on (animations should soften).
4. **Apply** saves preferences.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Settings:
1. Persist non-sensitive prefs only; document keys (`sei-lite-theme`, etc.).
2. Enforce max_instances: 1.
3. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] System theme tracks OS changes
- [ ] Motion preference honored
- [ ] Max instances enforced
- [ ] Settings UI keyboard accessible
- [ ] No reliance on cookies for essentials
