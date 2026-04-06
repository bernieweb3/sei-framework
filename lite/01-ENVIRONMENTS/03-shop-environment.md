---
environment_id: shop
name: "🏪 Mini Shop"
version: "1.0.0"
phase: "lite"
max_objects: 8
zones: ["CORE", "ACTION", "TOOL", "PROGRESSION", "PROFILE"]
---

# 🏪 Mini Shop Environment

## 📖 Narrative

“A small storefront with a clear promise: what you sell, why it matters, and how to buy or inquire.”

_Một cửa hàng nhỏ với lời hứa rõ ràng: bạn bán gì, vì sao quan trọng, và cách mua hoặc liên hệ._

## 🎨 Theme specification

### Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--primary` | `#0F766E` | Buy / checkout actions |
| `--secondary` | `#ECFEFF` | Background |
| `--accent` | `#EA580C` | Sale / urgency (use sparingly) |
| `--text` | `#0F172A` | Body |

### Typography

| Token | Value | Usage |
|-------|-------|-------|
| `--font-heading` | `Inter, system-ui, sans-serif` | Headings |
| `--font-body` | `Inter, system-ui, sans-serif` | Body |
| `--font-size-base` | `16px` | Minimum body size |

### Layout

```text
[PROFILE]   [TOOLS]
 Brand        Search

    [CORE]
  Offers

[ACTION]     [PROGRESSION]
 Buy/Lead     Shipping / trust steps
```

## 📦 Available objects (max 8)

| ID | Object | Zone | Description |
|----|--------|------|-------------|
| 01 | Text Block | CORE | Value proposition |
| 02 | Image Card | CORE | Product hero |
| 04 | Gallery | CORE | Product grid |
| 07 | Table | CORE | Compare SKUs or sizes |
| 11 | Contact Form | ACTION | Lead capture |
| 12 | Button | ACTION | Buy / WhatsApp / Book |
| 15 | Search Bar | TOOL | Find product |
| 18 | Analytics | TOOL | Track events (implementation-level) |

## 🤖 AI agent instructions

```text
When the user selects the Mini Shop environment:
1. Surface pricing or “from $X” clearly in CORE if relevant (plain language).
2. ACTION must include exactly one primary commerce path (button or form)—avoid competing CTAs.
3. If analytics object is present, wire privacy-friendly events (overlay_opened, cta_click) without third-party cookies by default.
4. Enforce max 8 objects.
5. Ensure form labels are visible (no placeholder-only labels).
```

## ✅ Validation checklist

- [ ] Primary CTA is obvious
- [ ] Form has labels and error messages
- [ ] Max 8 objects enforced
- [ ] Price and currency clear (if applicable)
- [ ] Keyboard operable cart or lead flow
