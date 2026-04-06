---
doc_id: accessibility-checklist
name: "Accessibility Checklist (WCAG 2.1 AA intent)"
version: "1.0.0"
phase: "lite"
---

# Accessibility checklist — SEI-Lite intent (WCAG 2.1 AA)

> Automated tools help; **manual** testing is required.

## Perceivable

- [ ] Text resize to 200% without loss of core content
- [ ] Color contrast ≥ **4.5:1** normal text; ≥ **3:1** large text/UI components
- [ ] Informative images have appropriate **alt** text
- [ ] Video/audio: captions called out when hosting provides them

## Operable

- [ ] All interactive elements keyboard reachable
- [ ] Visible **focus** indicator
- [ ] No keyboard traps (except intentional modal with ESC)
- [ ] Touch targets **≥ 44×44px** where mobile applies

## Understandable

- [ ] Page language set (`lang` attribute)
- [ ] Form errors described in text near fields
- [ ] Navigation consistent across pages/sections

## Robust

- [ ] Valid, semantic landmarks (`header`, `main`, `nav`, `footer`)
- [ ] ARIA used only when semantics insufficient

## Assistive tech smoke tests

- [ ] VoiceOver (iOS/macOS) or TalkBack (Android): read contact form labels
- [ ] Windows Narrator quick pass on primary flow

## Documentation

Record issues as: **severity**, **steps**, **expected**, **actual**, **WCAG ref** (if known).
