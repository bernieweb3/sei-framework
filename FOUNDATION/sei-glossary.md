# SEI Terminology Glossary

> Standardized vocabulary for Spatial Experience Interface design, development, and communication.

---

## Core Concepts

### Environment
**Definition:** The spatial context that contains all interactive elements.

**Characteristics:**
- Provides immediate cognitive orientation
- Establishes the "world" where interaction happens
- Remains static during overlay interactions
- Examples: Laboratory, City, Campus, Office, Command Center

**Usage:** "The Banking Environment uses a financial district as its spatial context."

---

### Object
**Definition:** A visual entity within the environment that represents a system capability.

**Characteristics:**
- Visible and recognizable
- Maps to exactly one primary function
- Has a hotspot for interaction
- Opens an overlay when activated

**Usage:** "The Vault object represents the asset storage capability."

---

### Hotspot
**Definition:** An invisible interaction area mapped to an object.

**Characteristics:**
- Not visually rendered (or subtly indicated)
- Positioned absolutely over objects
- Triggers overlay on interaction
- Single responsibility: one hotspot = one overlay

**Usage:** "Click the vault-hotspot to open the asset management overlay."

---

### Overlay
**Definition:** A modal interface that contains data, forms, and actions.

**Characteristics:**
- Opens above the environment
- Contains the actual logic and functionality
- Must close to return to environment
- Can be dismissed to cancel action

**Usage:** "The Deposit Overlay displays balance and handles deposit transactions."

---

## System Layers

### Truth Layer
**Definition:** The authoritative source of all data and system state.

**Components:**
- APIs
- Smart contracts
- Databases
- Backend services
- External data sources

**Rule:** The Experience Layer must never fabricate Truth Layer data.

**Usage:** "User balance comes from the Truth Layer via smart contract call."

---

### Experience Layer
**Definition:** The visual and interactive representation of the system.

**Components:**
- Environment visuals
- Object representations
- Hotspot interactions
- Overlay interfaces
- Narrative framing

**Rule:** The Experience Layer represents but never replaces the Truth Layer.

**Usage:** "The Experience Layer renders the laboratory environment with all interactive objects."

---

## Spatial Concepts

### Zone
**Definition:** A designated area within the environment with a specific purpose.

**The Five Universal Zones:**

| Zone        | Purpose                          | Typical Content                    |
|-------------|----------------------------------|------------------------------------|
| CORE        | Orientation and identity         | Central landmark, main feature     |
| ACTION      | Primary work area                | Terminals, machines, consoles      |
| TOOL        | Supporting functions             | Settings, utilities, configuration |
| PROGRESSION | Feedback and status              | Stats, achievements, milestones    |
| PROFILE     | User identity                    | Avatar, user info, personal data   |

**Usage:** "The Terminal is placed in the ACTION zone for easy access."

---

### Perspective
**Definition:** The visual viewpoint from which the environment is rendered.

**Types:**
- **Isometric:** 3D view with parallel projection (common in games)
- **Top-down:** Directly overhead view
- **Flat:** 2D illustration with depth cues
- **3D Perspective:** Realistic depth with vanishing points

**Usage:** "The Education Environment uses an isometric campus view."

---

## Interaction Concepts

### Interaction Flow
**Definition:** The sequence of user actions through the SEI system.

**Standard Flow:**
```
Environment → Object → Hotspot → Overlay → Action → Environment
```

**Usage:** "The interaction flow for deposits starts at the Bank object."

---

### Spatial Memory
**Definition:** User's ability to remember object locations based on spatial context.

**Principle:** Users remember "the vault is on the left" better than "click menu item #3."

**Usage:** "Consistent object positioning leverages spatial memory."

---

### Progressive Disclosure
**Definition:** Revealing additional objects or options only when relevant.

**Usage:** "Advanced options use progressive disclosure to avoid overwhelming new users."

---

## Design Concepts

### Narrative Framing
**Definition:** Describing system actions using story-like language.

**Examples:**
| System Action | Narrative Frame           |
|---------------|---------------------------|
| Open dataset  | "Enter the archive"       |
| Deposit funds | "Secure your assets"      |
| Run analysis  | "Conduct an experiment"   |
| View report   | "Check the records"       |

**Usage:** "Narrative framing makes 'database query' feel like 'exploring the library.'"

---

### Visual Anchor
**Definition:** A prominent visual element that helps users orient themselves.

**Examples:** Central building, distinctive landmark, unique color scheme

**Usage:** "The Command Tower serves as the visual anchor for the environment."

---

### Cognitive Load
**Definition:** The mental effort required to use the interface.

**SEI Target:** Low cognitive load through spatial familiarity and object affordances.

**Usage:** "Limiting to 5 objects reduces cognitive load for new users."

---

## Technical Terms

### Mock Data
**Definition:** Simulated data used during development.

**Rule:** Mock data is allowed in development but must be replaced before deployment.

**Usage:** "Remove all mock data before connecting to the Truth Layer."

---

### Authoritative Source
**Definition:** The primary system of record for a data type.

**Examples:**
| Data Type   | Authoritative Source        |
|-------------|-----------------------------|
| Balance     | Smart contract / Bank API   |
| User profile| Identity service / Database |
| Analytics   | Data warehouse / API        |
| Content     | CMS / Content API           |

**Usage:** "User XP must come from the authoritative source, never local storage."

---

### State Synchronization
**Definition:** Keeping the Experience Layer aligned with the Truth Layer.

**Methods:**
- Polling
- WebSockets
- Server-Sent Events
- Manual refresh

**Usage:** "Implement state synchronization to reflect balance changes immediately."

---

## Abbreviations

| Abbreviation | Full Term                        |
|--------------|----------------------------------|
| SEI          | Spatial Experience Interface     |
| UI           | User Interface                   |
| UX           | User Experience                  |
| API          | Application Programming Interface|
| CMS          | Content Management System        |

---

## Related Paradigms

| Paradigm           | Description                              |
|--------------------|------------------------------------------|
| Traditional UI     | Menu-based, page-navigation interfaces   |
| Dashboard UI       | Data-dense, widget-based interfaces      |
| Game UI            | HUD, inventory, spatial game interfaces  |
| Spatial UI         | 3D-space-based interaction (VR/AR)       |
| **SEI**            | 2D spatial context with functional objects|

---

> **Note:** This glossary ensures all stakeholders (designers, developers, AI builders, product managers) use consistent terminology when discussing SEI systems.
