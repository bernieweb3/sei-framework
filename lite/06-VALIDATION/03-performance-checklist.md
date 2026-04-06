---
doc_id: performance-checklist
name: "Performance Checklist (Lighthouse-oriented)"
version: "1.0.0"
phase: "lite"
---

# Performance checklist — Lighthouse-oriented

Targets assume **mid-tier mobile** emulation for the exported static site.

## Targets (defaults for SEI-Lite Phase 1)

| Metric | Target |
|--------|--------|
| Lighthouse Performance | **≥ 90** |
| LCP | **< 2.5s** on tested device |
| CLS | **< 0.1** |
| TBT | keep low (contextual to JS amount) |

## Images

- [ ] Width/height attributes or CSS to reduce CLS
- [ ] Lazy-load below-the-fold images
- [ ] Modern formats where available (webp/avif) with fallbacks

## JavaScript

- [ ] No huge bundles for lite static sites; defer non-critical JS
- [ ] Respect `prefers-reduced-motion`

## Fonts

- [ ] `font-display: swap` (or system font stack)
- [ ] Limit weights/styles

## Network

- [ ] Compress assets (gzip/brotli) on host
- [ ] HTTP caching headers on static assets (host config)

## Measurement

- [ ] Run Lighthouse on **exported** `index.html`, not only dev server
- [ ] Repeat on a throttled profile at least once
