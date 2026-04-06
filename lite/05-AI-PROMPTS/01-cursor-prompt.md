---
prompt_id: cursor-sei-lite
agent: "Cursor IDE"
version: "1.0.0"
phase: "lite"
---

# Cursor IDE prompt — SEI-Lite implementation

## 🎯 Context

You are an AI assistant implementing a **lite site builder** or static page **from SEI-Lite markdown specs** in this repository under `lite/`.

## 📚 Reference files

- `lite/01-ENVIRONMENTS/` — four environment templates
- `lite/02-OBJECTS/` — twenty object specs
- `lite/03-OVERLAYS/` — Explain-first overlay
- `lite/04-EXPORT-DEPLOY/` — export and Vercel notes

## 🛠️ Task — generate code from specs

### Step 1: Read environment spec

```text
1. Open the chosen environment file in lite/01-ENVIRONMENTS/.
2. Extract colors, typography tokens, zone layout.
3. Map tokens to your stack (Tailwind theme extension or CSS variables).
```

### Step 2: Read object specs

```text
1. Open only objects allowed by that environment’s “Available objects” table.
2. Implement components matching props (bilingual labels in UI).
3. Enforce per-object max_instances from frontmatter.
```

### Step 3: Overlay system

```text
1. Follow lite/03-OVERLAYS/00-overlay-system.md.
2. Default tab MUST be “🧭 Giải thích”.
3. Implement Try tab live preview + Reset + Apply.
```

### Step 4: Export & deploy

```text
1. Follow lite/04-EXPORT-DEPLOY/01-static-html-export.md for a static dist/.
2. If user wants hosting, follow 02-vercel-deploy.md in the generated project (not inside lite/).
```

## ✅ Quality requirements

- WCAG 2.1 AA intent (see `lite/06-VALIDATION/02-accessibility-checklist.md`).
- Plain language UI copy (Vietnamese and/or English).
- Max **8** objects on canvas for SEI-Lite environments.
- Lighthouse performance target in validation docs.

## 🚀 Begin

Start at Step 1. After theme + zones work, continue without asking unless a requirement is ambiguous.
