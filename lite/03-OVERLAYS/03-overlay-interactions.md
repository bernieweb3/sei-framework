---
doc_id: overlay-interactions
name: "Overlay Interaction Patterns"
version: "1.0.0"
phase: "lite"
---

# Overlay interaction patterns

## Open / close

| Input | Behavior |
|-------|----------|
| Click object on canvas | Open overlay; tab = Explain |
| `Esc` | Close and return focus |
| Click outside (optional) | Close only if product chooses; lite recommends **confirm** if unsaved changes |
| Primary “Đóng / Close” | Close |

## Focus management

1. On open: move focus to **Explain** tab.
2. While open: trap tab cycle inside overlay.
3. On close: restore focus to launcher.

## Unsaved changes

Flow:

1. User edits in Try tab.
2. User clicks close.
3. If dirty → confirm: “Lưu thay đổi? / Save changes?” **[Lưu] [Hủy] [Không lưu]**

## Mobile

- Full-screen sheet on narrow widths.
- Sticky footer with **Lưu** / **Đóng**.

## Analytics (optional)

| Event | When |
|-------|------|
| `overlay_opened` | Overlay mounts |
| `overlay_tab_try` | User switches to Try |
| `overlay_saved` | Successful Apply |

## 🤖 AI agent instructions

```text
Implementers MUST NOT block screen readers with `aria-hidden` on the root while focus is ill-managed.
Prefer Radix/shadcn dialog patterns or equivalent accessible primitives.
```

## ✅ Validation checklist

- [ ] ESC works
- [ ] Focus trap verified
- [ ] Unsaved changes guarded
- [ ] Mobile sheet usable
- [ ] No duplicate `id`s between overlay and page
