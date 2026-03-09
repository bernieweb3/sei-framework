# AI Builder Rules for SEI

> Strict constraints and guidelines for AI builders (Lovable, Bolt, v0, Cursor, Claude Code) when generating Spatial Experience Interfaces.

---

## Absolute Constraints

### ❌ FORBIDDEN Elements

The following are **NEVER ALLOWED** in an SEI implementation:

| Element | Why Forbidden | What To Do Instead |
|---------|---------------|-------------------|
| Navigation menus | Breaks spatial paradigm | Use objects in environment |
| Top nav bars | Breaks spatial paradigm | Use PROFILE zone |
| Sidebar navigation | Breaks spatial paradigm | Use TOOLS zone |
| Breadcrumb trails | Implies page hierarchy | Stay in single environment |
| Tab navigation | Breaks spatial paradigm | Use separate objects |
| Hamburger menus | Hidden navigation | All functions visible as objects |
| Footer navigation | Traditional web pattern | Use PROGRESSION zone |
| Page routing | Multiple pages break spatial context | Single page with overlays |
| URL-based navigation | Routing is forbidden | State-based overlay management |
| Scroll-based sections | Implies page structure | Fixed viewport environment |

### ✅ REQUIRED Elements

The following **MUST BE PRESENT** in every SEI implementation:

| Element | Purpose | Implementation |
|---------|---------|----------------|
| Single environment | Spatial context | One main visual scene |
| Interactive objects | Function access | 5-8 clickable objects |
| Hotspots | Interaction layer | Invisible areas over objects |
| Overlays | Functionality container | Modal interfaces |
| Close mechanism | Return to environment | X button, click outside, Escape |
| Environment persistence | Context maintenance | Visible behind overlays |

---

## Architecture Rules

### Rule 1: Single Page Only

```
❌ Multiple page files (index, about, contact, etc.)
❌ Router configuration
❌ Route definitions

✅ One main App/Index component
✅ State-based overlay management
✅ Conditional rendering for overlays
```

**Enforcement:**
- Check for router imports (react-router, vue-router, etc.)
- Check for multiple page components
- Check for route configurations

---

### Rule 2: No Navigation Components

```
❌ <Nav />
❌ <Navbar />
❌ <Navigation />
❌ <Menu />
❌ <Sidebar />
❌ <Breadcrumb />
❌ <Tabs /> (as navigation)

✅ Objects rendered directly in environment
✅ Hotspots positioned over objects
✅ Overlays for functionality
```

**Enforcement:**
- Search for navigation-related component names
- Verify no menu structures exist
- Check for link lists

---

### Rule 3: Object-Based Interaction

```
❌ Buttons that navigate
❌ Links to other pages
❌ Menu items

✅ Visual objects (buildings, machines, terminals)
✅ Hotspots over objects
✅ Click object → open overlay
```

**Enforcement:**
- Every interactive element must be a visual object
- Objects must have visual representation
- Objects must map to overlays

---

### Rule 4: Overlay-Only Functionality

```
❌ Inline forms in environment
❌ Expandable sections in environment
❌ Dropdown menus

✅ All forms in overlays
✅ All actions in overlays
✅ All data display in overlays
```

**Enforcement:**
- Environment contains only visual context
- All functionality happens in overlays
- Overlays are modal

---

### Rule 5: Environment Persistence

```
❌ Environment hidden during overlay
❌ Full-screen overlays
❌ Page transitions

✅ Environment visible behind overlay
✅ Overlay as modal panel
✅ Dim/blur effect on environment
```

**Enforcement:**
- Environment must remain in DOM
- CSS must keep environment visible
- Overlay z-index above environment

---

## Code Structure Rules

### Component Hierarchy

```
App
└── Environment
    ├── Background
    ├── Objects
    │   ├── Object1
    │   ├── Object2
    │   └── ...
    ├── Hotspots
    │   ├── Hotspot1 (over Object1)
    │   ├── Hotspot2 (over Object2)
    │   └── ...
    └── Overlays (conditional)
        ├── Overlay1
        ├── Overlay2
        └── ...
```

### State Management

```typescript
// Required state structure
interface SEIState {
  activeOverlay: string | null;  // Which overlay is open
  overlayData: any;              // Data for active overlay
  isLoading: boolean;            // Loading state
  environmentState: any;         // Environment state
}

// Required actions
interface SEIActions {
  openOverlay: (overlayId: string) => void;
  closeOverlay: () => void;
  setOverlayData: (data: any) => void;
}
```

### File Structure

```
/src
  ├── components/
  │   ├── Environment/           # Main environment
  │   │   ├── index.tsx
  │   │   ├── Background.tsx
  │   │   └── styles.css
  │   ├── Objects/               # Object components
  │   │   ├── Object1.tsx
  │   │   ├── Object2.tsx
  │   │   └── index.ts
  │   ├── Hotspots/              # Hotspot components
  │   │   ├── Hotspot.tsx
  │   │   └── index.ts
  │   └── Overlays/              # Overlay components
  │       ├── Overlay1.tsx
  │       ├── Overlay2.tsx
  │       └── index.ts
  ├── hooks/
  │   ├── useOverlay.ts
  │   └── useData.ts
  ├── services/
  │   └── api.ts
  └── types/
      └── index.ts
```

---

## Interaction Rules

### Hotspot Interaction

```typescript
// Required hotspot behavior
<Hotspot
  onClick={() => openOverlay('overlay-id')}
  style={{
    position: 'absolute',
    cursor: 'pointer',
    // Invisible by default
    opacity: 0,
    // Subtle hover effect
    ':hover': {
      opacity: 0.3,
      background: 'rgba(255,255,255,0.2)'
    }
  }}
/>
```

### Overlay Behavior

```typescript
// Required overlay behavior
<Overlay
  isOpen={activeOverlay === 'overlay-id'}
  onClose={closeOverlay}
  // Environment visible behind
  backdropStyle={{
    background: 'rgba(0,0,0,0.5)'
  }}
  // Close on click outside
  closeOnBackdropClick={true}
  // Close on Escape
  closeOnEscape={true}
/>
```

---

## Data Rules

### Truth Layer Connection

```
❌ Hardcoded mock data in production
❌ Simulated values
❌ Placeholder data

✅ Real API calls
✅ Real contract interactions
✅ Dynamic data from sources
```

### Data Flow

```
User Action → API Call → Response → Update UI → Close Overlay
```

### Loading States

```typescript
// Required loading handling
const [isLoading, setIsLoading] = useState(false);

const handleAction = async () => {
  setIsLoading(true);
  try {
    const result = await api.call();
    updateUI(result);
  } catch (error) {
    showError(error);
  } finally {
    setIsLoading(false);
  }
};
```

---

## Styling Rules

### Environment Styling

```css
/* Required environment styles */
.environment {
  position: relative;
  width: 100%;
  height: 100vh; /* or fixed height */
  overflow: hidden;
}

/* Objects positioned absolutely */
.object {
  position: absolute;
  /* Position defined in spec */
}

/* Hotspots overlay objects */
.hotspot {
  position: absolute;
  cursor: pointer;
  z-index: 10;
}
```

### Overlay Styling

```css
/* Required overlay styles */
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: center;
}

.overlay-backdrop {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}

.overlay-content {
  position: relative;
  z-index: 101;
  /* Size per spec */
}
```

---

## Validation Rules

### Automated Checks

| Check | Pass Criteria |
|-------|---------------|
| No router imports | No react-router, vue-router, etc. |
| Single page component | One main App component |
| No nav components | No Nav, Navbar, Navigation components |
| Objects exist | At least 5 object components |
| Hotspots exist | Hotspot components for each object |
| Overlays exist | Overlay components defined |
| Close mechanism | closeOverlay function exists |

### Manual Checks

| Check | Pass Criteria |
|-------|---------------|
| Click object → overlay | Each object opens correct overlay |
| Close overlay → environment | Returns to environment |
| Environment visible | Can see environment behind overlay |
| No page transitions | No URL changes, no page reloads |
| Data loads | Real data from sources |
| Responsive | Works on different screen sizes |

---

## Error Prevention

### Common AI Builder Mistakes

| Mistake | Prevention |
|---------|------------|
| Creates navigation menu | Explicitly forbid in prompt |
| Creates multiple pages | Specify "single page" |
| Static objects only | Specify "clickable with hotspots" |
| Missing overlays | Define overlay content for each object |
| Inline functionality | Specify "all in overlays" |
| Full-screen overlays | Specify "environment visible behind" |

### Prompt Additions

Add these to every SEI prompt:

```
CRITICAL RULES:
1. NO navigation menus
2. NO page routing
3. Single page only
4. Objects must be clickable
5. All functionality in overlays
6. Environment visible behind overlays
7. Return to environment after overlay closes
```

---

## Post-Generation Checklist

### Code Review

- [ ] No router imports
- [ ] No navigation components
- [ ] Single main component
- [ ] Objects defined
- [ ] Hotspots defined
- [ ] Overlays defined
- [ ] Close mechanism exists

### Functional Testing

- [ ] All objects clickable
- [ ] Correct overlay opens
- [ ] Overlay closes
- [ ] Returns to environment
- [ ] Data loads
- [ ] Actions work

### Visual Testing

- [ ] Environment renders
- [ ] Objects visible
- [ ] Hotspot hover effects
- [ ] Overlays styled
- [ ] Responsive

---

> **Template Version:** SEI v1.0
