# Environment Specification Template

> Template for defining the spatial environment of a Spatial Experience Interface.

---

## Environment Identity

### Environment Name
```
[Enter environment name - e.g., "Research Laboratory", "Financial District", "University Campus"]
```

### Environment Theme
```
[Enter visual theme - e.g., "Cyberpunk", "Modern Corporate", "Academic Traditional", "Sci-Fi"]
```

### Environment Purpose
```
[Describe the primary purpose of this environment - what system does it represent?]
```

---

## Perspective Specification

### View Type
```
[Select one:]
- [ ] Isometric (3D with parallel projection)
- [ ] Top-down (directly overhead)
- [ ] Flat (2D with depth cues)
- [ ] 3D Perspective (realistic depth)
```

### Camera/View Details
```
Angle: [e.g., "45-degree isometric", "direct top-down"]
Zoom: [e.g., "fixed", "scrollable", "initial zoom level"]
Pan: [e.g., "fixed viewport", "pannable canvas"]
```

---

## Zone Layout

### The Five Universal Zones

Map your environment to the standard SEI zones:

```
        [PROFILE]

[TOOLS]  [CORE]  [ACTIONS]

      [PROGRESSION]
```

---

### CORE Zone (Orientation)

**Purpose:** Central landmark for user orientation

**Content:**
```
[Describe the central feature - e.g., "Main command center", "Central plaza", "Primary building"]
```

**Visual Characteristics:**
```
- Size: [relative size]
- Color: [dominant colors]
- Distinctive features: [what makes it recognizable]
```

---

### ACTION Zone (Primary Work Area)

**Purpose:** Where users perform main tasks

**Objects in this zone:**

| Object Name | Function | Visual Description |
|-------------|----------|-------------------|
| [Object 1]  | [Function]| [Description]     |
| [Object 2]  | [Function]| [Description]     |
| [Object 3]  | [Function]| [Description]     |

---

### TOOL Zone (Supporting Functions)

**Purpose:** Configuration, settings, utilities

**Objects in this zone:**

| Object Name | Function | Visual Description |
|-------------|----------|-------------------|
| [Object 1]  | [Function]| [Description]     |
| [Object 2]  | [Function]| [Description]     |

---

### PROGRESSION Zone (Feedback)

**Purpose:** Stats, achievements, milestones

**Objects in this zone:**

| Object Name | Function | Visual Description |
|-------------|----------|-------------------|
| [Object 1]  | [Function]| [Description]     |
| [Object 2]  | [Function]| [Description]     |

---

### PROFILE Zone (Identity)

**Purpose:** User identity and personal info

**Content:**
```
[Describe what appears here - e.g., "User avatar and name", "Character portrait"]
```

---

## Object Inventory

### Complete Object List

List ALL interactive objects in the environment:

| # | Object Name | Zone | Primary Function | Opens Overlay |
|---|-------------|------|------------------|---------------|
| 1 | [Name]      | [Zone]| [Function]       | [Overlay Name]|
| 2 | [Name]      | [Zone]| [Function]       | [Overlay Name]|
| 3 | [Name]      | [Zone]| [Function]       | [Overlay Name]|
| 4 | [Name]      | [Zone]| [Function]       | [Overlay Name]|
| 5 | [Name]      | [Zone]| [Function]       | [Overlay Name]|

**Total Objects:** [Count]

**Rule Check:** Maximum 8 objects recommended. [ ] Pass [ ] Fail

---

## Visual Design

### Color Palette

| Purpose | Color (Hex) | Usage |
|---------|-------------|-------|
| Background | [#XXXXXX] | Environment base |
| Primary    | [#XXXXXX] | Main objects |
| Secondary  | [#XXXXXX] | Secondary elements |
| Accent     | [#XXXXXX] | Interactive highlights |
| Text       | [#XXXXXX] | Labels and text |

### Lighting

```
[Describe lighting approach - e.g., "Daylight with shadows", "Neon ambient", "Uniform flat"]
```

### Visual Style

```
[Describe art direction - e.g., "Low-poly 3D", "Detailed illustration", "Minimalist vector"]
```

---

## Background Elements

### Non-Interactive Elements

List decorative elements that establish context but are not interactive:

| Element | Purpose | Location |
|---------|---------|----------|
| [Element 1]| [Purpose]| [Location]|
| [Element 2]| [Purpose]| [Location]|

---

## Responsive Considerations

### Viewport Adaptations

```
Desktop: [Describe layout for large screens]
Tablet: [Describe layout for medium screens]
Mobile: [Describe layout for small screens]
```

### Scaling Strategy

```
[ ] Scale entire environment
[ ] Show partial viewport with pan
[ ] Reflow zones
[ ] Other: [describe]
```

---

## Animation & Motion

### Environment Animations

| Animation | Trigger | Description |
|-----------|---------|-------------|
| [Animation 1]| [Trigger]| [Description]|
| [Animation 2]| [Trigger]| [Description]|

### Object Animations

| Object | Animation | Purpose |
|--------|-----------|---------|
| [Object]| [Animation]| [Purpose]|

---

## Example: Completed Template

### Environment Name
```
DeFi Command Center
```

### Environment Theme
```
Cyberpunk financial district
```

### Perspective
```
Isometric, 45-degree angle, fixed viewport
```

### Zone Layout

```
        [PROFILE - User Avatar]

[TOOLS]  [CORE]    [ACTIONS]
Settings  Central   Bank
          Plaza     Exchange
                    Vault

      [PROGRESSION - Stats Board]
```

### Object Inventory

| # | Object Name | Zone | Function | Overlay |
|---|-------------|------|----------|---------|
| 1 | Bank | ACTION | Asset management | Vault Overlay |
| 2 | Exchange | ACTION | Trading | Trade Overlay |
| 3 | Vault | ACTION | Secure storage | Deposit Overlay |
| 4 | Settings | TOOL | Configuration | Settings Overlay |
| 5 | Stats Board | PROGRESSION | View metrics | Analytics Overlay |

---

## Next Steps

After completing this template:
1. [ ] Create Object Mapping for each object
2. [ ] Define Hotspot Specifications
3. [ ] Design Overlay Specifications
4. [ ] Document Truth Layer connections

---

> **Template Version:** SEI v1.0  
> **Last Updated:** [Date]
