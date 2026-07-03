# Repo Types & Styling Guidelines

**Clear distinction between community educational blueprints and internal Px development.**

This document protects long-term maintainability and educational value across the Pixel Journey organization.

---

## Two Distinct Repo Categories

### 1. `wax-*` Educational Blueprints (Community / Dev Guides)

**Purpose**: General, high-quality reference implementations and learning resources for the broader WAX developer community.

**Examples**: `wax-generative-art-seed-canvas`, `wax-organic-activity-fingerprinter`, `wax-advanced-drop-mechanics-toolkit`, `wax-alcor-market-cap-bubble-chart`, future community data trackers, etc.

**Key Rules**:

- **Styling**: Use **plain Tailwind CSS only** (via CDN for simplest demos, or minimal PostCSS setup).
  - No Px-prefixed classes or custom design system components.
  - Focus on clarity, accessibility, copy-paste friendliness, and broad educational value.
- **Audience**: WAX builders, educators, AI-assisted developers, and community contributors.
- **Tone in READMEs**: "This is a clean, educational reference implementation demonstrating [pattern] using public WAX primitives."
- **Dependencies**: Keep minimal. Prefer native Web APIs, Canvas, Web Workers, and lightweight libraries.
- **Goal**: Maximum reusability and learning value for anyone in the WAX ecosystem.

**Why Tailwind-only?**
- Global best practice and easiest for new developers to understand.
- Excellent accessibility baseline.
- Prevents premature coupling to internal Px styling before it is fully finalized and polished.

### 2. Px- Internal Projects & PxPortals

**Purpose**: Production code for the Pixel Journey ecosystem (PxWallet, Hot or Not, PxPackages, PxPortals, leaderboards, etc.).

**Key Rules**:

- Use the full **Px design system** and shared component packages once finalized.
- Strict adherence to Px- prefixed classes, design tokens, and component library.
- Higher consistency requirements across all internal surfaces.
- Can (and should) use internal shared packages (`@pxjourney/*`).

**Future Work (Explicitly Deferred)**:

Once the Px UI and styling system is fully finalized and stable, we will create a dedicated small package:

- `px-tailwind-mapper` or `px-styling-system`
- Provides Tailwind config + plugin to map/override classes toward Px aesthetics.
- Acts as a bridge for gradual adoption in community blueprints that want closer visual alignment.
- Documentation on when and how to adopt it.

This keeps `wax-*` educational examples timeless and clean while giving internal Px work the tight alignment it needs.

---

## Decision Matrix

| Dimension              | `wax-*` Educational Blueprints                  | Px- Internal Projects                          |
|------------------------|--------------------------------------------------|------------------------------------------------|
| **Primary Audience**   | Broader WAX community + educators               | Pixel Journey core team & close collaborators  |
| **Styling**            | Plain Tailwind CSS only                         | Full Px design system + shared packages        |
| **Component Usage**    | Vanilla or minimal framework components         | Px component library                           |
| **README Language**    | Educational / reference implementation          | Production internal module                     |
| **When to use Px patterns** | Never (until future mapper exists)           | Always (once ready)                            |
| **Maintenance Priority** | High educational clarity & accessibility      | Consistency across Px ecosystem                |

---

## How to Classify a New Repo

- If the primary goal is **teaching a pattern** or providing a **reusable reference** for the WAX community → `wax-*` + Tailwind only.
- If the primary goal is **shipping production features** inside the Pixel Journey product surface → Px internal standards apply.

When in doubt, default to the `wax-*` educational style for anything published in the public Blueprint Catalog.

---

*This guideline protects both community value and internal velocity.*