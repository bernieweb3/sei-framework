# Object Mapping Template

> Template for mapping environment objects to system functions and overlays.

---

## Object Mapping Overview

### Purpose

This document defines how each visible object in the environment connects to:
- System capabilities
- Data sources
- Overlay interfaces
- User actions

### Mapping Principle

```
Every object must map to exactly one primary overlay.
Every overlay must map to exactly one primary function.
```

---

## Object Mapping Table

### Complete Object Registry

| Object ID | Object Name | Visual Description | Location (Zone) | Primary Function |
|-----------|-------------|-------------------|-----------------|------------------|
| OBJ-001 | [Name] | [Description] | [Zone] | [Function] |
| OBJ-002 | [Name] | [Description] | [Zone] | [Function] |
| OBJ-003 | [Name] | [Description] | [Zone] | [Function] |
| OBJ-004 | [Name] | [Description] | [Zone] | [Function] |
| OBJ-005 | [Name] | [Description] | [Zone] | [Function] |

---

## Detailed Object Specifications

---

### Object: [OBJ-001] [Object Name]

#### Basic Information

```yaml
Object ID: OBJ-001
Object Name: [Name]
Display Label: [Label shown to user]
Zone: [CORE / ACTION / TOOL / PROGRESSION / PROFILE]
```

#### Visual Specification

```
Visual Description: [Detailed description of appearance]
Size: [Relative size in environment]
Color Scheme: [Primary colors]
Animation: [Idle animation if any]
Distinctive Features: [What makes it recognizable]
```

#### Functional Mapping

```yaml
Primary Function: [What this object does]
System Capability: [Backend/system function it represents]
Overlay Triggered: [Name of overlay that opens]
```

#### Data Requirements

| Data Field | Source | Real-time? |
|------------|--------|------------|
| [Field 1] | [Source] | [Yes/No] |
| [Field 2] | [Source] | [Yes/No] |

#### User Actions

| Action | Description | Result |
|--------|-------------|--------|
| Click/Tap | [What happens] | [Overlay opens] |
| Hover (desktop) | [Visual feedback] | [Highlight effect] |

#### Accessibility

```
Alt Text: [Description for screen readers]
Keyboard Access: [Tab order, shortcut key]
ARIA Label: [Accessible name]
```

---

### Object: [OBJ-002] [Object Name]

#### Basic Information

```yaml
Object ID: OBJ-002
Object Name: [Name]
Display Label: [Label shown to user]
Zone: [CORE / ACTION / TOOL / PROGRESSION / PROFILE]
```

#### Visual Specification

```
Visual Description: [Detailed description of appearance]
Size: [Relative size in environment]
Color Scheme: [Primary colors]
Animation: [Idle animation if any]
Distinctive Features: [What makes it recognizable]
```

#### Functional Mapping

```yaml
Primary Function: [What this object does]
System Capability: [Backend/system function it represents]
Overlay Triggered: [Name of overlay that opens]
```

#### Data Requirements

| Data Field | Source | Real-time? |
|------------|--------|------------|
| [Field 1] | [Source] | [Yes/No] |
| [Field 2] | [Source] | [Yes/No] |

#### User Actions

| Action | Description | Result |
|--------|-------------|--------|
| Click/Tap | [What happens] | [Overlay opens] |
| Hover (desktop) | [Visual feedback] | [Highlight effect] |

#### Accessibility

```
Alt Text: [Description for screen readers]
Keyboard Access: [Tab order, shortcut key]
ARIA Label: [Accessible name]
```

---

### Object: [OBJ-003] [Object Name]

*[Repeat structure for all objects]*

---

## Object Affordance Guidelines

### Visual Affordances

Objects should visually imply their function:

| Object Type | Visual Cues | Implied Function |
|-------------|-------------|------------------|
| Terminal | Screen, keyboard, buttons | Configure, operate |
| Vault | Heavy door, lock, metal | Store, secure |
| Board | Flat surface, displays | View, read |
| Archive | Shelves, folders, books | Retrieve, browse |
| Machine | Gears, pipes, activity | Process, execute |
| Chest | Container, lid | Collect, open |
| Portal | Doorway, glow, transition | Navigate, enter |

### Affordance Checklist

For each object, verify:

- [ ] User can guess function without label
- [ ] Object looks interactive
- [ ] Object stands out from background
- [ ] Object fits environment theme
- [ ] Object size is appropriate

---

## Object Interaction Matrix

### Cross-Object Relationships

| Object | Related Objects | Relationship |
|--------|-----------------|--------------|
| [Object A]| [Object B, C] | [Description] |
| [Object B]| [Object A, D] | [Description] |

### Interaction Flows

Multi-object workflows:

```
[Object A] → [Action] → [Object B] → [Action] → [Result]
```

Example:
```
Library → Get Recipe → Workshop → Craft Item → Inventory
```

---

## Object State Management

### State Definitions

| State | Visual | Description |
|-------|--------|-------------|
| Default | [Visual] | Normal state |
| Hover | [Visual] | Mouse/touch over |
| Active | [Visual] | Currently in use |
| Disabled | [Visual] | Temporarily unavailable |
| Completed | [Visual] | Task/objective done |
| New | [Visual] | Newly available |

### State Transitions

```
[Default] --(hover)--> [Hover] --(click)--> [Active] --(complete)--> [Completed]
```

---

## Example: Complete Object Mapping

### Environment: DeFi Dashboard

| Object ID | Object Name | Function | Overlay |
|-----------|-------------|----------|---------|
| OBJ-001 | Central Vault | Asset storage | Vault Overlay |
| OBJ-002 | Trading Terminal | Execute trades | Trade Overlay |
| OBJ-003 | Analytics Board | View metrics | Analytics Overlay |
| OBJ-004 | Settings Console | Configuration | Settings Overlay |
| OBJ-005 | Rewards Chest | Claim rewards | Rewards Overlay |

### Object: Central Vault

```yaml
Object ID: OBJ-001
Object Name: Central Vault
Display Label: "Vault"
Zone: ACTION
```

**Visual:** Large metallic structure with glowing lock, security bars, digital display showing balance

**Function:** Primary interface for deposits, withdrawals, and balance viewing

**Overlay:** vault-overlay

**Data:**
| Field | Source | Real-time |
|-------|--------|-----------|
| Balance | Smart Contract | Yes |
| APY | Backend API | Yes |
| Deposit History | Subgraph | No |

---

## Validation Checklist

- [ ] Every object has unique ID
- [ ] Every object maps to one overlay
- [ ] Every object has clear affordance
- [ ] Object count ≤ 8
- [ ] All data sources documented
- [ ] Accessibility attributes defined

---

> **Template Version:** SEI v1.0
