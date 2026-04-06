---
doc_id: export-overview
name: "Export & Deploy Overview"
version: "1.0.0"
phase: "lite"
---

# Export & deploy — overview (SEI-Lite)

## Goals

- **Time to first web < 15 minutes** when an AI implements a builder from these specs.
- **Static-first**: HTML/CSS/JS output must run on any static host.
- **No secrets** in exported folders.

## Formats

| Format | Spec | Use case |
|--------|------|----------|
| Static HTML zip | [`01-static-html-export.md`](01-static-html-export.md) | Universal baseline |
| Vercel deploy | [`02-vercel-deploy.md`](02-vercel-deploy.md) | Fast public URL |
| Checklist | [`03-deploy-checklist.md`](03-deploy-checklist.md) | Pre-flight QA |

## What gets exported

- Rendered pages **as configured** in the lite canvas (max objects per environment).
- Assets referenced by absolute URLs may remain remote; relative assets should be bundled if **Include assets** is true (see `20-export.md`).

## Environment variables (implementation only)

Store in host dashboard — **never** in `lite/*.md`:

- Analytics keys
- Form endpoints with auth tokens
- Vercel project linkage tokens

## Success metrics (product)

Track (if Analytics enabled):

1. `session_start → export_completed` duration (target < 15 min).
2. Self-reported confidence (7+/10) per user testing guide.

## 🤖 AI agent instructions

```text
Read in order:
1. 01-static-html-export.md
2. 03-deploy-checklist.md
3. 02-vercel-deploy.md (if user wants hosting)
```

## ✅ Validation checklist

- [ ] Exported site loads offline (except intentional remote media)
- [ ] No `.env` in artifact
- [ ] Lighthouse smoke test passes thresholds from validation docs
