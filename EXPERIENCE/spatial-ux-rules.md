# Spatial UX Design Rules

> User experience guidelines for designing intuitive and effective Spatial Experience Interfaces.

---

## Core UX Principles

### Principle 1: Spatial Memory Over Menu Memory

```
Humans remember places better than lists.
```

**Application:**
- Keep object positions consistent
- Use spatial relationships to group related functions
- Allow users to develop mental maps of the environment

**Example:**
```
❌ "Click menu item #4, then submenu item #2"
✅ "The vault is on the left, the exchange is on the right"
```

---

### Principle 2: Object Affordances

```
Objects should visually imply their function.
```

**Affordance Guidelines:**

| Object Type | Visual Cues | Implied Function |
|-------------|-------------|------------------|
| Terminal | Screen, keyboard, buttons | Configure, operate |
| Vault | Heavy door, lock, metal | Store, secure |
| Board | Flat surface, displays | View, read |
| Archive | Shelves, folders, books | Retrieve, browse |
| Machine | Gears, pipes, activity | Process, execute |
| Chest | Container, lid | Collect, open |
| Portal | Doorway, glow | Navigate, enter |
| Garden | Plants, growth | Cultivate, grow |

**Design Checklist:**
- [ ] Can users guess the function without labels?
- [ ] Do objects look interactive?
- [ ] Are affordances culturally universal?

---

### Principle 3: Cognitive Load Management

```
Maximum 5-8 interactive objects per view.
```

**Why:** Miller's Law - humans can hold 7±2 items in working memory.

**Strategies:**

| Situation | Solution |
|-----------|----------|
| Too many functions | Group into categories |
| Complex workflows | Multi-step overlays |
| Rare functions | Progressive disclosure |
| Power user features | Advanced mode toggle |

**Object Count Guidelines:**

| User Type | Max Objects | Reason |
|-----------|-------------|--------|
| Novice | 5 | Lower cognitive load |
| Regular | 7 | Familiarity allows more |
| Expert | 8 | Efficiency over discovery |

---

### Principle 4: Visual Hierarchy

```
Guide attention through size, color, and position.
```

**Hierarchy Levels:**

```
Level 1 (Primary):   CORE zone objects - largest, most prominent
Level 2 (Secondary): ACTION zone objects - medium size
Level 3 (Tertiary):  TOOLS zone objects - smaller, subtle
Level 4 (Ambient):   Background elements - decorative only
```

**Visual Weight Factors:**

| Factor | High Attention | Low Attention |
|--------|---------------|---------------|
| Size | Large | Small |
| Color | Bright, saturated | Muted, desaturated |
| Contrast | High | Low |
| Animation | Moving | Static |
| Position | Center, eye-level | Edge, corner |

---

### Principle 5: Consistent Spatial Relationships

```
Related objects should be near each other.
```

**Grouping Principles:**

| Relationship | Spatial Treatment |
|--------------|-------------------|
| Functional | Objects near each other |
| Sequential | Objects in a path |
| Hierarchical | Objects around a center |
| Categorical | Objects in a zone |

**Example Layout:**
```
        [PROFILE]

[TOOLS]  [CORE]  [ACTIONS]
Settings  Main    Bank
          Hub     Exchange
                  Vault

      [PROGRESSION]
```

---

## Zone Design Rules

### CORE Zone Rules

**Purpose:** Orientation and identity

**Rules:**
- Must be visually dominant
- Should be immediately recognizable
- Represents the "heart" of the environment
- Usually contains 1-2 primary objects

**Examples:**
- Central plaza in a city
- Main building on a campus
- Command center in a facility

---

### ACTION Zone Rules

**Purpose:** Primary work area

**Rules:**
- Contains the most-used functions
- Objects should be easily accessible
- Visual treatment should invite interaction
- Usually contains 3-4 objects

**Examples:**
- Bank, exchange, vault in DeFi
- Terminals, workstations in offices
- Classrooms, labs in education

---

### TOOLS Zone Rules

**Purpose:** Supporting functions

**Rules:**
- Less prominent than ACTION zone
- Contains configuration and utilities
- Should not compete for attention
- Usually contains 1-2 objects

**Examples:**
- Settings console
- Help desk
- Configuration panel

---

### PROGRESSION Zone Rules

**Purpose:** Feedback and motivation

**Rules:**
- Visible but not distracting
- Shows status and achievements
- Updates to reflect progress
- Usually contains 1-2 elements

**Examples:**
- Stats board
- Achievement display
- Progress tracker

---

### PROFILE Zone Rules

**Purpose:** User identity

**Rules:**
- Consistently positioned (usually top)
- Shows user info at a glance
- May be interactive (opens profile overlay)
- Should be subtle but accessible

**Examples:**
- User avatar and name
- Wallet address display
- Character portrait

---

## Interaction Design Rules

### Hover State Rules

**Purpose:** Indicate interactivity

**Guidelines:**

| Element | Hover Treatment |
|---------|-----------------|
| Objects | Subtle glow or highlight |
| Hotspots | Slight opacity increase |
| Labels | Underline or color change |

**Timing:**
- Hover delay: 0ms (immediate)
- Hover-off delay: 100ms (prevents flicker)

---

### Click Feedback Rules

**Purpose:** Confirm action received

**Guidelines:**

| Action | Feedback |
|--------|----------|
| Click | Immediate visual response |
| Loading | Spinner or progress indicator |
| Success | Checkmark or success animation |
| Error | Shake or error color |

**Timing:**
- Click feedback: < 100ms
- Loading state: < 500ms
- Result display: < 2 seconds

---

### Overlay Transition Rules

**Purpose:** Smooth context switching

**Guidelines:**

| Transition | Duration | Easing |
|------------|----------|--------|
| Overlay open | 200-300ms | ease-out |
| Overlay close | 150-200ms | ease-in |
| Content load | 100-200ms | ease-out |

**Effects:**
- Environment dims (opacity 0.3-0.5)
- Overlay scales up slightly (0.95 → 1.0)
- Backdrop blurs optionally

---

## Feedback Design Rules

### Immediate Feedback

**Rule:** Every user action must have immediate visual feedback.

| Action | Feedback |
|--------|----------|
| Hover | Highlight, cursor change |
| Click | Press effect, ripple |
| Drag | Follow cursor, drop zone highlight |
| Scroll | Parallax, content movement |

---

### Progress Feedback

**Rule:** Show progress for operations > 1 second.

| Duration | Feedback Type |
|----------|---------------|
| < 1s | Spinner |
| 1-5s | Progress bar |
| > 5s | Progress bar + ETA |

---

### Success Feedback

**Rule:** Confirm successful completion.

| Context | Feedback |
|---------|----------|
| Form submit | Checkmark, green color |
| Transaction | Success message, confetti (optional) |
| Achievement | Badge, animation, sound |

---

### Error Feedback

**Rule:** Clear, actionable error messages.

| Error Type | Message Format |
|------------|----------------|
| Validation | "[Field] must be [requirement]" |
| Network | "Connection lost. Please try again." |
| Server | "Something went wrong. [Error code]" |
| Permission | "You don't have permission to [action]" |

---

## Animation Rules

### Purposeful Animation

**Rule:** Every animation must serve a purpose.

| Purpose | Animation Type |
|---------|----------------|
| Attention | Pulse, glow |
| Feedback | Scale, color change |
| Transition | Fade, slide |
| Delight | Bounce, elastic |

### Animation Timing

| Type | Duration | Use Case |
|------|----------|----------|
| Micro | 50-150ms | Hover, click feedback |
| Small | 150-300ms | State changes |
| Medium | 300-500ms | Transitions |
| Large | 500-1000ms | Major changes |

### Performance Rules

- Use `transform` and `opacity` only
- Avoid animating `width`, `height`, `top`, `left`
- Use `will-change` sparingly
- Target 60fps

---

## Accessibility Rules

### Color Contrast

| Element | Minimum Ratio |
|---------|---------------|
| Normal text | 4.5:1 |
| Large text | 3:1 |
| UI components | 3:1 |

### Focus Management

- All interactive elements must be focusable
- Focus order must be logical
- Focus indicator must be visible
- No focus traps

### Motion Sensitivity

- Respect `prefers-reduced-motion`
- Provide static alternatives
- Avoid auto-playing animations

---

## Responsive UX Rules

### Mobile Adaptations

| Element | Desktop | Mobile |
|---------|---------|--------|
| Object size | 100-150px | 60-80px |
| Hotspot size | Object size | Min 44px |
| Overlay width | 400-600px | 90% viewport |
| Spacing | 20-40px | 10-20px |

### Touch Interactions

- Touch targets minimum 44×44px
- No hover-dependent interactions
- Swipe gestures for common actions
- Pinch to zoom if applicable

---

## Validation Checklist

### Spatial Design

- [ ] Object positions are consistent
- [ ] Spatial relationships are logical
- [ ] Visual hierarchy guides attention
- [ ] Object count ≤ 8
- [ ] Affordances are clear

### Interaction Design

- [ ] Hover states exist
- [ ] Click feedback is immediate
- [ ] Transitions are smooth
- [ ] Loading states are shown
- [ ] Error states are handled

### Feedback Design

- [ ] Every action has feedback
- [ ] Progress is shown for long operations
- [ ] Success is confirmed
- [ ] Errors are clear and actionable

### Animation

- [ ] Animations serve a purpose
- [ ] Timing feels natural
- [ ] Performance is smooth (60fps)
- [ ] Reduced motion is supported

### Accessibility

- [ ] Color contrast meets standards
- [ ] Keyboard navigation works
- [ ] Screen reader compatible
- [ ] Focus management is correct

---

> **Template Version:** SEI v1.0
