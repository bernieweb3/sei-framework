# SEI Mental Model

> Understanding the paradigm shift from traditional UI to Spatial Experience Interface.

---

## Two Ways to Build Interfaces

Every software interface follows a mental model. The model determines how users understand, navigate, and interact with the system.

SEI represents a fundamental shift in this mental model.

---

## Traditional UI Mental Model

### The Flow

```
User → Menu → Page → Form → Action
```

### How Users Think

```
"I need to find the right menu item"
"Then navigate to the correct page"
"Then fill out the form"
"Then submit"
```

### Visual Representation

```
┌─────────────────────────────────────────┐
│  [Logo]  [Menu] [Menu] [Menu] [Profile] │  ← Navigation
├─────────────────────────────────────────┤
│                                         │
│  [Sidebar]                              │
│  ├── Menu Item                          │
│  ├── Menu Item                          │
│  └── Menu Item                          │
│                                         │
│         [Page Content]                  │
│         ┌─────────────┐                 │
│         │   Form      │                 │
│         │   ┌─────┐   │                 │
│         │   │Input│   │                 │
│         │   └─────┘   │                 │
│         │   [Submit]  │                 │
│         └─────────────┘                 │
│                                         │
└─────────────────────────────────────────┘
```

### Characteristics

| Aspect | Traditional UI |
|--------|----------------|
| Navigation | Hierarchical menus |
| Context | Abstract, text-based |
| Memory | Must remember menu paths |
| Discovery | Browse menus to find features |
| Orientation | "Where am I in the hierarchy?" |

---

## SEI Mental Model

### The Flow

```
User → Environment → Object → Hotspot → Overlay → Action → Environment
```

### How Users Think

```
"I see a laboratory"
"That microscope is for experiments"
"I click it to run an analysis"
"I complete the task"
"I'm back in the lab"
```

### Visual Representation

```
┌─────────────────────────────────────────┐
│                                         │
│              [PROFILE]                  │
│                                         │
│   [TOOLS]      [CORE]      [ACTIONS]    │
│   ⚙️          🏛️           🔬           │
│   Settings   Central      Experiment    │
│              Hub          Station       │
│                           💰            │
│                           Vault         │
│                                         │
│           [PROGRESSION]                 │
│           📊 Stats                      │
│                                         │
│     ┌─────────────────┐                 │
│     │   [Overlay]     │                 │
│     │   Experiment    │                 │
│     │   ┌─────────┐   │                 │
│     │   │  Form   │   │                 │
│     │   └─────────┘   │                 │
│     │   [Run]         │                 │
│     └─────────────────┘                 │
│                                         │
└─────────────────────────────────────────┘
```

### Characteristics

| Aspect | SEI |
|--------|-----|
| Navigation | Spatial, object-based |
| Context | Visual, environmental |
| Memory | Remember object locations |
| Discovery | Explore the environment |
| Orientation | "Where am I in this space?" |

---

## Side-by-Side Comparison

| Dimension | Traditional UI | SEI |
|-----------|----------------|-----|
| **Primary metaphor** | Filing system | Physical space |
| **Navigation unit** | Menu item | Object |
| **Context provider** | Breadcrumbs | Environment |
| **Feature discovery** | Browse menus | Explore space |
| **User memory** | Menu paths | Object locations |
| **Cognitive load** | Abstract hierarchy | Concrete spatial |
| **Visual density** | Text-heavy | Visual-first |
| **Interaction flow** | Page-to-page | Overlay-based |

---

## Why Spatial Cognition?

### The Science

Humans evolved to navigate physical spaces. Our brains are optimized for:

- **Spatial memory** — remembering where things are
- **Object recognition** — understanding what things do
- **Environmental context** — knowing what to expect in different places

### The Evidence

| Research Finding | Implication for UI |
|------------------|-------------------|
| People remember locations better than lists | Spatial UI reduces cognitive load |
| Context accelerates decision-making | Environment provides immediate orientation |
| Visual processing is faster than reading | Objects communicate faster than text |
| Narrative improves recall | Story framing enhances memory |

### The Result

```
Traditional: "Click Finance → Accounts → Savings → Deposit"
SEI:         "Click the vault, deposit"

Traditional: 4 steps to understand context
SEI:         Immediate context, 1 step to action
```

---

## Mental Model Transfer

### Users Already Understand

SEI leverages existing mental models from the real world:

| Environment | Real-World Parallel | User Expectation |
|-------------|---------------------|------------------|
| Library | Physical library | Knowledge, research |
| Bank | Financial institution | Money, security |
| Laboratory | Science lab | Experiments, analysis |
| Workshop | Craftsman's space | Building, creating |
| Command Center | Control room | Monitoring, operations |

### Zero Learning Curve

Users do not need to learn:
- Menu hierarchies
- Navigation patterns
- Where features are hidden

Users only need to:
- Recognize the environment
- Identify relevant objects
- Interact naturally

---

## When to Use Each Model

### Traditional UI Works Best For

- Content-heavy sites (news, blogs)
- E-commerce catalogs
- Documentation
- Admin dashboards (data-dense)

### SEI Works Best For

- Tool interfaces (AI, analytics, DeFi)
- Workflow systems
- Educational platforms
- Gaming applications
- Any system where context improves understanding

---

## The SEI Advantage

### For Users

| Benefit | Explanation |
|---------|-------------|
| Faster orientation | Environment provides immediate context |
| Easier recall | Spatial memory is more durable |
| Lower cognitive load | Concrete metaphors reduce abstraction |
| More engaging | Visual environments are inherently interesting |
| Better discovery | Exploration reveals features naturally |

### For Developers

| Benefit | Explanation |
|---------|-------------|
| Clear structure | Five zones organize functionality |
| Reusable patterns | Same architecture, different skins |
| AI-friendly | Prompts generate consistent output |
| Maintainable | Separation of concerns |
| Scalable | Add objects without restructuring |

---

## Making the Shift

### From Thinking in Pages

```
"I need to design the Settings page"
"What menu items should it have?"
"How do users navigate there?"
```

### To Thinking in Space

```
"I need a Settings object in the TOOLS zone"
"What should it look like?"
"What overlay opens when clicked?"
```

### Key Questions

| Traditional UI Question | SEI Question |
|------------------------|--------------|
| "What pages do we need?" | "What environment represents this system?" |
| "What's the menu structure?" | "What objects represent key functions?" |
| "Where does this feature go?" | "Which zone fits this capability?" |
| "How do users navigate there?" | "How do users discover this object?" |

---

## Summary

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   TRADITIONAL UI          →        SEI                  │
│                                                         │
│   Menu → Page → Form      →        Environment          │
│   ↓                       →           ↓                 │
│   Abstract hierarchy      →        Spatial context      │
│   ↓                       →           ↓                 │
│   Remember paths          →        Remember places      │
│   ↓                       →           ↓                 │
│   Text-first              →        Visual-first         │
│                                                         │
│   Filing cabinet          →        Physical world       │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

SEI does not replace traditional UI. It offers an alternative paradigm for systems where spatial context improves user understanding and experience.

---

> **Remember:** The goal is not to make software look like a game. The goal is to make complex systems feel intuitive by leveraging how humans naturally understand and remember spaces.

---

> **Template Version:** SEI v1.0
