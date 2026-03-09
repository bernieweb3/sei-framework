# Spatial Patterns

> Reusable spatial interface patterns for common domains.

---

## Pattern Overview

Spatial patterns provide proven environment metaphors for specific domains. Each pattern defines:

- Environment metaphor
- Typical object types
- Zone layout
- Suitable domains

Use these patterns as starting points for your SEI implementation.

---

## Pattern 1: Command Center

### Environment Metaphor

A high-tech control room where operators monitor and manage complex systems.

### Visual Style

- Dark, focused interface
- Glowing screens and indicators
- Isometric or flat perspective
- High contrast for readability

### Zone Layout

```
        [PROFILE]
     [Operator Badge]

[TOOLS]    [CORE]      [ACTIONS]
Settings  Main       Monitoring
Console   Display    Stations
                     Consoles

      [PROGRESSION]
    [Status Board]
```

### Typical Objects

| Object | Function | Zone |
|--------|----------|------|
| Main Display | System overview | CORE |
| Monitoring Station | View metrics | ACTIONS |
| Control Console | Execute commands | ACTIONS |
| Alert Panel | View notifications | ACTIONS |
| Settings Console | Configuration | TOOLS |
| Status Board | View achievements | PROGRESSION |

### Suitable Domains

- AI/ML monitoring
- DevOps dashboards
- Network operations
- Security operations (SOC)
- IoT management
- Server management

### Example Applications

| Application | Objects |
|-------------|---------|
| AI Training Dashboard | Model terminal, Dataset archive, Metrics screen |
| DevOps Monitor | Deployment panel, Log viewer, Alert console |
| Network Monitor | Topology map, Traffic analyzer, Alert system |

---

## Pattern 2: Financial District

### Environment Metaphor

A bustling city district with banks, exchanges, and financial institutions.

### Visual Style

- Modern urban aesthetic
- Glass and steel buildings
- Day or night setting
- Isometric city view

### Zone Layout

```
        [PROFILE]
      [Investor Card]

[TOOLS]    [CORE]      [ACTIONS]
Settings  Central    Bank
Console   Plaza      Exchange
                     Vault

      [PROGRESSION]
    [Portfolio Board]
```

### Typical Objects

| Object | Function | Zone |
|--------|----------|------|
| Central Plaza | Orientation landmark | CORE |
| Bank | Asset management | ACTIONS |
| Exchange | Trading | ACTIONS |
| Vault | Secure storage | ACTIONS |
| Settings Console | Configuration | TOOLS |
| Portfolio Board | View portfolio | PROGRESSION |

### Suitable Domains

- DeFi protocols
- Trading platforms
- Portfolio management
- Banking applications
- Investment tools
- Payment systems

### Example Applications

| Application | Objects |
|-------------|---------|
| DeFi Yield Farm | Vault, Pool, Rewards chest, Analytics tower |
| Trading Platform | Exchange building, Order book, Chart station |
| Portfolio Tracker | Asset vault, Performance board, News terminal |

---

## Pattern 3: Research Laboratory

### Environment Metaphor

A scientific facility where researchers conduct experiments and analyze data.

### Visual Style

- Clean, clinical aesthetic
- White and blue tones
- Equipment and instruments
- Organized workspace

### Zone Layout

```
        [PROFILE]
      [Researcher ID]

[TOOLS]    [CORE]      [ACTIONS]
Equipment  Central    Experiment
Storage    Atrium     Stations
                      Lab Benches

      [PROGRESSION]
    [Publications Wall]
```

### Typical Objects

| Object | Function | Zone |
|--------|----------|------|
| Central Atrium | Main gathering space | CORE |
| Experiment Station | Run experiments | ACTIONS |
| Lab Bench | Analyze samples | ACTIONS |
| Data Terminal | View results | ACTIONS |
| Equipment Storage | Manage resources | TOOLS |
| Publications Wall | View achievements | PROGRESSION |

### Suitable Domains

- Scientific research
- Data analysis platforms
- Educational labs
- Quality control systems
- Medical research
- Academic platforms

### Example Applications

| Application | Objects |
|-------------|---------|
| Data Science Platform | Dataset library, Model workshop, Results board |
| Educational Lab | Lesson terminal, Exercise bench, Progress display |
| Research Manager | Project table, Publication archive, Collaboration space |

---

## Pattern 4: Campus

### Environment Metaphor

A university or school campus with buildings for different activities.

### Visual Style

- Warm, welcoming atmosphere
- Green spaces and pathways
- Traditional or modern architecture
- Daytime setting

### Zone Layout

```
        [PROFILE]
       [Student Card]

[TOOLS]    [CORE]      [ACTIONS]
Settings  Central    Lecture Hall
Office    Quad       Library
                     Lab Building

      [PROGRESSION]
    [Achievement Hall]
```

### Typical Objects

| Object | Function | Zone |
|--------|----------|------|
| Central Quad | Main gathering area | CORE |
| Lecture Hall | Access lessons | ACTIONS |
| Library | Browse resources | ACTIONS |
| Lab Building | Complete exercises | ACTIONS |
| Settings Office | Configuration | TOOLS |
| Achievement Hall | View progress | PROGRESSION |

### Suitable Domains

- E-learning platforms
- Training systems
- Course management
- Skill development
- Certification programs
- Onboarding systems

### Example Applications

| Application | Objects |
|-------------|---------|
| Online Course Platform | Classroom, Resource library, Practice lab |
| Corporate Training | Training center, Assessment room, Certificate hall |
| Language Learning | Lesson building, Dictionary, Exercise garden |

---

## Pattern 5: Observatory

### Environment Metaphor

A facility for observing, analyzing, and understanding complex phenomena.

### Visual Style

- Dark, cosmic aesthetic
- Starfield or data visualization background
- Telescopes and instruments
- Mysterious, exploratory feel

### Zone Layout

```
        [PROFILE]
      [Observer Badge]

[TOOLS]    [CORE]      [ACTIONS]
Settings  Central    Telescope
Console   Dome       Analysis
                     Station

      [PROGRESSION]
    [Discovery Log]
```

### Typical Objects

| Object | Function | Zone |
|--------|----------|------|
| Central Dome | Main observation area | CORE |
| Telescope | Explore data | ACTIONS |
| Analysis Station | Process findings | ACTIONS |
| Data Archive | Store discoveries | ACTIONS |
| Settings Console | Configuration | TOOLS |
| Discovery Log | View achievements | PROGRESSION |

### Suitable Domains

- Analytics platforms
- Business intelligence
- Data visualization
- Research tools
- Monitoring systems
- Discovery platforms

### Example Applications

| Application | Objects |
|-------------|---------|
| Analytics Dashboard | Chart telescope, Query console, Report archive |
| Business Intelligence | Metrics observatory, Insight analyzer, Data vault |
| Research Platform | Search telescope, Analysis desk, Finding library |

---

## Pattern 6: Workshop

### Environment Metaphor

A craftsman's workspace where things are built, repaired, and improved.

### Visual Style

- Industrial, hands-on aesthetic
- Tools and workbenches
- Warm lighting
- Organized chaos

### Zone Layout

```
        [PROFILE]
      [Craftsman Badge]

[TOOLS]    [CORE]      [ACTIONS]
Tool Rack  Central    Workbench
Storage    Workshop   Forge
                      Assembly

      [PROGRESSION]
    [Masterpiece Wall]
```

### Typical Objects

| Object | Function | Zone |
|--------|----------|------|
| Central Workshop | Main workspace | CORE |
| Workbench | Build/create | ACTIONS |
| Forge | Process/transform | ACTIONS |
| Assembly Station | Combine components | ACTIONS |
| Tool Rack | Manage tools | TOOLS |
| Masterpiece Wall | View achievements | PROGRESSION |

### Suitable Domains

- Creator tools
- Builder platforms
- Workflow automation
- Content creation
- Product development
- Manufacturing systems

### Example Applications

| Application | Objects |
|-------------|---------|
| No-Code Builder | Component workbench, Logic forge, Preview station |
| Content Creator | Editor bench, Asset library, Publish portal |
| Workflow Tool | Automation workbench, Integration forge, Monitor display |

---

## Pattern 7: Garden

### Environment Metaphor

A cultivated space where things grow and flourish over time.

### Visual Style

- Natural, organic aesthetic
- Green spaces and pathways
- Growth and life themes
- Peaceful atmosphere

### Zone Layout

```
        [PROFILE]
      [Gardener Profile]

[TOOLS]    [CORE]      [ACTIONS]
Seed       Central    Greenhouse
Storage    Garden     Harvest
                      Station

      [PROGRESSION]
    [Growth Tracker]
```

### Typical Objects

| Object | Function | Zone |
|--------|----------|------|
| Central Garden | Main growing area | CORE |
| Greenhouse | Nurture growth | ACTIONS |
| Harvest Station | Collect yield | ACTIONS |
| Seed Vault | Manage resources | ACTIONS |
| Tool Shed | Configuration | TOOLS |
| Growth Tracker | View progress | PROGRESSION |

### Suitable Domains

- Investment growth
- Skill development
- Community building
- Wellness tracking
- Sustainability apps
- Long-term goals

### Example Applications

| Application | Objects |
|-------------|---------|
| Investment App | Portfolio greenhouse, Dividend harvest, Asset vault |
| Habit Tracker | Habit garden, Streak harvest, Goal tracker |
| Community Platform | Community garden, Engagement harvest, Member nursery |

---

## Pattern 8: Archive

### Environment Metaphor

A vast repository of knowledge and records, organized for discovery.

### Visual Style

- Ancient or modern library aesthetic
- Shelves, scrolls, or digital displays
- Organized, searchable
- Knowledge-focused

### Zone Layout

```
        [PROFILE]
      [Researcher Card]

[TOOLS]    [CORE]      [ACTIONS]
Catalog    Central    Reading
System     Hall       Room
                      Study Desk

      [PROGRESSION]
    [Knowledge Tree]
```

### Typical Objects

| Object | Function | Zone |
|--------|----------|------|
| Central Hall | Main browsing area | CORE |
| Reading Room | Access content | ACTIONS |
| Study Desk | Deep analysis | ACTIONS |
| Catalog System | Search and filter | TOOLS |
| Bookmark Shelf | Saved items | TOOLS |
| Knowledge Tree | Learning progress | PROGRESSION |

### Suitable Domains

- Knowledge bases
- Documentation systems
- Research platforms
- Content libraries
- Learning management
- Information portals

### Example Applications

| Application | Objects |
|-------------|---------|
| Documentation Site | Doc library, Search terminal, Bookmark shelf |
| Research Database | Paper archive, Citation desk, Reading list |
| Wiki Platform | Article hall, Edit desk, Contribution tracker |

---

## Pattern Selection Guide

### Choose Based on Domain

| Domain | Recommended Pattern |
|--------|---------------------|
| Finance/DeFi | Financial District |
| AI/ML/Data | Command Center or Observatory |
| Education | Campus |
| Research | Research Laboratory |
| Analytics | Observatory |
| Creation/Building | Workshop |
| Growth/Investment | Garden |
| Knowledge/Content | Archive |

### Choose Based on User Goal

| User Goal | Recommended Pattern |
|-----------|---------------------|
| Monitor systems | Command Center |
| Execute transactions | Financial District |
| Learn skills | Campus |
| Conduct experiments | Research Laboratory |
| Analyze data | Observatory |
| Build/create | Workshop |
| Track progress | Garden |
| Discover knowledge | Archive |

---

## Combining Patterns

Some applications may combine elements from multiple patterns:

| Application | Primary Pattern | Secondary Elements |
|-------------|-----------------|-------------------|
| DeFi Learning Platform | Campus | Financial District objects |
| Research Dashboard | Observatory | Research Laboratory objects |
| Creator Community | Workshop | Garden progress tracking |

---

## Customizing Patterns

Patterns are starting points, not rigid templates:

1. **Keep the zone structure** — Five zones are universal
2. **Adapt objects to your domain** — Use domain-appropriate metaphors
3. **Maintain affordances** — Objects should imply function
4. **Preserve the flow** — Environment → Object → Overlay → Action

---

## Pattern Checklist

When applying a pattern, verify:

- [ ] Environment metaphor fits the domain
- [ ] Objects represent real system capabilities
- [ ] Zone layout follows the five-zone structure
- [ ] Object count is 5-8
- [ ] Each object maps to one overlay
- [ ] Visual style supports the metaphor
- [ ] User can guess object functions without labels

---

> **Template Version:** SEI v1.0
