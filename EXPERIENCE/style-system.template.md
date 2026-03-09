# Style System Template

> Template for defining visual style systems that are independent of SEI architecture.

---

## Style System Overview

### Principle

```
Style is a skin. Architecture is the skeleton.
Never let skin change skeleton.
```

### Style Independence

The same SEI architecture can have different styles:

| Style | Theme | Use Case |
|-------|-------|----------|
| Cyberpunk | Neon city | DeFi, gaming |
| Corporate | Modern office | Enterprise, B2B |
| Academic | University campus | Education, research |
| Fantasy | Medieval village | Gaming, entertainment |
| Sci-Fi | Space station | Tech, AI tools |
| Nature | Forest garden | Wellness, sustainability |

---

## Style Definition Template

### 1. Style Identity

```yaml
Style Name: [e.g., "Neon Cyberpunk"]
Style Family: [Cyberpunk / Corporate / Academic / Fantasy / Sci-Fi / Nature]
Mood: [e.g., "High-tech, edgy, futuristic"]
Target Audience: [e.g., "Crypto natives, gamers"]
Use Cases: [DeFi, gaming, analytics]
```

### 2. Color System

#### Primary Palette

| Role | Color Name | Hex | RGB | Usage |
|------|------------|-----|-----|-------|
| Background Primary | [Name] | [#XXXXXX] | [R,G,B] | Main background |
| Background Secondary | [Name] | [#XXXXXX] | [R,G,B] | Secondary areas |
| Primary | [Name] | [#XXXXXX] | [R,G,B] | Main brand color |
| Secondary | [Name] | [#XXXXXX] | [R,G,B] | Secondary accent |
| Accent | [Name] | [#XXXXXX] | [R,G,B] | CTAs, highlights |

#### Semantic Colors

| Role | Color Name | Hex | Usage |
|------|------------|-----|-------|
| Text Primary | [Name] | [#XXXXXX] | Main text |
| Text Secondary | [Name] | [#XXXXXX] | Secondary text |
| Text Muted | [Name] | [#XXXXXX] | Disabled, hints |
| Success | [Name] | [#XXXXXX] | Success states |
| Warning | [Name] | [#XXXXXX] | Warning states |
| Error | [Name] | [#XXXXXX] | Error states |
| Info | [Name] | [#XXXXXX] | Info states |

#### Color Usage Patterns

```
Environment Background: [Color]
Object Base: [Color]
Object Highlight: [Color]
Hotspot Hover: [Color]
Overlay Background: [Color]
Overlay Border: [Color]
```

---

### 3. Typography System

#### Font Families

| Role | Font Family | Fallback |
|------|-------------|----------|
| Display/Headings | [Font] | [Fallback] |
| Body | [Font] | [Fallback] |
| Monospace | [Font] | [Fallback] |

#### Type Scale

| Level | Size | Weight | Line Height | Letter Spacing | Usage |
|-------|------|--------|-------------|----------------|-------|
| H1 | [px] | [w] | [px] | [px] | Page titles |
| H2 | [px] | [w] | [px] | [px] | Section titles |
| H3 | [px] | [w] | [px] | [px] | Subsection |
| Body | [px] | [w] | [px] | [px] | Main text |
| Small | [px] | [w] | [px] | [px] | Captions |
| Label | [px] | [w] | [px] | [px] | UI labels |

#### Typography Patterns

```
Environment Title: [Style]
Object Labels: [Style]
Overlay Titles: [Style]
Data Display: [Style]
Button Text: [Style]
```

---

### 4. Spacing System

#### Base Unit

```yaml
Base Unit: [px] (e.g., 4px or 8px)
Scale: [e.g., 4, 8, 12, 16, 24, 32, 48, 64]
```

#### Spacing Tokens

| Token | Value | Usage |
|-------|-------|-------|
| space-xs | [px] | Tight spacing |
| space-sm | [px] | Small spacing |
| space-md | [px] | Medium spacing |
| space-lg | [px] | Large spacing |
| space-xl | [px] | Extra large spacing |
| space-2xl | [px] | 2x large spacing |

#### Component Spacing

```
Object Padding: [px]
Overlay Padding: [px]
Button Padding: [px]
Card Padding: [px]
Section Gap: [px]
```

---

### 5. Border & Radius System

#### Border Widths

| Token | Value | Usage |
|-------|-------|-------|
| border-thin | [px] | Subtle borders |
| border-regular | [px] | Standard borders |
| border-thick | [px] | Emphasis borders |

#### Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| radius-sm | [px] | Small elements |
| radius-md | [px] | Medium elements |
| radius-lg | [px] | Large elements |
| radius-xl | [px] | Extra large |
| radius-full | [px/%] | Pills, circles |

---

### 6. Shadow System

#### Shadow Tokens

| Token | Value | Usage |
|-------|-------|-------|
| shadow-sm | [value] | Subtle elevation |
| shadow-md | [value] | Standard elevation |
| shadow-lg | [value] | High elevation |
| shadow-xl | [value] | Maximum elevation |
| shadow-glow | [value] | Glow effects |

#### Shadow Usage

```
Object Default: [Shadow]
Object Hover: [Shadow]
Object Active: [Shadow]
Overlay: [Shadow]
Modal: [Shadow]
```

---

### 7. Animation System

#### Duration Tokens

| Token | Value | Usage |
|-------|-------|-------|
| duration-fast | [ms] | Micro-interactions |
| duration-normal | [ms] | Standard transitions |
| duration-slow | [ms] | Emphasis animations |

#### Easing Tokens

| Token | Value | Usage |
|-------|-------|-------|
| ease-default | [value] | Standard easing |
| ease-in | [value] | Entering |
| ease-out | [value] | Exiting |
| ease-bounce | [value] | Playful |
| ease-elastic | [value] | Dramatic |

#### Animation Patterns

```
Hover Transition: [Duration] [Easing]
Overlay Open: [Duration] [Easing]
Overlay Close: [Duration] [Easing]
Object Idle: [Animation]
Success State: [Animation]
```

---

### 8. Component Styles

#### Object Styles

```yaml
Object Base:
  Background: [Color]
  Border: [Width] [Color]
  Border Radius: [Radius]
  Shadow: [Shadow]

Object Hover:
  Background: [Color]
  Border: [Width] [Color]
  Shadow: [Shadow]
  Transform: [e.g., scale(1.02)]

Object Active:
  Background: [Color]
  Transform: [e.g., scale(0.98)]
```

#### Hotspot Styles

```yaml
Hotspot Default:
  Opacity: 0
  Cursor: pointer

Hotspot Hover:
  Opacity: 0.3
  Background: [Color]
  Box Shadow: [Shadow]
```

#### Overlay Styles

```yaml
Overlay Backdrop:
  Background: [Color with opacity]
  Backdrop Filter: [blur/none]

Overlay Container:
  Background: [Color]
  Border: [Width] [Color]
  Border Radius: [Radius]
  Shadow: [Shadow]
  Padding: [Spacing]

Overlay Header:
  Border Bottom: [Width] [Color]
  Padding Bottom: [Spacing]

Overlay Content:
  Padding: [Spacing]

Overlay Footer:
  Border Top: [Width] [Color]
  Padding Top: [Spacing]
```

#### Button Styles

```yaml
Button Primary:
  Background: [Color]
  Color: [Color]
  Border: [Width] [Color]
  Border Radius: [Radius]
  Padding: [Spacing]
  Font: [Typography]

Button Primary Hover:
  Background: [Color]
  Transform: [e.g., translateY(-2px)]

Button Secondary:
  [Define...]

Button Disabled:
  [Define...]
```

#### Form Styles

```yaml
Input:
  Background: [Color]
  Border: [Width] [Color]
  Border Radius: [Radius]
  Padding: [Spacing]
  Font: [Typography]

Input Focus:
  Border: [Width] [Color]
  Box Shadow: [Shadow]

Label:
  Font: [Typography]
  Color: [Color]
  Margin Bottom: [Spacing]

Error Message:
  Font: [Typography]
  Color: [Color]
```

---

### 9. Responsive Styles

#### Breakpoints

| Name | Width | Description |
|------|-------|-------------|
| sm | [px] | Small devices |
| md | [px] | Medium devices |
| lg | [px] | Large devices |
| xl | [px] | Extra large |

#### Responsive Patterns

```
Object Size:
  Desktop: [Size]
  Tablet: [Size]
  Mobile: [Size]

Overlay Width:
  Desktop: [Width]
  Tablet: [Width]
  Mobile: [Width]

Spacing:
  Desktop: [Spacing]
  Tablet: [Spacing]
  Mobile: [Spacing]
```

---

### 10. Asset Guidelines

#### Iconography

```yaml
Icon Style: [e.g., "Line icons", "Filled icons", "Outlined"]
Icon Size: [px]
Icon Color: [Color]
Icon Library: [e.g., "Lucide", "Heroicons", "Custom"]
```

#### Imagery

```yaml
Image Style: [e.g., "Illustration", "3D render", "Photography"]
Color Treatment: [e.g., "Vibrant", "Muted", "Monochrome"]
Preferred Format: [SVG/PNG/WebP]
```

---

## Style System Examples

### Example 1: Cyberpunk Neon

```yaml
Style Name: Neon Cyberpunk
Mood: High-tech, edgy, futuristic

Colors:
  Background Primary: #0a0a0f
  Background Secondary: #12121a
  Primary: #00f0ff
  Secondary: #ff00a0
  Accent: #f0ff00
  Text Primary: #ffffff
  Text Secondary: #a0a0b0

Typography:
  Display: "Orbitron", sans-serif
  Body: "Inter", sans-serif

Effects:
  Glow: 0 0 20px rgba(0, 240, 255, 0.5)
  Scanlines: overlay pattern
```

### Example 2: Corporate Clean

```yaml
Style Name: Corporate Modern
Mood: Professional, trustworthy, efficient

Colors:
  Background Primary: #ffffff
  Background Secondary: #f5f7fa
  Primary: #0066cc
  Secondary: #4a90d9
  Accent: #00c853
  Text Primary: #1a1a2e
  Text Secondary: #6b7280

Typography:
  Display: "Inter", sans-serif
  Body: "Inter", sans-serif

Effects:
  Shadows: Subtle, professional
  Rounded: Medium radius (8-12px)
```

### Example 3: Academic Traditional

```yaml
Style Name: Academic Classic
Mood: Scholarly, established, intellectual

Colors:
  Background Primary: #faf8f5
  Background Secondary: #f0ece5
  Primary: #8b4513
  Secondary: #d4a574
  Accent: #2e5c4f
  Text Primary: #2c241b
  Text Secondary: #6b5d4d

Typography:
  Display: "Merriweather", serif
  Body: "Source Sans Pro", sans-serif

Effects:
  Textures: Subtle paper grain
  Borders: Classic, thin lines
```

---

## Style Application Checklist

- [ ] Color palette defined
- [ ] Typography system defined
- [ ] Spacing system defined
- [ ] Border/radius system defined
- [ ] Shadow system defined
- [ ] Animation system defined
- [ ] Component styles defined
- [ ] Responsive styles defined
- [ ] Asset guidelines defined
- [ ] Style doesn't break SEI architecture

---

> **Template Version:** SEI v1.0
