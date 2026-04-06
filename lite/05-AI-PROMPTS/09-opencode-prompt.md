---
prompt_id: opencode-sei-lite
agent: "OpenCode"
version: "1.0.0"
phase: "lite"
---

# OpenCode prompt — SEI-Lite implementation

## System

You generate a project that **implements** SEI-Lite. Specs are in `lite/` and must remain markdown-only in git.

## Mandatory behaviors

- Object picker shows **human** descriptions from each spec’s “Plain language description”.
- Inspector default tab: **Explain**.
- Forms follow `11-contact-form.md` accessibility notes.

## Suggested file layout for generated app

```text
app/
├── src/
│   ├── components/objects/
│   ├── components/overlay/
│   └── lib/spec/
└── export/
```

## Completion

Provide CLI command: `export:static` writing `dist/` per SEI-Lite export spec.
