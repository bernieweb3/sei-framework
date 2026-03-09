# SEI Framework Index

> Quick reference guide to all SEI Framework documents.

---

## Document Map

### FOUNDATION - Core Concepts

| Document | Purpose | When to Use |
|----------|---------|-------------|
| [sei-principles.md](FOUNDATION/sei-principles.md) | Core SEI principles | Understanding the philosophy |
| [sei-mental-model.md](FOUNDATION/sei-mental-model.md) | Paradigm comparison | Understanding SEI vs traditional UI |
| [sei-glossary.md](FOUNDATION/sei-glossary.md) | Standardized terminology | Ensuring consistent language |
| [sei-interaction-model.md](FOUNDATION/sei-interaction-model.md) | Universal interaction pattern | Designing interactions |

### ARCHITECTURE - System Design

| Document | Purpose | When to Use |
|----------|---------|-------------|
| [sei-system-architecture.md](ARCHITECTURE/sei-system-architecture.md) | High-level architecture | Understanding system structure |
| [environment-spec.template.md](ARCHITECTURE/environment-spec.template.md) | Define spatial environment | Starting a new SEI project |
| [object-mapping.template.md](ARCHITECTURE/object-mapping.template.md) | Map objects to functions | Designing object inventory |
| [hotspot-spec.template.md](ARCHITECTURE/hotspot-spec.template.md) | Define interaction areas | Specifying clickable regions |
| [overlay-spec.template.md](ARCHITECTURE/overlay-spec.template.md) | Design modal interfaces | Creating overlay content |
| [truth-layer-spec.md](ARCHITECTURE/truth-layer-spec.md) | Define data sources | Connecting to backends |

### IMPLEMENTATION - Building

| Document | Purpose | When to Use |
|----------|---------|-------------|
| [sei-master-prompt.template.md](IMPLEMENTATION/sei-master-prompt.template.md) | AI builder prompt | Using AI tools to build |
| [sei-starter-template.md](IMPLEMENTATION/sei-starter-template.md) | Project starter structure | Setting up a new project |
| [canvas-ui-spec.template.md](IMPLEMENTATION/canvas-ui-spec.template.md) | Complete UI specification | Detailed implementation spec |
| [ai-builder-rules.md](IMPLEMENTATION/ai-builder-rules.md) | Constraints for AI | Preventing common mistakes |
| [sei-validation-checklist.md](IMPLEMENTATION/sei-validation-checklist.md) | Verify implementation | Testing and QA |

### EXPERIENCE - UX & Design

| Document | Purpose | When to Use |
|----------|---------|-------------|
| [spatial-ux-rules.md](EXPERIENCE/spatial-ux-rules.md) | UX best practices | Designing user experience |
| [spatial-patterns.md](EXPERIENCE/spatial-patterns.md) | Reusable patterns | Choosing environment metaphors |
| [narrative-layer.template.md](EXPERIENCE/narrative-layer.template.md) | Story framing | Adding narrative context |
| [style-system.template.md](EXPERIENCE/style-system.template.md) | Visual design system | Defining visual style |

---

## Workflow Guides

### Starting a New SEI Project

1. Read [SEI Principles](FOUNDATION/sei-principles.md)
2. Understand the [Mental Model](FOUNDATION/sei-mental-model.md)
3. Review [System Architecture](ARCHITECTURE/sei-system-architecture.md)
4. Choose a [Spatial Pattern](EXPERIENCE/spatial-patterns.md)
5. Complete [Environment Spec](ARCHITECTURE/environment-spec.template.md)
6. Complete [Object Mapping](ARCHITECTURE/object-mapping.template.md)
7. Complete [Hotspot Spec](ARCHITECTURE/hotspot-spec.template.md)
8. Complete [Overlay Spec](ARCHITECTURE/overlay-spec.template.md)
9. Document [Truth Layer](ARCHITECTURE/truth-layer-spec.md)

### Building with AI

1. Fill out [Master Prompt Template](IMPLEMENTATION/sei-master-prompt.template.md)
2. Review [AI Builder Rules](IMPLEMENTATION/ai-builder-rules.md)
3. Submit to AI builder tool
4. Validate with [Validation Checklist](IMPLEMENTATION/sei-validation-checklist.md)

### Building Manually

1. Use [Starter Template](IMPLEMENTATION/sei-starter-template.md) for project structure
2. Follow [Canvas UI Spec](IMPLEMENTATION/canvas-ui-spec.template.md) for implementation
3. Apply [Spatial UX Rules](EXPERIENCE/spatial-ux-rules.md) for user experience

### Refining UX

1. Review [Spatial UX Rules](EXPERIENCE/spatial-ux-rules.md)
2. Complete [Narrative Layer](EXPERIENCE/narrative-layer.template.md)
3. Define [Style System](EXPERIENCE/style-system.template.md)

---

## Quick Reference

### The SEI Mantra

```
Context first.
Objects speak.
Overlays act.
Truth rules.
Space remembers.
```

### The Five Zones

```
        [PROFILE]

[TOOLS]  [CORE]  [ACTIONS]

      [PROGRESSION]
```

### Interaction Flow

```
Environment → Object → Hotspot → Overlay → Action → Environment
```

### Critical Constraints

```
❌ NO navigation menus
❌ NO page routing
✅ Single page only
✅ Object-based interaction
✅ Hotspot-triggered overlays
✅ Return to environment
```

---

## Templates at a Glance

| Template | Output |
|----------|--------|
| Environment Spec | Complete environment definition |
| Object Mapping | Object-to-function mapping |
| Hotspot Spec | Interaction area definitions |
| Overlay Spec | Modal interface designs |
| Master Prompt | AI builder input |
| Starter Template | Project structure |
| Canvas UI Spec | Full implementation spec |
| Narrative Layer | Story framing |
| Style System | Visual design system |
| Spatial Patterns | Environment metaphors |

---

## Checklists at a Glance

| Checklist | Use For |
|-----------|---------|
| [Validation Checklist](IMPLEMENTATION/sei-validation-checklist.md) | Verifying implementations |
| [AI Builder Rules](IMPLEMENTATION/ai-builder-rules.md) | Preventing AI mistakes |
| [Spatial UX Rules](EXPERIENCE/spatial-ux-rules.md) | UX validation |

---

## Terminology Quick Reference

| Term | Definition |
|------|------------|
| **Environment** | Spatial context containing all elements |
| **Object** | Visual entity representing a capability |
| **Hotspot** | Invisible interaction area over an object |
| **Overlay** | Modal interface containing functionality |
| **Truth Layer** | Authoritative source of data |
| **Experience Layer** | Visual and interactive representation |
| **Zone** | Designated area with specific purpose |

See [Glossary](FOUNDATION/sei-glossary.md) for complete terminology.

---

## Common Patterns

### Pattern 1: Simple View

```
Environment → Object → Overlay (view data) → Close → Environment
```

Use for: Displaying information, viewing status

### Pattern 2: Form Submission

```
Environment → Object → Overlay (form) → Submit → Loading → Success → Close → Environment
```

Use for: Deposits, configuration, data entry

### Pattern 3: Multi-Step

```
Environment → Object → Overlay (step 1) → Overlay (step 2) → ... → Close → Environment
```

Use for: Complex workflows, wizards

---

## Troubleshooting

| Problem | Solution | Document |
|---------|----------|----------|
| AI creates navigation | Add explicit constraints | [AI Builder Rules](IMPLEMENTATION/ai-builder-rules.md) |
| Too many objects | Reduce to 5-8 | [UX Rules](EXPERIENCE/spatial-ux-rules.md) |
| Objects not clickable | Verify hotspots | [Hotspot Spec](ARCHITECTURE/hotspot-spec.template.md) |
| Overlays don't close | Check close mechanism | [Overlay Spec](ARCHITECTURE/overlay-spec.template.md) |
| Data not loading | Verify Truth Layer | [Truth Layer Spec](ARCHITECTURE/truth-layer-spec.md) |

---

## External Resources

### AI Builder Tools

- [Lovable](https://lovable.dev)
- [Bolt](https://bolt.new)
- [v0](https://v0.dev)
- [Cursor](https://cursor.sh)

### Design Inspiration

- [Dribbble](https://dribbble.com) - UI inspiration
- [Behance](https://behance.net) - Design portfolios
- [Awwwards](https://awwwards.com) - Web design trends

---

## Framework Evolution

### Current Version

**SEI v1.1** - Added mental model, system architecture, spatial patterns, and starter template

### Version History

| Version | Changes |
|---------|---------|
| v1.1 | Added sei-mental-model, sei-system-architecture, spatial-patterns, sei-starter-template |
| v1.0 | Initial release |

### Future Enhancements

- [ ] Additional environment templates
- [ ] Animation guidelines
- [ ] Accessibility deep-dive
- [ ] Performance optimization guide
- [ ] Testing strategy guide

---

## Feedback

To suggest improvements or report issues:

1. Document the problem/suggestion
2. Reference specific files
3. Propose solution if applicable

---

> **Last Updated:** March 2026  
> **Version:** SEI v1.1
