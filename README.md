# Spatial Experience Interface (SEI) Framework

> A comprehensive framework for building spatial, object-based software interfaces.

---

## What is SEI?

**Spatial Experience Interface (SEI)** is a software interface paradigm where system capabilities are represented as spatial objects inside a contextual environment, and users interact with those objects instead of navigating menus.

### Traditional UI vs SEI

```
Traditional:  Menu → Page → Form → Action
SEI:          Environment → Object → Overlay → Action
```

### Core Principle

```
Context first.
Function second.
```

Users understand the environment first, then understand the actions available within it.

---

## Why SEI?

| Traditional UI | SEI |
|----------------|-----|
| Menu-heavy | Intuitive |
| Abstract | Memorable |
| Boring | Discoverable |
| Hard to remember | Contextual |

SEI leverages human spatial cognition—people remember places better than lists.

---

## Framework Structure

```
SEI-Framework/
├── FOUNDATION/           # Core principles and concepts
│   ├── sei-principles.md
│   ├── sei-glossary.md
│   └── sei-interaction-model.md
├── ARCHITECTURE/         # System architecture specs
│   ├── environment-spec.template.md
│   ├── object-mapping.template.md
│   ├── hotspot-spec.template.md
│   ├── overlay-spec.template.md
│   └── truth-layer-spec.md
├── IMPLEMENTATION/       # Implementation guides
│   ├── sei-master-prompt.template.md
│   ├── canvas-ui-spec.template.md
│   ├── ai-builder-rules.md
│   └── sei-validation-checklist.md
└── EXPERIENCE/           # UX and design
    ├── spatial-ux-rules.md
    ├── narrative-layer.template.md
    └── style-system.template.md
```

---

## Quick Start

### 1. Understand the Principles

Read the Foundation documents:
- [SEI Principles](FOUNDATION/sei-principles.md) - Core principles
- [SEI Glossary](FOUNDATION/sei-glossary.md) - Standardized terminology
- [Interaction Model](FOUNDATION/sei-interaction-model.md) - Universal interaction pattern

### 2. Design Your Environment

Use the Architecture templates:
- [Environment Spec](ARCHITECTURE/environment-spec.template.md)
- [Object Mapping](ARCHITECTURE/object-mapping.template.md)
- [Hotspot Spec](ARCHITECTURE/hotspot-spec.template.md)
- [Overlay Spec](ARCHITECTURE/overlay-spec.template.md)

### 3. Build with AI

Use the Implementation resources:
- [Master Prompt](IMPLEMENTATION/sei-master-prompt.template.md) - For AI builders
- [AI Builder Rules](IMPLEMENTATION/ai-builder-rules.md) - Constraints and guidelines
- [Validation Checklist](IMPLEMENTATION/sei-validation-checklist.md) - Verify implementation

### 4. Refine the Experience

Apply the Experience guidelines:
- [Spatial UX Rules](EXPERIENCE/spatial-ux-rules.md)
- [Narrative Layer](EXPERIENCE/narrative-layer.template.md)
- [Style System](EXPERIENCE/style-system.template.md)

---

## The Five Universal Zones

Every SEI environment has five zones:

```
        [PROFILE]
          User
          identity

[TOOLS]  [CORE]  [ACTIONS]
Config   Main    Primary
         hub     functions

      [PROGRESSION]
        Status &
      achievements
```

| Zone | Purpose | Example Content |
|------|---------|-----------------|
| CORE | Orientation | Central landmark, main feature |
| ACTION | Primary work | Terminals, machines, consoles |
| TOOL | Supporting | Settings, configuration |
| PROGRESSION | Feedback | Stats, achievements |
| PROFILE | Identity | Avatar, user info |

---

## Universal Interaction Pattern

Every SEI interaction follows this flow:

```
User sees environment
        ↓
User recognizes object
        ↓
User interacts with object (hotspot)
        ↓
Overlay opens
        ↓
System action occurs
        ↓
Overlay closes
        ↓
Return to environment
```

---

## Use Cases

SEI applies to any domain:

| Domain | Environment Example |
|--------|---------------------|
| DeFi | Financial district |
| AI Tools | Command center |
| Education | Campus |
| Analytics | Observatory |
| Healthcare | Medical facility |
| Research | Laboratory |
| Enterprise | Office workspace |
| Gaming | Game world |

---

## Key Constraints

### ❌ Never Allowed

- Navigation menus
- Page routing
- Top/sidebar navigation
- Breadcrumbs
- Tab navigation

### ✅ Always Required

- Single-page environment
- Object-based interaction
- Hotspot-triggered overlays
- Return to environment

---

## Two-Layer Architecture

```
┌─────────────────────────────────┐
│      EXPERIENCE LAYER           │
│  (Environment, Objects,         │
│   Hotspots, Overlays, Visuals)  │
└─────────────┬───────────────────┘
              │
              │ Represents
              │
┌─────────────▼───────────────────┐
│        TRUTH LAYER              │
│  (APIs, Smart Contracts,        │
│   Database, Backend Services)   │
└─────────────────────────────────┘
```

**Rule:** The Experience Layer must never fabricate truth.

---

## For AI Builders

Use the [Master Prompt Template](IMPLEMENTATION/sei-master-prompt.template.md) with tools like:

- Lovable
- Bolt
- v0
- Cursor
- Claude Code

Include these critical constraints in every prompt:

```
CRITICAL RULES:
1. NO navigation menus
2. NO page routing
3. Single page only
4. Objects must be clickable
5. All functionality in overlays
6. Environment visible behind overlays
7. Return to environment after overlay closes
```

---

## Validation

Use the [Validation Checklist](IMPLEMENTATION/sei-validation-checklist.md) to verify:

- [ ] No navigation elements
- [ ] Single-page structure
- [ ] All objects clickable
- [ ] Overlays open and close
- [ ] Returns to environment
- [ ] Data from Truth Layer

---

## Contributing

This framework is designed to be extended. When adding new templates:

1. Follow the three-layer structure (Foundation, Architecture, Implementation, Experience)
2. Maintain consistency with existing terminology
3. Include examples
4. Provide validation criteria

---

## Version

**Current Version:** SEI v1.0

---

## License

[Specify your license]

---

## Credits

Framework developed based on the Spatial Experience Interface paradigm.

---

> **Remember:** SEI is not about making software look like a game. It's about making complex systems feel intuitive through spatial context.
