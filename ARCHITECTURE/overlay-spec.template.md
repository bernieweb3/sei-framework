# Overlay Specification Template

> Template for defining modal interfaces that contain data, forms, and actions.

---

## Overlay Overview

### Definition

An overlay is a modal interface that appears above the environment when a user interacts with an object. It contains the actual functionality, data, and actions of the system.

### Key Characteristics

```
- Opens above the environment
- Contains logic and functionality
- Must be closable
- Data comes from Truth Layer
- Returns user to environment when closed
```

---

## Overlay Inventory

### Complete Overlay Registry

| Overlay ID | Overlay Name | Triggered By | Purpose | Complexity |
|------------|--------------|--------------|---------|------------|
| OVERLAY-001 | [Name] | [Object/Hotspot] | [Purpose] | [Simple/Medium/Complex] |
| OVERLAY-002 | [Name] | [Object/Hotspot] | [Purpose] | [Simple/Medium/Complex] |
| OVERLAY-003 | [Name] | [Object/Hotspot] | [Purpose] | [Simple/Medium/Complex] |

---

## Detailed Overlay Specifications

---

### Overlay: [OVERLAY-001] [Overlay Name]

#### Basic Information

```yaml
Overlay ID: OVERLAY-001
Overlay Name: [Name]
Triggered By: [Hotspot ID and Name]
Purpose: [One-sentence description]
Complexity: [Simple / Medium / Complex]
```

#### Visual Design

```yaml
# Container
Width: [% or px]
Height: [% or px]
Max Width: [px]
Max Height: [px]

# Position
Position Type: [centered / anchored]
Anchor Point: [if anchored - e.g., "top-right"]

# Styling
Background: [#hex or rgba]
Border Radius: [px]
Border: [description]
Shadow: [description]
Padding: [px]
```

#### Background Treatment

```yaml
Environment Behind Overlay:
  Visibility: [visible / hidden]
  Treatment: [dimmed / blurred / darkened]
  Dim Level: [% opacity]
  Click Outside to Close: [yes / no]
```

#### Content Structure

```
┌─────────────────────────────────────┐
│  [Header]                           │
│  - Title                            │
│  - Close Button                     │
├─────────────────────────────────────┤
│  [Content Area]                     │
│  - Data Display                     │
│  - Forms                            │
│  - Actions                          │
├─────────────────────────────────────┤
│  [Footer - optional]                │
│  - Secondary Actions                │
│  - Status                           │
└─────────────────────────────────────┘
```

#### Header Content

| Element | Content | Required? |
|---------|---------|-----------|
| Title | [Text] | Yes |
| Icon | [Icon description] | No |
| Close Button | [X / Close / Back] | Yes |
| Subtitle | [Text] | No |

#### Data Display

| Data Field | Source | Format | Update Frequency |
|------------|--------|--------|------------------|
| [Field 1] | [Source] | [Format] | [Real-time / On load] |
| [Field 2] | [Source] | [Format] | [Real-time / On load] |
| [Field 3] | [Source] | [Format] | [Real-time / On load] |

#### Form Elements

| Field | Type | Validation | Required? |
|-------|------|------------|-----------|
| [Field 1] | [text/number/select/etc] | [Rules] | [Yes/No] |
| [Field 2] | [text/number/select/etc] | [Rules] | [Yes/No] |

#### Actions

| Action | Type | Primary? | Result |
|--------|------|----------|--------|
| [Action 1] | [Button/Link] | [Yes/No] | [What happens] |
| [Action 2] | [Button/Link] | [No] | [What happens] |
| Cancel/Close | [Button/Link] | [No] | [Close overlay] |

#### Footer Content

| Element | Content | Purpose |
|---------|---------|---------|
| [Element 1] | [Description] | [Purpose] |
| [Element 2] | [Description] | [Purpose] |

---

#### State Management

| State | Visual | Description |
|-------|--------|-------------|
| Loading | [Spinner / Skeleton] | Data is being fetched |
| Ready | [Full content] | Data loaded, ready for interaction |
| Processing | [Spinner on action] | Action in progress |
| Success | [Success message] | Action completed successfully |
| Error | [Error message] | Action failed |
| Empty | [Empty state] | No data available |

#### Error Handling

| Error Type | Display | User Action |
|------------|---------|-------------|
| [Error 1] | [How shown] | [What user can do] |
| [Error 2] | [How shown] | [What user can do] |

#### Animations

| Animation | Trigger | Duration | Easing |
|-----------|---------|----------|--------|
| Open | [Click hotspot] | [ms] | [easing] |
| Close | [Click close] | [ms] | [easing] |
| Content Load | [Data ready] | [ms] | [easing] |

#### Accessibility

```yaml
ARIA Role: [dialog / alertdialog]
ARIA Label: [Description]
Focus Trap: [yes / no]
Escape to Close: [yes / no]
Initial Focus: [Element to focus]
```

---

### Overlay: [OVERLAY-002] [Overlay Name]

*[Repeat structure for all overlays]*

---

## Overlay Types Reference

### Simple Overlay

**Use for:** Viewing data, simple actions

**Characteristics:**
- Single section
- No forms or minimal input
- One primary action

**Example:** View balance, confirm action, display notification

---

### Medium Overlay

**Use for:** Forms, multi-step actions

**Characteristics:**
- Multiple sections
- Form inputs
- Primary + secondary actions

**Example:** Deposit form, settings panel, profile edit

---

### Complex Overlay

**Use for:** Multi-step workflows, rich functionality

**Characteristics:**
- Multiple steps or tabs
- Rich data visualization
- Multiple actions

**Example:** Trading interface, analytics dashboard, wizard

---

## Overlay Interaction Patterns

### Single Action Pattern

```
Open Overlay → Display Data → User Action → Close → Environment
```

### Form Submission Pattern

```
Open Overlay → Display Form → User Input → Validation → Submit → Loading → Success/Error → Close → Environment
```

### Multi-Step Pattern

```
Open Overlay → Step 1 → Step 2 → ... → Final Step → Close → Environment
```

### Confirmation Pattern

```
Open Overlay → Display Confirmation → Confirm/Cancel → Execute → Close → Environment
```

---

## Data Flow

### Overlay Data Architecture

```
┌─────────────────┐
│   Environment   │
│   (User clicks  │
│    hotspot)     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│     Overlay     │
│   (Opens with   │
│   loading state)│
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Truth Layer    │
│  (API/Contract  │
│   call made)    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│     Overlay     │
│  (Data displayed│
│   user interacts)│
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Truth Layer    │
│  (Action executed│
│   if applicable)│
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│     Overlay     │
│   (Closes,      │
│   returns user) │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   Environment   │
│  (User continues)│
└─────────────────┘
```

---

## Example: Complete Overlay Specification

### Overlay: Vault Management

```yaml
Overlay ID: OVERLAY-001
Overlay Name: Vault Management
Triggered By: HS-001 (vault-hotspot)
Purpose: Allow users to view balance, deposit, and withdraw assets
Complexity: Medium
```

**Visual:**
- Width: 500px
- Height: Auto (max 80vh)
- Position: Centered
- Background: #1a1a2e
- Border Radius: 16px
- Shadow: 0 20px 60px rgba(0,0,0,0.5)

**Background Treatment:**
- Environment dimmed to 30% opacity
- Click outside closes overlay

**Content:**

| Section | Elements |
|---------|----------|
| Header | Title: "Vault", Close button (X) |
| Data Display | Balance, APY, Total Deposited |
| Form | Deposit amount input |
| Actions | Deposit button, Withdraw button |
| Footer | Last transaction timestamp |

**States:**

| State | Treatment |
|-------|-----------|
| Loading | Skeleton screens for data |
| Ready | Full content with current data |
| Processing | Button shows spinner, disabled |
| Success | Green checkmark, auto-close after 2s |
| Error | Red error message, retry option |

---

## Validation Checklist

- [ ] Every hotspot maps to one overlay
- [ ] Every overlay has clear purpose
- [ ] Overlay dimensions defined
- [ ] All data sources documented
- [ ] All actions defined
- [ ] Loading states designed
- [ ] Error handling specified
- [ ] Close mechanism defined
- [ ] Accessibility attributes set
- [ ] Animations specified
- [ ] Background treatment defined

---

> **Template Version:** SEI v1.0
