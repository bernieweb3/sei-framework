---
catalog: environments
count: 4
phase: "lite"
---

# Environment catalog — SEI-Lite

SEI-Lite defines **four** environment templates. Each has **five zones** and allows **at most eight** placed objects.

| ID | File | Name | Mood | Best for |
|----|------|------|------|----------|
| `garden` | [`01-garden-environment.md`](01-garden-environment.md) | Minimal Garden | Calm, natural | Personal story, soft landing pages |
| `studio` | [`02-studio-environment.md`](02-studio-environment.md) | Creative Studio | Bold, expressive | Portfolios, creative work, experiments |
| `shop` | [`03-shop-environment.md`](03-shop-environment.md) | Mini Shop | Commerce | Small catalog, lead capture, simple store |
| `portfolio` | [`04-portfolio-environment.md`](04-portfolio-environment.md) | Professional Portfolio | Crisp, trustworthy | Job search, services, B2B intro |

## Shared zone model

All environments use the same zone keys (layout may vary):

- **CORE** — primary content
- **ACTION** — primary calls to action
- **TOOL** — utilities (search, settings affordances)
- **PROGRESSION** — status, steps, “what’s next”
- **PROFILE** — identity / avatar

## Agent workflow

1. Ask the user (or infer) which **environment** fits their goal.
2. Open that environment’s `.md` file; apply **theme**, **typography**, and **layout**.
3. Load only objects listed in that file’s **Available Objects** table (max 8 types allowed in the canvas).
4. Enforce **max 8** total placed objects for the lite canvas unless the product explicitly extends SEI-Lite.

## Cross-references

- Objects: [`../02-OBJECTS/00-object-index.md`](../02-OBJECTS/00-object-index.md)
- Overlay: [`../03-OVERLAYS/00-overlay-system.md`](../03-OVERLAYS/00-overlay-system.md)
