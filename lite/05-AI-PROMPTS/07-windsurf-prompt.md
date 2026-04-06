---
prompt_id: windsurf-sei-lite
agent: "Windsurf"
version: "1.0.0"
phase: "lite"
---

# Windsurf prompt — SEI-Lite implementation

Use **Cascade** with repo-wide context on `lite/`.

## Instruction packet

- Goal: implement a static-site builder that reads SEI-Lite markdown at build time OR ships JSON derived from those files.
- Prioritize **clarity** over features: one happy path from pick-environment → add-objects → edit-in-overlay → export.
- Overlay tabs: **Explain** default; **Try** contains preview.

## Suggested tasks for the agent

1. Add a parser for frontmatter in environment/object files (implementation language of your choice).
2. Render zones grid from environment layout ASCII diagrams.
3. Map each `object_id` to a component registry.

## Done definition

`pnpm build` / `npm run build` produces `dist/` consistent with `lite/04-EXPORT-DEPLOY/01-static-html-export.md`.
