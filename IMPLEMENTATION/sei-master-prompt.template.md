# SEI Master Prompt Template

> Universal prompt template for AI builders (Lovable, Bolt, v0, Cursor, Claude Code) to generate Spatial Experience Interfaces correctly.

---

## Instructions for Using This Template

1. Fill in the `[bracketed sections]` with your specific project details
2. Copy the entire filled prompt
3. Paste into your AI builder tool
4. Review and iterate on the output

---

## THE PROMPT

```
# SPATIAL EXPERIENCE INTERFACE (SEI) - PROJECT BUILD

## CRITICAL CONSTRAINTS - READ FIRST

⚠️ THIS IS A SPATIAL INTERFACE - NOT A TRADITIONAL WEB APP

ABSOLUTELY FORBIDDEN:
❌ Navigation menus
❌ Page routing / multiple pages
❌ Top navigation bars
❌ Sidebar navigation
❌ Breadcrumb trails
❌ Tab navigation
❌ Hamburger menus
❌ Footer navigation

REQUIRED STRUCTURE:
✅ Single-page environment
✅ Object-based interaction
✅ Hotspot-triggered overlays
✅ Return to environment after each action

---

## PROJECT OVERVIEW

Project Name: [PROJECT_NAME]

Project Type: [DeFi Dashboard / AI Tool Interface / Education Platform / Analytics System / Other]

Core Purpose: [One-sentence description of what this system does]

Target Users: [Who will use this system]

---

## ENVIRONMENT SPECIFICATION

### Theme & Style

Environment Theme: [e.g., "Cyberpunk City", "University Campus", "Modern Office", "Sci-Fi Lab"]

Visual Style: [e.g., "Low-poly 3D", "Detailed Illustration", "Minimalist Vector", "Isometric"]

Color Palette:
- Background: [COLOR]
- Primary: [COLOR]
- Secondary: [COLOR]
- Accent: [COLOR]
- Text: [COLOR]

### Perspective

View Type: [Isometric / Top-down / Flat / 3D Perspective]

Camera Details: [e.g., "Fixed 45-degree isometric view", "Scrollable viewport"]

### The Five Zones

Map your environment to SEI zones:

```
        [PROFILE ZONE]
        [What appears here: e.g., "User avatar and name"]

[TOOLS]  [CORE]  [ACTIONS]
[What    [What   [What
 objects] objects] objects]

      [PROGRESSION ZONE]
      [What appears here]
```

---

## OBJECT INVENTORY

List ALL interactive objects (maximum 8):

### Object 1: [OBJECT_NAME]
- Zone: [CORE / ACTION / TOOL / PROGRESSION / PROFILE]
- Visual: [Description of appearance]
- Function: [What it does]
- Opens Overlay: [OVERLAY_NAME]

### Object 2: [OBJECT_NAME]
- Zone: [Zone]
- Visual: [Description]
- Function: [What it does]
- Opens Overlay: [OVERLAY_NAME]

### Object 3: [OBJECT_NAME]
- Zone: [Zone]
- Visual: [Description]
- Function: [What it does]
- Opens Overlay: [OVERLAY_NAME]

[Continue for all objects...]

---

## OVERLAY SPECIFICATIONS

### Overlay 1: [OVERLAY_NAME]

Triggered By: [OBJECT_NAME]

Purpose: [What this overlay does]

Content:
- Data to display: [What data shows]
- User actions: [What user can do]
- Forms (if any): [Form fields]

Data Source: [Where data comes from - API/Contract/Database]

Visual:
- Size: [e.g., "500px wide, auto height"]
- Position: [e.g., "Centered"]
- Background: [Color/description]

States:
- Loading: [How loading appears]
- Success: [How success appears]
- Error: [How errors appear]

### Overlay 2: [OVERLAY_NAME]

[Repeat structure...]

---

## TRUTH LAYER (DATA SOURCES)

For each data field, specify the source:

| Data Field | Displayed In | Source | Source Type |
|------------|--------------|--------|-------------|
| [Field 1] | [Overlay] | [Source] | [API/Contract/DB] |
| [Field 2] | [Overlay] | [Source] | [API/Contract/DB] |

---

## INTERACTION RULES

### User Flow

```
User sees environment
    ↓
User clicks object
    ↓
Overlay opens
    ↓
User completes action
    ↓
Overlay closes
    ↓
User returns to environment
```

### Hotspot Behavior

- Hotspots are positioned over objects
- Hover effect: [Description or "subtle glow"]
- Click opens overlay immediately
- Cursor changes to pointer on hover

### Overlay Behavior

- Environment dims behind overlay
- Click outside overlay to close
- X button in top-right to close
- Escape key closes overlay
- After action, return to environment

---

## TECHNICAL REQUIREMENTS

### Framework/Stack

Preferred Stack: [React/Vue/Svelte/Other]

Styling: [Tailwind/CSS-in-Modules/Other]

Animation: [Framer Motion/GSAP/CSS/Other]

### Responsive Behavior

Desktop: [Full environment visible]

Tablet: [Adaptation strategy]

Mobile: [Adaptation strategy - may show partial view with pan]

### Accessibility

- Keyboard navigation: [Yes/No]
- Screen reader support: [Yes/No]
- Focus management: [Description]

---

## VISUAL REFERENCES

[Optional: Add descriptions or references to visual style]

Style Inspiration: [e.g., "Cyberpunk 2077 UI", "Monument Valley", "Material Design"]

Mood: [e.g., "Professional but playful", "Dark and mysterious", "Bright and educational"]

---

## EXAMPLE INTERACTION

Walk through a typical user journey:

1. User lands on page, sees [ENVIRONMENT_DESCRIPTION]
2. User notices [OBJECT_NAME] in the [ZONE]
3. User hovers over [OBJECT_NAME], sees [HOVER_EFFECT]
4. User clicks [OBJECT_NAME], [OVERLAY_NAME] opens
5. In overlay, user sees [DATA_DISPLAYED]
6. User [ACTION_TAKEN]
7. Overlay shows [SUCCESS_STATE]
8. Overlay closes, user returns to environment
9. [Any state changes visible in environment]

---

## VALIDATION CHECKLIST FOR AI BUILDER

Before submitting, verify:

- [ ] NO navigation menus exist
- [ ] NO page routing implemented
- [ ] Single-page environment rendered
- [ ] All objects visible without scrolling
- [ ] Each object has interactive hotspot
- [ ] Overlays open on object click
- [ ] Environment visible behind overlays
- [ ] Overlays can be closed
- [ ] Return to environment after close
- [ ] Data comes from specified sources
- [ ] Loading states implemented
- [ ] Error handling implemented

---

## OUTPUT EXPECTATIONS

Generate:

1. **Environment Component**: The main spatial environment with all objects
2. **Hotspot Components**: Invisible interaction areas over objects
3. **Overlay Components**: Modal interfaces for each object
4. **State Management**: Handling overlay open/close, data fetching
5. **Data Layer**: Connections to specified data sources
6. **Styling**: Complete visual implementation per specifications

DO NOT generate:
- Navigation components
- Page routing
- Multiple page files
- Menu systems

---

END OF PROMPT
```

---

## Tips for Best Results

### Be Specific

```
❌ Vague: "A finance app"
✅ Specific: "A DeFi yield farming dashboard with vault deposits"
```

### Limit Objects

```
❌ Too many: 12 interactive objects
✅ Good: 5-7 interactive objects
```

### Define Data Sources

```
❌ Vague: "Show user data"
✅ Specific: "Balance from smart contract 0x..., APY from /api/apy"
```

### Provide Visual Direction

```
❌ Vague: "Make it look good"
✅ Specific: "Cyberpunk theme with neon accents, dark background"
```

---

## Common AI Builder Mistakes to Prevent

### Mistake 1: Creating Navigation

**Prevention:** Explicitly state "NO navigation menus" multiple times.

### Mistake 2: Multiple Pages

**Prevention:** State "Single-page application" and "No routing" clearly.

### Mistake 3: Static Objects

**Prevention:** Specify "Objects must be clickable with hotspots."

### Mistake 4: Missing Overlays

**Prevention:** Define overlay content for each object.

### Mistake 5: Mock Data in Production

**Prevention:** Specify real data sources and require truth layer connection.

---

## Post-Generation Checklist

After AI builder generates code:

- [ ] Verify no navigation elements exist
- [ ] Confirm single-page structure
- [ ] Test all object hotspots
- [ ] Verify overlays open and close
- [ ] Check data source connections
- [ ] Test responsive behavior
- [ ] Validate accessibility

---

> **Template Version:** SEI v1.0
