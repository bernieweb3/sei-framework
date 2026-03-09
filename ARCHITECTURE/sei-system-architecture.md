# SEI System Architecture

> High-level architecture of a Spatial Experience Interface system.

---

## Architecture Overview

SEI follows a layered architecture that separates concerns while maintaining a clear flow from user interaction to system execution.

### Full Stack Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                         USER                                │
│                   (Person interacting)                      │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            │ Sees, interacts
                            ▼
┌─────────────────────────────────────────────────────────────┐
│  ┌─────────────────────────────────────────────────────┐    │
│  │                  EXPERIENCE LAYER                    │    │
│  │                                                      │    │
│  │  ┌─────────────┐                                    │    │
│  │  │ Environment │  ← Spatial context                 │    │
│  │  │  (Visual)   │    (laboratory, city, campus)      │    │
│  │  └──────┬──────┘                                    │    │
│  │         │                                           │    │
│  │         ▼                                           │    │
│  │  ┌─────────────┐                                    │    │
│  │  │   Objects   │  ← Functional entities             │    │
│  │  │  (Visual)   │    (vault, terminal, board)        │    │
│  │  └──────┬──────┘                                    │    │
│  │         │                                           │    │
│  │         ▼                                           │    │
│  │  ┌─────────────┐                                    │    │
│  │  │   Hotspots  │  ← Interaction triggers            │    │
│  │  │ (Invisible) │    (click/tap areas)               │    │
│  │  └──────┬──────┘                                    │    │
│  │         │                                           │    │
│  │         ▼                                           │    │
│  │  ┌─────────────┐                                    │    │
│  │  │   Overlays  │  ← Functionality containers        │    │
│  │  │   (Modal)   │    (forms, data, actions)          │    │
│  │  └─────────────┘                                    │    │
│  │                                                      │    │
│  └─────────────────────────────────────────────────────┘    │
│                            │                                │
│                            │ Reads / Writes                 │
│                            ▼                                │
│  ┌─────────────────────────────────────────────────────┐    │
│  │                   TRUTH LAYER                        │    │
│  │                                                      │    │
│  │  ┌─────────┐  ┌─────────┐  ┌─────────┐             │    │
│  │  │   APIs  │  │Database │  │Contracts│             │    │
│  │  │ (REST)  │  │ (SQL)   │  │(Web3)   │             │    │
│  │  └─────────┘  └─────────┘  └─────────┘             │    │
│  │                                                      │    │
│  └─────────────────────────────────────────────────────┘    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Layer Responsibilities

### User Layer

**Purpose:** The human interacting with the system.

**Characteristics:**
- Uses spatial memory to navigate
- Recognizes objects by appearance
- Expects consistent behavior
- Benefits from contextual orientation

---

### Experience Layer

**Purpose:** Provide visual context and interaction interface.

**Components:**

#### 1. Environment

**Responsibility:** Establish spatial context.

**Contains:**
- Visual background
- The five zones (CORE, ACTION, TOOLS, PROGRESSION, PROFILE)
- Non-interactive decorative elements
- Lighting and atmosphere

**Rules:**
- Remains visible during overlay interactions
- Provides immediate cognitive orientation
- Never contains functionality directly

**Example:**
```
A laboratory environment with:
- Workbenches (ACTION zone)
- Equipment cabinets (TOOLS zone)
- Central atrium (CORE zone)
- Achievement display (PROGRESSION zone)
- Researcher badge (PROFILE zone)
```

---

#### 2. Objects

**Responsibility:** Represent system capabilities visually.

**Characteristics:**
- One object = One primary function
- Visually distinct and recognizable
- Positioned within appropriate zones
- Implies function through appearance

**Rules:**
- Maximum 5-8 interactive objects
- Each maps to exactly one overlay
- Affordances must be clear

**Example:**
```
Microscope → Experiment overlay
Data terminal → Analytics overlay
Sample vault → Storage overlay
```

---

#### 3. Hotspots

**Responsibility:** Capture user interaction on objects.

**Characteristics:**
- Invisible or subtly indicated
- Positioned over objects
- Single interaction mapping
- Absolute positioning

**Rules:**
- One hotspot per object
- Minimum touch target 44×44px
- Hover effects indicate interactivity

**Example:**
```
Hotspot over microscope:
- Position: X: 35%, Y: 40%
- Size: W: 12%, H: 15%
- Opens: experiment-overlay
```

---

#### 4. Overlays

**Responsibility:** Contain all functionality, forms, and data.

**Characteristics:**
- Modal interface above environment
- Contains actual system logic
- Must be closable
- Data comes from Truth Layer

**Rules:**
- All actions happen in overlays
- Environment remains visible behind
- Clear close mechanism required
- Return to environment after completion

**Example:**
```
Experiment overlay contains:
- Parameter inputs
- Run button
- Results display
- Close button
```

---

### Truth Layer

**Purpose:** Provide authoritative data and execute system operations.

**Components:**

#### APIs

**Responsibility:** Serve data and handle operations via HTTP.

**Examples:**
- REST endpoints
- GraphQL APIs
- WebSocket connections

**Data:**
- User profiles
- Application state
- Computed metrics
- Configuration

---

#### Database

**Responsibility:** Persistent structured storage.

**Examples:**
- PostgreSQL
- MongoDB
- Redis (cache)

**Data:**
- User data
- Transaction history
- Settings
- Session state

---

#### Smart Contracts

**Responsibility:** On-chain logic and state (Web3 applications).

**Examples:**
- DeFi protocols
- NFT contracts
- Governance systems

**Data:**
- Token balances
- Ownership records
- Protocol state

---

## Data Flow

### Read Flow (Display Data)

```
User clicks object
        ↓
Hotspot triggers
        ↓
Overlay opens (loading state)
        ↓
API/Contract/DB query
        ↓
Data returns
        ↓
Overlay displays data
        ↓
User views/interacts
        ↓
Overlay closes
        ↓
Return to environment
```

### Write Flow (Execute Action)

```
User clicks object
        ↓
Hotspot triggers
        ↓
Overlay opens with form
        ↓
User fills form
        ↓
User submits
        ↓
Validation (client-side)
        ↓
API/Contract call
        ↓
Processing state
        ↓
Success/Error response
        ↓
Feedback displayed
        ↓
Overlay closes
        ↓
Return to environment
        ↓
Environment reflects changes
```

---

## Component Relationships

### One-to-One Mappings

```
Object ──────→ Hotspot ──────→ Overlay ──────→ API/Contract
  │               │               │               │
  │               │               │               │
  └─ One object   └─ One hotspot  └─ One overlay  └─ One endpoint
     per            per object      per hotspot     per action
     function
```

### Many-to-One Relationships

```
Multiple objects ──────→ One environment
Multiple overlays ─────→ One environment state
Multiple API calls ────→ One Truth Layer
```

---

## State Management

### Experience Layer State

```typescript
interface ExperienceState {
  // Which overlay is currently open
  activeOverlay: string | null;
  
  // Data for the active overlay
  overlayData: any;
  
  // Loading states
  isLoading: boolean;
  
  // Environment state (optional animations)
  environmentState: {
    objectStates: Record<string, ObjectState>;
    ambientAnimations: boolean;
  };
}
```

### Truth Layer State

```typescript
interface TruthState {
  // User-specific data
  user: User;
  
  // Application data
  data: ApplicationData;
  
  // Real-time updates
  subscriptions: Subscription[];
}
```

### Synchronization

```
Truth Layer changes
        ↓
Event emitted (WebSocket/Polling)
        ↓
Experience Layer receives
        ↓
State updates
        ↓
UI re-renders
```

---

## Architectural Principles

### Principle 1: Separation of Concerns

```
Experience Layer: HOW things look and feel
Truth Layer:      WHAT data exists and operations do
```

### Principle 2: Single Source of Truth

```
All data originates from Truth Layer.
Experience Layer only displays, never invents.
```

### Principle 3: Environment Persistence

```
Environment remains in DOM at all times.
Overlays are temporary layers above.
```

### Principle 4: Stateless Overlays

```
Overlays receive data via props/context.
Overlays don't maintain persistent state.
```

---

## Technology Stack Examples

### Web Stack

| Layer | Technology Options |
|-------|-------------------|
| Frontend Framework | React, Vue, Svelte |
| State Management | Zustand, Redux, Context |
| Styling | Tailwind, CSS Modules |
| Animation | Framer Motion, GSAP |
| Data Fetching | React Query, SWR |

### Backend Stack

| Component | Technology Options |
|-----------|-------------------|
| API | Node.js, Python, Go |
| Database | PostgreSQL, MongoDB |
| Real-time | WebSocket, SSE |
| Auth | JWT, OAuth, Wallet |

### Web3 Stack

| Component | Technology Options |
|-----------|-------------------|
| Contracts | Solidity, Rust |
| Interaction | ethers.js, web3.js |
| Indexing | The Graph, Subsquid |

---

## Scalability Considerations

### Horizontal Scaling

| Component | Scaling Strategy |
|-----------|------------------|
| Environment | Static assets, CDN |
| Objects | Component library |
| Hotspots | Configuration-driven |
| Overlays | Component library |
| APIs | Load balancing |
| Database | Read replicas |

### Performance Optimization

| Strategy | Implementation |
|----------|----------------|
| Lazy loading | Load overlays on demand |
| Code splitting | Separate overlay bundles |
| Caching | Cache Truth Layer data |
| Debouncing | Limit rapid interactions |

---

## Security Considerations

### Experience Layer

- No secrets in client code
- Input validation before API calls
- XSS prevention

### Truth Layer

- Authentication required
- Authorization checks
- Rate limiting
- Input sanitization

---

## Summary

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   USER                                                  │
│     │                                                   │
│     ▼                                                   │
│   ┌─────────────────┐                                   │
│   │  ENVIRONMENT    │ ← Context                         │
│   │    (Visual)     │                                   │
│   └────────┬────────┘                                   │
│            │                                            │
│   ┌────────▼────────┐                                   │
│   │    OBJECTS      │ ← Capabilities                    │
│   │    (Visual)     │                                   │
│   └────────┬────────┘                                   │
│            │                                            │
│   ┌────────▼────────┐                                   │
│   │    HOTSPOTS     │ ← Interaction                     │
│   │   (Invisible)   │                                   │
│   └────────┬────────┘                                   │
│            │                                            │
│   ┌────────▼────────┐                                   │
│   │    OVERLAYS     │ ← Functionality                   │
│   │    (Modal)      │                                   │
│   └────────┬────────┘                                   │
│            │                                            │
│   ┌────────▼────────┐                                   │
│   │   TRUTH LAYER   │ ← Authority                       │
│   │  (API/DB/Chain) │                                   │
│   └─────────────────┘                                   │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

The architecture ensures:
- Clear separation of concerns
- Maintainable codebase
- Scalable structure
- Consistent user experience

---

> **Template Version:** SEI v1.0
