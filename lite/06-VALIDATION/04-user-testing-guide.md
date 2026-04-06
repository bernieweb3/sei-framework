---
doc_id: user-testing-guide
name: "User Testing Guide"
version: "1.0.0"
phase: "lite"
---

# User testing guide — SEI-Lite

## Participant profile (priority)

1. **Primary:** Adults **40–45**, mixed international + Vietnamese.
2. **Secondary:** **18–35**.
3. **Tertiary:** **35–40**.

## Session setup (30 minutes)

1. **0–5 min:** Warm intro; clarify you’re testing the product, not the person.
2. **5–20 min:** Task list (below); think-aloud encouraged.
3. **20–30 min:** Survey + debrief.

## Tasks

1. Pick an environment that fits a pretend bakery landing page.
2. Add **3** objects: text, image, button.
3. Open the overlay; confirm **Explain** shows first.
4. Change props in **Try**; save.
5. Export or publish (simulated if needed).

## 🎯 Success criteria

### Metric 1: Time to first web

- **Target:** **< 15 minutes** from session start (or app open, if pre-signed-in) through export completion.
- **Measure:** Timestamp milestones in notes or analytics (`export_completed`).

### Metric 2: User confidence

- **Target:** **≥ 7 / 10** self-reported.
- **Questions:**
  1. “How confident do you feel you could do this alone next time (1–10)?”
  2. “What felt easiest?”
  3. “What felt hardest?”

### Metric 3: Completion rate

- **Target:** **100%** complete export in pilot cohorts (allow retries).
- **Measure:** `export_completed / session_start`.

### Metric 4: Accessibility compliance

- **Target:** WCAG 2.1 **AA intent** per [`02-accessibility-checklist.md`](02-accessibility-checklist.md).

### Metric 5: Performance

- **Target:** Lighthouse Performance **≥ 90** on exported output per [`03-performance-checklist.md`](03-performance-checklist.md).

## Facilitation tips

- If stuck >2 minutes on jargon, file a **copy bug** against object specs.
- Prefer quiet observation; ask open prompts.

## Reporting

Summarize: **participants**, **tasks passed**, **top 3 issues**, **quotes**.
