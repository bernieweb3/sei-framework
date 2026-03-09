# SEI Starter Template

> Recommended project structure for implementing Spatial Experience Interfaces.

---

## Project Structure

This structure maps SEI architecture to a typical React-style codebase. Adapt to your framework of choice.

```
/src
├── components/
│   ├── environment/
│   │   ├── Environment.tsx       # Main environment container
│   │   ├── Background.tsx        # Visual background layer
│   │   └── index.ts
│   │
│   ├── objects/
│   │   ├── Vault.tsx             # Example object component
│   │   ├── Terminal.tsx          # Example object component
│   │   ├── Board.tsx             # Example object component
│   │   └── index.ts              # Object exports
│   │
│   ├── hotspots/
│   │   ├── Hotspot.tsx           # Reusable hotspot component
│   │   └── index.ts
│   │
│   ├── overlays/
│   │   ├── VaultOverlay.tsx      # Example overlay
│   │   ├── TerminalOverlay.tsx   # Example overlay
│   │   ├── OverlayContainer.tsx  # Overlay wrapper
│   │   └── index.ts
│   │
│   └── ui/                       # Shared UI components
│       ├── Button.tsx
│       ├── Input.tsx
│       ├── Card.tsx
│       └── index.ts
│
├── hooks/
│   ├── useOverlay.ts             # Overlay state management
│   ├── useData.ts                # Data fetching hook
│   └── index.ts
│
├── state/
│   ├── store.ts                  # Global state (Zustand/Redux)
│   └── types.ts                  # State type definitions
│
├── services/
│   ├── api.ts                    # API client
│   ├── contracts.ts              # Web3 contract interactions
│   └── index.ts
│
├── types/
│   ├── index.ts                  # Global type definitions
│   ├── objects.ts                # Object type definitions
│   └── overlays.ts               # Overlay type definitions
│
├── constants/
│   ├── environment.ts            # Environment configuration
│   ├── objects.ts                # Object definitions
│   └── index.ts
│
├── styles/
│   ├── globals.css               # Global styles
│   ├── environment.css           # Environment-specific styles
│   └── index.ts
│
└── utils/
    ├── positioning.ts            # Position calculation helpers
    └── index.ts
```

---

## Architecture Mapping

### SEI Layer → Code Location

| SEI Layer | Directory | Key Files |
|-----------|-----------|-----------|
| Environment | `components/environment/` | Environment.tsx, Background.tsx |
| Objects | `components/objects/` | [Object].tsx files |
| Hotspots | `components/hotspots/` | Hotspot.tsx |
| Overlays | `components/overlays/` | [Overlay].tsx files |
| Truth Layer | `services/` | api.ts, contracts.ts |
| State | `state/`, `hooks/` | store.ts, useOverlay.ts |

---

## Component Details

### Environment Component

**File:** `components/environment/Environment.tsx`

**Purpose:** Container for the entire spatial environment.

**Structure:**
```tsx
// Environment.tsx
import { Background } from './Background';
import { Vault, Terminal, Board } from '../objects';
import { Hotspot } from '../hotspots';
import { useOverlay } from '../../hooks';

export function Environment() {
  const { openOverlay } = useOverlay();

  return (
    <div className="environment">
      <Background />
      
      {/* PROFILE Zone */}
      <UserProfile />
      
      {/* CORE Zone */}
      <CentralHub />
      
      {/* ACTION Zone */}
      <div className="action-zone">
        <Vault />
        <Hotspot 
          objectId="vault"
          onClick={() => openOverlay('vault')}
        />
        
        <Terminal />
        <Hotspot 
          objectId="terminal"
          onClick={() => openOverlay('terminal')}
        />
      </div>
      
      {/* TOOLS Zone */}
      <SettingsConsole />
      
      {/* PROGRESSION Zone */}
      <StatsBoard />
    </div>
  );
}
```

---

### Object Components

**File:** `components/objects/Vault.tsx`

**Purpose:** Visual representation of a system capability.

**Structure:**
```tsx
// Vault.tsx
export function Vault() {
  return (
    <div className="object vault">
      {/* Visual representation */}
      <svg className="vault-visual">
        {/* SVG or image */}
      </svg>
      
      {/* Optional label */}
      <span className="object-label">Vault</span>
    </div>
  );
}
```

**Guidelines:**
- Objects are purely visual
- No click handlers (handled by hotspots)
- No state management
- Receive props for visual state (active, completed, etc.)

---

### Hotspot Component

**File:** `components/hotspots/Hotspot.tsx`

**Purpose:** Invisible interaction layer over objects.

**Structure:**
```tsx
// Hotspot.tsx
interface HotspotProps {
  objectId: string;
  onClick: () => void;
  position?: { x: number; y: number };
  size?: { width: number; height: number };
}

export function Hotspot({ 
  objectId, 
  onClick, 
  position, 
  size 
}: HotspotProps) {
  return (
    <button
      className="hotspot"
      onClick={onClick}
      style={{
        position: 'absolute',
        left: position?.x,
        top: position?.y,
        width: size?.width,
        height: size?.height,
      }}
      aria-label={`Open ${objectId}`}
    />
  );
}
```

**Guidelines:**
- Use `<button>` for accessibility
- Absolute positioning
- Invisible by default, visible on hover
- Large enough touch targets (min 44px)

---

### Overlay Components

**File:** `components/overlays/VaultOverlay.tsx`

**Purpose:** Modal interface containing functionality.

**Structure:**
```tsx
// VaultOverlay.tsx
import { useData } from '../../hooks';
import { Button, Card } from '../ui';

export function VaultOverlay() {
  const { data, isLoading, error } = useData('vault');
  
  if (isLoading) return <LoadingState />;
  if (error) return <ErrorState error={error} />;
  
  return (
    <div className="overlay-content">
      <header className="overlay-header">
        <h2>Vault</h2>
        <CloseButton />
      </header>
      
      <div className="overlay-body">
        <Card>
          <div className="balance-display">
            <span className="label">Balance</span>
            <span className="value">{data.balance}</span>
          </div>
        </Card>
        
        <DepositForm />
      </div>
      
      <footer className="overlay-footer">
        <Button variant="secondary">Withdraw</Button>
        <Button variant="primary">Deposit</Button>
      </footer>
    </div>
  );
}
```

---

### Overlay Container

**File:** `components/overlays/OverlayContainer.tsx`

**Purpose:** Wrapper for all overlays with common behavior.

**Structure:**
```tsx
// OverlayContainer.tsx
import { useOverlay } from '../../hooks';
import { VaultOverlay, TerminalOverlay } from './';

const overlays = {
  vault: VaultOverlay,
  terminal: TerminalOverlay,
};

export function OverlayContainer() {
  const { activeOverlay, closeOverlay } = useOverlay();
  
  if (!activeOverlay) return null;
  
  const OverlayComponent = overlays[activeOverlay];
  
  return (
    <div 
      className="overlay-backdrop"
      onClick={closeOverlay}
    >
      <div 
        className="overlay-container"
        onClick={(e) => e.stopPropagation()}
      >
        <OverlayComponent />
      </div>
    </div>
  );
}
```

---

## State Management

### Overlay State

**File:** `state/store.ts`

**Structure:**
```typescript
// store.ts
import { create } from 'zustand';

interface OverlayState {
  activeOverlay: string | null;
  overlayData: any;
  isLoading: boolean;
  
  openOverlay: (overlayId: string) => void;
  closeOverlay: () => void;
  setOverlayData: (data: any) => void;
  setLoading: (loading: boolean) => void;
}

export const useStore = create<OverlayState>((set) => ({
  activeOverlay: null,
  overlayData: null,
  isLoading: false,
  
  openOverlay: (overlayId) => set({ 
    activeOverlay: overlayId,
    overlayData: null,
    isLoading: true 
  }),
  
  closeOverlay: () => set({ 
    activeOverlay: null,
    overlayData: null 
  }),
  
  setOverlayData: (data) => set({ 
    overlayData: data,
    isLoading: false 
  }),
  
  setLoading: (loading) => set({ isLoading: loading }),
}));
```

---

### Custom Hooks

**File:** `hooks/useOverlay.ts`

**Structure:**
```typescript
// useOverlay.ts
import { useStore } from '../state/store';

export function useOverlay() {
  const { 
    activeOverlay, 
    openOverlay, 
    closeOverlay 
  } = useStore();
  
  return {
    activeOverlay,
    isOpen: !!activeOverlay,
    openOverlay,
    closeOverlay,
  };
}
```

**File:** `hooks/useData.ts`

**Structure:**
```typescript
// useData.ts
import { useQuery } from '@tanstack/react-query';
import { api } from '../services/api';

export function useData(endpoint: string) {
  const { data, isLoading, error } = useQuery({
    queryKey: [endpoint],
    queryFn: () => api.get(endpoint),
  });
  
  return { data, isLoading, error };
}
```

---

## Services

### API Client

**File:** `services/api.ts`

**Structure:**
```typescript
// api.ts
const API_BASE = process.env.REACT_APP_API_URL;

export const api = {
  async get(endpoint: string) {
    const response = await fetch(`${API_BASE}/${endpoint}`);
    if (!response.ok) throw new Error('API Error');
    return response.json();
  },
  
  async post(endpoint: string, data: any) {
    const response = await fetch(`${API_BASE}/${endpoint}`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(data),
    });
    if (!response.ok) throw new Error('API Error');
    return response.json();
  },
};
```

---

## Constants

### Object Definitions

**File:** `constants/objects.ts`

**Structure:**
```typescript
// objects.ts
export const OBJECTS = {
  vault: {
    id: 'vault',
    name: 'Vault',
    zone: 'ACTION',
    overlay: 'vault',
    position: { x: '20%', y: '35%' },
    size: { width: '15%', height: '20%' },
  },
  terminal: {
    id: 'terminal',
    name: 'Terminal',
    zone: 'ACTION',
    overlay: 'terminal',
    position: { x: '50%', y: '30%' },
    size: { width: '12%', height: '15%' },
  },
} as const;
```

---

## Styles

### CSS Structure

**File:** `styles/globals.css`

**Structure:**
```css
/* globals.css */

/* Environment */
.environment {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

/* Objects */
.object {
  position: absolute;
}

/* Hotspots */
.hotspot {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  background: transparent;
  border: none;
  padding: 0;
}

.hotspot:hover {
  opacity: 0.3;
  background: rgba(255, 255, 255, 0.2);
}

/* Overlays */
.overlay-backdrop {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 100;
}

.overlay-container {
  background: var(--overlay-bg);
  border-radius: 16px;
  padding: 24px;
  max-width: 500px;
  width: 90%;
}
```

---

## Getting Started

### Step 1: Set Up Project

```bash
# Create new project
npx create-react-app my-sei-app --template typescript
# or
npm create vite@latest my-sei-app -- --template react-ts

# Install dependencies
npm install zustand @tanstack/react-query
npm install -D tailwindcss
```

### Step 2: Create Directory Structure

```bash
mkdir -p src/components/{environment,objects,hotspots,overlays,ui}
mkdir -p src/{hooks,state,services,types,constants,styles,utils}
```

### Step 3: Define Your Environment

1. Choose a spatial pattern from `spatial-patterns.md`
2. Define objects in `constants/objects.ts`
3. Create object components in `components/objects/`
4. Position hotspots in `components/environment/Environment.tsx`

### Step 4: Create Overlays

1. Create overlay components in `components/overlays/`
2. Add to `OverlayContainer.tsx` overlay registry
3. Connect to data sources in `services/`

### Step 5: Wire Everything Together

```tsx
// App.tsx
import { Environment } from './components/environment';
import { OverlayContainer } from './components/overlays';
import { QueryClient, QueryClientProvider } from '@tanstack/react-query';

const queryClient = new QueryClient();

function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <Environment />
      <OverlayContainer />
    </QueryClientProvider>
  );
}
```

---

## Validation Checklist

Before deploying, verify:

- [ ] No navigation components exist
- [ ] Single-page application
- [ ] All objects have hotspots
- [ ] All hotspots open overlays
- [ ] All overlays can be closed
- [ ] Environment visible behind overlays
- [ ] Data comes from real sources
- [ ] Responsive on mobile
- [ ] Keyboard accessible

---

## Dependencies

### Required

| Package | Purpose |
|---------|---------|
| React/Vue/Svelte | UI framework |
| Zustand/Redux | State management |
| @tanstack/react-query | Data fetching |

### Optional

| Package | Purpose |
|---------|---------|
| Framer Motion | Animations |
| Tailwind CSS | Styling |
| ethers/web3 | Web3 integration |

---

> **Template Version:** SEI v1.0
