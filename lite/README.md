# SEI-Lite

**SEI-Lite** is a **markdown-only** specification pack for AI agents (Cursor, Claude Code, Lovable, Bolt.new, v0, Antigravity, OpenCode, Codex, etc.). It is **not** executable code: agents read these `.md` files to generate implementations.

## Audience priority

1. **Primary:** Adults ~40–45 (and international users); plain language, low jargon.
2. **Secondary:** Younger adults 18–35.
3. **Tertiary:** Ages 35–40.

Specs support **Vietnamese and English** where noted.

## Entry points

| File | Purpose |
|------|---------|
| [`index.md`](index.md) | Main routing index for AI agents |
| [`01-ENVIRONMENTS/00-environment-index.md`](01-ENVIRONMENTS/00-environment-index.md) | Four environment templates |
| [`02-OBJECTS/00-object-index.md`](02-OBJECTS/00-object-index.md) | Twenty object specifications |

## Phase 1 timeline (5 weeks)

### Week 1: Foundation

- [x] Create `lite/` folder structure
- [x] Write `index.md` entry point
- [x] Create `00-*-index.md` catalog files
- [x] Define markdown template standards (in specs)

### Week 2: Environments

- [x] `01-garden-environment.md`
- [x] `02-studio-environment.md`
- [x] `03-shop-environment.md`
- [x] `04-portfolio-environment.md`
- [x] `00-environment-index.md`

### Week 3: Objects (content)

- [x] Ten content object specs (01–10)
- [x] Plain-language props (Vietnamese and/or English)
- [x] Explain / Try tab content per object

### Week 4: Objects (interaction + utility) + overlays

- [x] Five interaction object specs (11–15)
- [x] Five utility object specs (16–20)
- [x] Overlay system specs (four files)

### Week 5: Export, prompts, docs, validation

- [x] Export/deploy specs (four files)
- [x] AI prompt templates (per `05-AI-PROMPTS/`)
- [x] Validation checklists (five files)
- [x] User documentation (six files)

## Success criteria (product)

- **Time to first web:** target **under 15 minutes** from opening the builder to completed export (when an AI implements from these specs).
- **Explain-first:** default overlay tab is **Giải thích** (Explain), then **Thử ngay** (Try).
- **Accessibility:** WCAG 2.1 AA expectations are captured in [`06-VALIDATION/`](06-VALIDATION/).
- **Per environment:** **max 8 placed objects** (see each environment spec).

## Repository layout

```text
lite/
├── README.md
├── index.md
├── 01-ENVIRONMENTS/
├── 02-OBJECTS/
├── 03-OVERLAYS/
├── 04-EXPORT-DEPLOY/
├── 05-AI-PROMPTS/
├── 06-VALIDATION/
└── 07-DOCS/
```

`FOUNDATION/`, `ARCHITECTURE/`, and `IMPLEMENTATION/` at repo root stay unchanged.

## Git commits

Use Conventional Commits, scoped with `lite/`, for example:

- `feat(lite): add garden environment spec (markdown)`
- `docs(lite): add 15-minute quick start guide`

**Do not** commit generated app source (`.tsx`, `.ts`, `.json`, `.css`) as part of SEI-Lite itself—only these specifications.
