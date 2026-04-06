---
catalog: ai-prompts
phase: "lite"
---

# AI prompt index — SEI-Lite

Use **one** primary prompt for your tool. All prompts assume you only commit **markdown** under `lite/`; generated app code lives elsewhere.

| Tool | File |
|------|------|
| Cursor IDE | [`01-cursor-prompt.md`](01-cursor-prompt.md) |
| Claude Code | [`02-claude-code-prompt.md`](02-claude-code-prompt.md) |
| Lovable | [`03-lovable-prompt.md`](03-lovable-prompt.md) |
| Bolt.new | [`04-bolt-prompt.md`](04-bolt-prompt.md) |
| v0 | [`05-v0-prompt.md`](05-v0-prompt.md) |
| Google Antigravity | [`06-google-antigravity-prompt.md`](06-google-antigravity-prompt.md) |
| Windsurf | [`07-windsurf-prompt.md`](07-windsurf-prompt.md) |
| Trae IDE | [`08-trae-prompt.md`](08-trae-prompt.md) |
| OpenCode | [`09-opencode-prompt.md`](09-opencode-prompt.md) |
| OpenAI Codex | [`10-codex-prompt.md`](10-codex-prompt.md) |

## Shared instructions (embed in any tool)

1. Read [`../index.md`](../index.md).
2. Pick **one** environment from [`../01-ENVIRONMENTS/00-environment-index.md`](../01-ENVIRONMENTS/00-environment-index.md).
3. Compose with objects from [`../02-OBJECTS/00-object-index.md`](../02-OBJECTS/00-object-index.md); respect **max 8** canvas objects.
4. Implement **Explain-first** overlay per [`../03-OVERLAYS/00-overlay-system.md`](../03-OVERLAYS/00-overlay-system.md).
5. Export per [`../04-EXPORT-DEPLOY/`](../04-EXPORT-DEPLOY/).

## Safety

- No secrets in specs or generated commits.
- Validate against [`../06-VALIDATION/`](../06-VALIDATION/) before claiming “done”.
