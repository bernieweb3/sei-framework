---
object_id: analytics
name: "📈 Analytics"
category: "utility"
version: "1.0.0"
phase: "lite"
max_instances: 1
zones: ["TOOL"]
---

# 📈 Analytics Object

## 📖 Plain language description

“Analytics / Phân tích — privacy-minded event hooks for builder actions (not required for static export).”

## 🎯 Purpose

Define **events** implementations may track: `overlay_opened`, `cta_click`, `export_completed`. **No secrets in specs.**

## 🔧 Props

| Prop name (UI) | Type | Options | Default | Description |
|----------------|------|---------|---------|-------------|
| `Bật / Enabled` | boolean | — | `false` | Master switch |
| `Nhà cung cấp / Provider` | enum | `none`, `plausible`, `custom` | `none` | Integration style |
| `Endpoint tùy chỉnh / Custom endpoint` | url | — | `""` | Server endpoint (env-driven in code) |
| `Ẩn danh / Anonymize IP` | boolean | — | `true` | Policy flag (provider-dependent) |
| `Sự kiện / Events` | multiselect | built-ins | `overlay_opened,cta_click,export_completed` | Enabled events |

## 🧭 Explain tab content

```markdown
### What is Analytics?
A way to learn what people use—without being creepy.

### When to use?
- After launch, to see drop-offs
- To measure “time to first export” in product analytics

### Real example
Count how many users finish export in <15 minutes.

### Tips
- Prefer privacy-friendly providers.
- Never paste API keys into markdown—use environment variables in generated apps only.
```

## ⚡ Try tab content

```markdown
### Interactive sandbox

1. Toggle **Enabled**.
2. Pick **Provider** (documentation mode in lite).
3. Select **Events** to log.
4. **Apply** saves spec; real wiring happens in implementation.

[Live Preview Area]
[Reset] [Áp dụng]
```

## 🤖 AI agent instructions

```text
For Analytics:
1. Do not embed secrets; instruct `process.env` / platform env for keys.
2. Enforce max_instances: 1.
3. Default overlay tab: Explain.
```

## ✅ Validation checklist

- [ ] No hardcoded tokens in generated code from specs
- [ ] Cookie banner policy referenced if needed (locale law)
- [ ] Max instances enforced
- [ ] Events documented and testable
- [ ] Opt-out respected if product requires it
