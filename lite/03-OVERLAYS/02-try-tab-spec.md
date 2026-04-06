---
tab_id: try
name: "Thử ngay (Try)"
version: "1.0.0"
phase: "lite"
---

# Try tab — specification

## Goals

- Let users **feel** the outcome before committing.
- Always pair **inputs** with **preview**.

## Required controls

| Control | Required | Behavior |
|---------|----------|----------|
| Live preview | ✅ | Reflects current props |
| Reset | ✅ | Restores last saved or defaults |
| Apply / Lưu | ✅ | Commits to canvas model |
| Inline errors | ✅ For forms | Text + `aria-invalid` in implementation |

## Microcopy (bilingual labels)

- **Reset** / **Đặt lại**
- **Apply** / **Áp dụng**
- **Save & close** / **Lưu và đóng** (if separate from Apply)

## Progressive disclosure

For complex objects (Gallery, Table):

1. Start with 3 sample items.
2. Offer “Add row” / “Add image” after success with basics.

## 🤖 AI agent instructions

```text
When implementing Try tab:
1. Debounce preview updates ~100–250ms for text fields.
2. On Apply, close overlay OR keep open based on product UX—lite default: keep open until user clicks Save & close or Đóng.
3. Announce validation errors via polite `aria-live` region.
```

## ✅ Validation checklist

- [ ] Preview matches exported output (same tokenized styles)
- [ ] Reset never loses unrelated objects
- [ ] Apply disabled when invalid (when validation exists)
- [ ] Touch targets ≥ 44px for primary actions
