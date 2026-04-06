---
doc_id: static-html-export
name: "Static HTML Export"
version: "1.0.0"
phase: "lite"
---

# Static HTML export — specification

## Output structure

```text
dist/
├── index.html
├── assets/
│   ├── app.css
│   └── app.js
└── media/          (optional bundled images)
```

## HTML requirements

- Valid document outline: **one** `h1` per page unless multi-page export.
- Language attribute: `<html lang="en">` or `lang="vi"` based on user choice.
- Include skip link: “Skip to content”.

## CSS requirements

- Use design tokens from active environment spec (`--primary`, etc.).
- **16px** minimum body font.
- Dark mode: respect `prefers-color-scheme` if Settings object uses `system`.

## JavaScript requirements (minimal)

- Progressive enhancement: core content readable without JS.
- If Settings persists theme: use `localStorage` with namespaced keys.

## Paths

- Prefer **relative** paths (`./assets/app.css`) for portability.
- Avoid absolute filesystem paths in HTML.

## Media

- Copy remote images only if license/rights are cleared (product policy).
- Preserve `alt` text verbatim from object specs.

## 🤖 AI agent instructions

```text
When generating export:
1. Inline critical CSS optional; default external `app.css`.
2. Minify toggles should not remove `aria-*` attributes.
3. Emit a `robots.txt` stub only if user opts into SEO pack (out of lite scope—document if added).
```

## ✅ Validation checklist

- [ ] No broken relative links
- [ ] Keyboard nav works on menus/forms
- [ ] Images have alt or decorative handling
- [ ] No secrets in HTML/JS
- [ ] `gzip`/`brotli` friendly filenames (no spaces)
