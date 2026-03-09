# SEI Interaction Model

> The universal interaction pattern for all Spatial Experience Interfaces.

---

## The Core Pattern

Every SEI interaction follows this exact sequence:

```
┌─────────────┐
│ Environment │ ◄────────── Home state
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   Object    │ ◄────────── User recognizes capability
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   Hotspot   │ ◄────────── User initiates interaction
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   Overlay   │ ◄────────── System presents functionality
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   Action    │ ◄────────── User executes operation
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ Environment │ ◄────────── Return to home state
└─────────────┘
```

---

## Detailed Flow Description

### Phase 1: Environment Perception

**State:** User views the spatial environment

**Purpose:** Provide immediate context and orientation

**Requirements:**
- Environment must be visually complete
- All interactive objects must be visible
- Visual anchor must be prominent
- No overlays or modals visible

**User Mental Model:** "I am in a [laboratory/city/office/campus]."

**Success Criteria:** User can describe the environment type within 2 seconds.

---

### Phase 2: Object Recognition

**State:** User identifies objects in the environment

**Purpose:** Help user understand available capabilities

**Requirements:**
- Objects must be visually distinct
- Object affordances must be clear
- Object positions must be consistent
- Maximum 5-8 interactive objects visible

**User Mental Model:** "That vault probably stores assets. That terminal probably configures settings."

**Success Criteria:** User can correctly guess at least 3 object functions without labels.

---

### Phase 3: Hotspot Interaction

**State:** User interacts with an object via its hotspot

**Purpose:** Initiate the capability associated with the object

**Requirements:**
- Hotspot must cover the entire interactive area
- Hover state should indicate interactivity (optional)
- Click/tap must trigger immediately
- Only one hotspot per object

**User Action:** Click or tap on the object

**Success Criteria:** Interaction triggers in <100ms with clear visual feedback.

---

### Phase 4: Overlay Presentation

**State:** Overlay opens above the environment

**Purpose:** Present data and actions related to the selected capability

**Requirements:**
- Environment must remain visible (dimmed/frozen)
- Overlay must contain all relevant functionality
- Data must come from Truth Layer
- Clear close/dismiss mechanism

**User Mental Model:** "I'm now using the [vault/terminal/archive] functionality."

**Success Criteria:** User can complete intended task without leaving overlay.

---

### Phase 5: Action Execution

**State:** User performs actions within the overlay

**Purpose:** Execute system operations

**Requirements:**
- Actions must trigger Truth Layer calls
- Feedback must be immediate
- Error states must be handled
- Loading states must be shown

**User Action:** Fill forms, click buttons, make selections

**Success Criteria:** Action completes with clear success/failure indication.

---

### Phase 6: Environment Return

**State:** Overlay closes, user returns to environment

**Purpose:** Restore spatial context and allow next interaction

**Requirements:**
- Overlay must close completely
- Environment must be fully visible
- Any state changes should be reflected
- User can immediately interact with new objects

**User Mental Model:** "I'm back in the [environment]. I can do something else now."

**Success Criteria:** User can interact with a different object within 1 second.

---

## Interaction Rules

### Rule 1: No Menu Navigation

```
❌ FORBIDDEN: Menu → Submenu → Page → Action
✅ REQUIRED:  Environment → Object → Overlay → Action
```

---

### Rule 2: No Page Routing

```
❌ FORBIDDEN: URL changes, page transitions, browser history manipulation
✅ REQUIRED: Single page, overlay-based interaction
```

---

### Rule 3: Environment Persistence

```
❌ FORBIDDEN: Environment changes during overlay interaction
✅ REQUIRED: Environment remains visible (dimmed) behind overlay
```

---

### Rule 4: Single Object Responsibility

```
❌ FORBIDDEN: One object opens multiple different overlays
✅ REQUIRED: One object = One overlay = One primary capability
```

---

### Rule 5: Mandatory Return

```
❌ FORBIDDEN: Trapping user in overlay without close option
✅ REQUIRED: Every overlay must have clear close/return mechanism
```

---

### Rule 6: Truth Layer Validation

```
❌ FORBIDDEN: Overlay actions without Truth Layer verification
✅ REQUIRED: All actions must sync with authoritative source
```

---

## Alternative Interaction Patterns

### Quick Action Pattern

For frequently used actions:

```
Environment → Object → Quick Action → Environment
```

- Skips overlay for simple actions
- Example: "Collect daily reward" from a chest object

---

### Multi-Step Overlay Pattern

For complex workflows:

```
Environment → Object → Overlay Step 1 → Overlay Step 2 → ... → Environment
```

- Multiple overlay screens within same capability
- Example: Deposit → Approve → Confirm

---

### Sub-Environment Pattern

For deeply nested capabilities:

```
Environment A → Object → Environment B → Object → Overlay → Environment A
```

- Transitions to a new spatial context
- Example: Campus → Building → Room → Terminal

---

## Error Handling Flow

```
Action Error
     │
     ▼
Error Display (in overlay)
     │
     ▼
User Acknowledgment
     │
     ▼
Return to Overlay (retry) OR Close Overlay (cancel)
```

---

## Loading State Flow

```
User Action
     │
     ▼
Loading Indicator (in overlay)
     │
     ▼
Truth Layer Response
     │
     ├─► Success → Success Display → Environment
     │
     └─► Error   → Error Display   → Retry/Cancel
```

---

## State Diagram

```
                    ┌─────────────┐
         ┌─────────│ Environment │◄────────┐
         │         │   (Home)    │         │
         │         └──────┬──────┘         │
         │                │                │
    Close│           Select Object         │
    Overlay│                │                │
         │                ▼                │
         │         ┌─────────────┐         │
         │         │   Overlay   │         │
         │         │   Opened    │         │
         │         └──────┬──────┘         │
         │                │                │
         │     ┌─────────┼─────────┐       │
         │     │         │         │       │
         │     ▼         ▼         ▼       │
         │  ┌─────┐  ┌─────┐  ┌─────┐     │
         │  │Form │  │View │  │Action│     │
         │  │Input│  │Data │  │Exec  │     │
         │  └──┬──┘  └──┬──┘  └──┬──┘     │
         │     │         │         │       │
         │     └─────────┼─────────┘       │
         │               │                 │
         │               ▼                 │
         │         ┌─────────────┐         │
         └────────│   Close     │─────────┘
                   │   Overlay   │
                   └─────────────┘
```

---

## Implementation Checklist

- [ ] Environment renders as single page
- [ ] All objects visible without scrolling
- [ ] Each object has exactly one hotspot
- [ ] Hotspots cover entire interactive area
- [ ] Overlays open on object interaction
- [ ] Overlays contain all relevant functionality
- [ ] Environment visible behind overlay (dimmed)
- [ ] Close button/function in every overlay
- [ ] Overlay closes return to environment
- [ ] No page navigation or routing
- [ ] No menu bars or navigation elements
- [ ] All data comes from Truth Layer
- [ ] Actions sync with Truth Layer
- [ ] Loading states shown during async operations
- [ ] Error handling within overlay context

---

> **Remember:** The interaction model is the skeleton of SEI. Every implementation must follow this pattern exactly. Style and theme can vary, but the flow must remain constant.
