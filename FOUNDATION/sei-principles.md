# SEI Core Principles

> **Spatial Experience Interface (SEI)**  
> A software interface where system capabilities are represented as spatial objects inside a contextual environment, and users interact with those objects instead of navigating menus.

---

## Principle 1: Context Before Function

```
User understands the environment FIRST.
User understands the function SECOND.
```

The spatial context provides immediate cognitive orientation. A library implies knowledge. A bank implies assets. A lab implies experiments.

**Rule:** Never present functionality without first establishing its spatial context.

---

## Principle 2: Objects Represent Capabilities

```
Every visible object = One system capability
```

Objects are not decoration. They are the interface.

| Object   | Implied Capability |
|----------|-------------------|
| Terminal | Configure, Operate |
| Vault    | Store, Secure      |
| Board    | View, Monitor      |
| Archive  | Read, Retrieve     |
| Machine  | Process, Execute   |

**Rule:** If an object exists in the environment, it must map to a real system function.

---

## Principle 3: Navigation Through Space

```
Traditional: Menu → Page → Form → Action
SEI:        Environment → Object → Overlay → Action
```

Users navigate by moving attention through space, not by clicking through hierarchical menus.

**Rule:** No menus. No page navigation. No routing-based transitions.

---

## Principle 4: Overlays Contain Logic

```
Environment = Context
Overlay     = Logic
```

The environment provides orientation. The overlay provides functionality.

**Rule:** All data display, forms, and actions happen inside overlays. The environment remains static during interaction.

---

## Principle 5: Truth Layer Dominates Experience Layer

```
Layer 1 (Truth):     APIs, Smart Contracts, Database, Backend
Layer 2 (Experience): Environment, Objects, Visuals, Narrative
```

The Experience Layer must never fabricate data. It must only represent the Truth Layer.

**Rule:** If data exists in the UI, it must come from an authoritative source. No mock data. No simulation.

---

## Principle 6: Style Must Not Alter Interaction Structure

```
Style changes: Visual theme, Art direction, Narrative framing
Style preserves: Interaction pattern, Object mapping, Flow structure
```

The same SEI system can look like:
- A cyberpunk city
- A university campus
- A corporate office
- A fantasy village

The backend and interaction structure remain identical.

**Rule:** Style is a skin. Architecture is the skeleton. Never let skin change skeleton.

---

## Principle 7: Spatial Memory Over Menu Memory

```
Humans remember places better than lists.
```

Users will remember "the vault is on the left" faster than "click Finance → Accounts → Savings."

**Rule:** Design for spatial memory. Keep object positions consistent.

---

## Principle 8: Narrative Reduces Complexity

```
"Enter the archive" feels simpler than "Open dataset management module"
```

Framing actions as narrative experiences reduces perceived cognitive load.

**Rule:** Use narrative language to describe system operations.

---

## Principle 9: Maximum Cognitive Load Limit

```
Maximum 5-8 interactive objects per environment view
```

Too many objects create decision paralysis.

**Rule:** If you need more than 8 objects, create sub-environments or use progressive disclosure.

---

## Principle 10: Return to Environment

```
Every interaction must return to the environment.
```

The environment is the home state. Overlays open, actions complete, overlays close, user returns to environment.

**Rule:** Never trap users in overlay states. Always provide a path back to the spatial context.

---

## Summary: The SEI Mantra

```
Context first.
Objects speak.
Overlays act.
Truth rules.
Space remembers.
```
