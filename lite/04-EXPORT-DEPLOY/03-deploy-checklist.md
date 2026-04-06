---
doc_id: deploy-checklist
name: "Deploy Checklist"
version: "1.0.0"
phase: "lite"
---

# Deploy checklist — SEI-Lite

Use before sharing a public link or handing off a ZIP.

## Content

- [ ] Proofread in both target languages (if bilingual site).
- [ ] All buttons/links navigate correctly.
- [ ] Forms point to correct endpoint and show success states.
- [ ] Images load; alt text present for informative images.

## Accessibility (quick)

- [ ] Keyboard-only walkthrough completes core task.
- [ ] Visible focus on interactive controls.
- [ ] Color contrast feels readable on sunny phone screen.

## Performance (quick)

- [ ] Largest image not unnecessarily huge (< ~500KB typical for hero unless art demands).
- [ ] Lighthouse Performance ≥ 90 on mid-tier mobile (see validation docs).

## Privacy & safety

- [ ] No API keys in HTML/JS.
- [ ] Contact form spam protection considered.
- [ ] Analytics honors local regulations (inform user in FAQ).

## SEO basics (optional)

- [ ] `<title>` and meta description set.
- [ ] `favicon` present.

## Post-deploy

- [ ] Open on real phone + one desktop browser you did **not** develop in.
- [ ] Share link with one external reader for clarity test.

## Sign-off

| Role | Name | Date |
|------|------|------|
| Builder |  |  |
| Reviewer |  |  |
