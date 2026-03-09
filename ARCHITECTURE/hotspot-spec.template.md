# Hotspot Specification Template

> Template for defining invisible interaction areas mapped to environment objects.

---

## Hotspot Overview

### Definition

A hotspot is an invisible interaction area positioned over an object. It is the bridge between the visual environment and the functional overlay.

### Key Characteristics

```
- Invisible (or subtly indicated)
- Absolute positioned
- Single interaction mapping
- Covers entire interactive area of object
```

---

## Hotspot Inventory

### Complete Hotspot Registry

| Hotspot ID | Hotspot Name | Target Object | Triggered Overlay | Position (X, Y) | Size (W, H) |
|------------|--------------|---------------|-------------------|-----------------|-------------|
| HS-001 | [Name] | [Object] | [Overlay] | [%, %] | [%, %] |
| HS-002 | [Name] | [Object] | [Overlay] | [%, %] | [%, %] |
| HS-003 | [Name] | [Object] | [Overlay] | [%, %] | [%, %] |
| HS-004 | [Name] | [Object] | [Overlay] | [%, %] | [%, %] |
| HS-005 | [Name] | [Object] | [Overlay] | [%, %] | [%, %] |

---

## Detailed Hotspot Specifications

---

### Hotspot: [HS-001] [Hotspot Name]

#### Basic Information

```yaml
Hotspot ID: HS-001
Hotspot Name: [Name]
Target Object: [Object ID and Name]
Triggered Overlay: [Overlay ID and Name]
```

#### Positioning

```yaml
Position Type: [absolute / relative]
Coordinate System: [percentage / pixels]

# If using percentage (recommended for responsiveness)
X Position: [% from left]
Y Position: [% from top]

# If using pixels
X Position: [px from left]
Y Position: [px from top]
```

#### Dimensions

```yaml
Width: [% or px]
Height: [% or px]

# Shape
Shape: [rectangle / circle / polygon]
Border Radius: [px or %] (if applicable)
```

#### Visual Indicators

```yaml
# Hover state (desktop)
Hover Effect: [none / highlight / glow / scale]
Hover Cursor: [pointer / default]

# Visual feedback
Show Border: [yes / no]
Border Color: [#hex]
Border Width: [px]

Show Overlay: [yes / no]
Overlay Color: [rgba]
```

#### Interaction

```yaml
Trigger Event: [click / tap / double-click / right-click]
Touch Target Size: [minimum 44x44px for mobile]

# Accessibility
Keyboard Accessible: [yes / no]
Tab Index: [number]
ARIA Role: [button / link]
ARIA Label: [description]
```

#### Z-Index

```yaml
Z-Index: [number]
# Must be above environment, below overlays
```

---

### Hotspot: [HS-002] [Hotspot Name]

*[Repeat structure for all hotspots]*

---

## Hotspot Positioning Guide

### Coordinate System

SEI recommends percentage-based positioning for responsiveness:

```
Environment: 100% width × 100% height

Hotspot positioned at:
- X: % from left edge
- Y: % from top edge
- Width: % of environment width
- Height: % of environment height
```

### Positioning Example

```
Environment: 1200px × 800px

Object: Vault (located center-left)
Hotspot Position:
  X: 25% (300px from left)
  Y: 40% (320px from top)
  Width: 15% (180px)
  Height: 20% (160px)
```

### Responsive Positioning

| Breakpoint | Position Strategy |
|------------|-------------------|
| Desktop (>1024px) | Fixed percentage |
| Tablet (768-1024px) | Adjusted percentage |
| Mobile (<768px) | Reflow or scaled |

---

## Hotspot Visual States

### State Definitions

| State | Visual Treatment | Purpose |
|-------|------------------|---------|
| Default | Invisible | No distraction from environment |
| Hover | Subtle highlight | Indicate interactivity |
| Active | Stronger highlight | Show selection |
| Disabled | Grayed out | Indicate unavailability |

### CSS Example (Reference)

```css
/* Default - invisible */
.hotspot {
  opacity: 0;
  cursor: pointer;
}

/* Hover - subtle indication */
.hotspot:hover {
  opacity: 0.3;
  background: rgba(255, 255, 255, 0.2);
  box-shadow: 0 0 20px rgba(255, 255, 255, 0.3);
}

/* Active - clear selection */
.hotspot:active {
  opacity: 0.5;
  background: rgba(255, 255, 255, 0.4);
}
```

---

## Hotspot Overlap Rules

### No Overlap Principle

```
Hotspots must not overlap.
Each hotspot must have clear, distinct boundaries.
```

### Minimum Spacing

```
Minimum 20px gap between hotspots (desktop)
Minimum 10px gap between hotspots (mobile)
```

### Overlap Resolution

If objects are close together:

| Strategy | Description |
|----------|-------------|
| Resize | Make hotspots smaller than objects |
| Merge | Combine nearby objects into one hotspot |
| Reposition | Adjust object positions in environment |

---

## Mobile Considerations

### Touch Target Size

```
Minimum touch target: 44px × 44px
Recommended touch target: 48px × 48px
```

### Mobile Adaptations

| Adaptation | Description |
|------------|-------------|
| Enlarge | Increase hotspot size for touch |
| Consolidate | Merge nearby hotspots |
| Prioritize | Show only primary hotspots |

---

## Hotspot-Overlay Mapping

### One-to-One Mapping

```
HS-001 (Vault Hotspot) → vault-overlay (Vault Overlay)
HS-002 (Terminal Hotspot) → terminal-overlay (Terminal Overlay)
```

### Mapping Verification

| Hotspot ID | Opens Overlay | Verified? |
|------------|---------------|-----------|
| HS-001 | overlay-001 | [ ] |
| HS-002 | overlay-002 | [ ] |
| HS-003 | overlay-003 | [ ] |

---

## Example: Complete Hotspot Specification

### Environment: DeFi Dashboard (1200×800px)

| Hotspot ID | Name | Object | Overlay | Position | Size |
|------------|------|--------|---------|----------|------|
| HS-001 | vault-hotspot | Central Vault | vault-overlay | X: 20%, Y: 35% | W: 18%, H: 25% |
| HS-002 | trade-hotspot | Trading Terminal | trade-overlay | X: 55%, Y: 30% | W: 20%, H: 20% |
| HS-003 | analytics-hotspot | Analytics Board | analytics-overlay | X: 75%, Y: 60% | W: 15%, H: 15% |

### Hotspot: vault-hotspot

```yaml
Hotspot ID: HS-001
Name: vault-hotspot
Target Object: OBJ-001 (Central Vault)
Triggered Overlay: OVERLAY-001 (Vault Overlay)

Position:
  X: 20% from left
  Y: 35% from top

Dimensions:
  Width: 18% of container
  Height: 25% of container

Shape: Rectangle with 8px border radius

Visual:
  Default: Invisible
  Hover: White glow, 30% opacity
  Cursor: Pointer

Interaction:
  Trigger: Click / Tap
  Touch Target: 48px minimum

Accessibility:
  Keyboard: Yes (Tab index: 1)
  ARIA Label: "Open vault management"

Z-Index: 10
```

---

## Validation Checklist

- [ ] Every object has exactly one hotspot
- [ ] Hotspot positions documented (X, Y)
- [ ] Hotspot sizes documented (W, H)
- [ ] All hotspots have unique IDs
- [ ] No hotspot overlap
- [ ] Minimum touch target size met
- [ ] Hover states defined
- [ ] Accessibility attributes set
- [ ] Z-index layering correct

---

> **Template Version:** SEI v1.0
