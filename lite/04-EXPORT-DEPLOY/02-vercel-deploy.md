---
doc_id: vercel-deploy
name: "Vercel Deploy"
version: "1.0.0"
phase: "lite"
---

# Vercel deploy — specification

## Preconditions

- Static export folder (`dist/`) matches [`01-static-html-export.md`](01-static-html-export.md).
- User has Vercel account and permissions to create/link a project.

## Recommended project settings

| Setting | Value |
|---------|-------|
| Framework | Other / Static |
| Output dir | `dist` |
| Install command | `None` (if pure static) or per generated repo |
| Build command | `None` or generator-specific |

## Environment variables

Configure only on Vercel dashboard (examples—**not** defaults with secrets):

- `PLAUSIBLE_DOMAIN`
- `FORM_API_URL`
- `CONTACT_WEBHOOK_SECRET`

## Custom domain

- Add domain in Vercel.
- Set **HTTPS** automatic.
- Document DNS records for user in builder UI.

## Preview vs production

- Map **preview** deployments to staging analytics provider (optional).
- Never enable destructive webhooks on previews.

## 🤖 AI agent instructions

```text
If user requests Vercel:
1. Ensure export is static and uses relative asset paths.
2. Add `vercel.json` ONLY if redirects or headers needed; keep file in generated app repo, not in `lite/` specs folder.
3. Document `vercel --prod` in user docs; do not store tokens in markdown.
```

## ✅ Validation checklist

- [ ] Production URL loads
- [ ] 404 page exists (optional but recommended)
- [ ] Security headers considered (`X-Content-Type-Options`, etc.)
- [ ] Redirect apex ↔ www documented
- [ ] No secrets committed alongside static files
