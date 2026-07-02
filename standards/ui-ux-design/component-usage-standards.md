# Px Component Usage Standards

**How to Properly Use and Compose UI Components in Pixel Journey**

*Part of the Pixel Journey Standards Codex — UI/UX Pillar*

---

## Purpose

This document defines how components should be used, composed, and styled across all Px interfaces. It ensures consistency, quality, and adherence to the Pixel Journey visual language while maximizing the value of the Design System.

All components must come from (or be approved extensions of) the `pixel-journey-design-system`. Individual custom styling is not permitted.

---

## Core Principles for Component Usage

1. **Composition over Creation** — Prefer composing existing components and variants over building new ones.
2. **Semantic & Intentional** — Every component should have a clear purpose and role in the interface.
3. **Consistent Hierarchy** — Visual weight, spacing, and emphasis should follow established patterns.
4. **On-Brand Feel** — Components should reinforce the retro pixel + premium glassmorphic identity.
5. **Accessible by Default** — All components must meet baseline accessibility standards.
6. **Responsive & Adaptive** — Components should work well across desktop, mobile, and extension contexts.

---

## Key Component Categories & Guidelines

### Buttons

- Primary, secondary, tertiary, and destructive variants should be used consistently.
- Pixel fonts or carefully paired type for labels.
- Clear visual feedback on hover, press, loading, and disabled states.
- Icon + text combinations should follow established spacing and alignment rules.
- Avoid mixing too many button styles on one screen.

**Anti-pattern**: Creating custom button styles or using raw `<button>` elements with ad-hoc Tailwind classes.

### Cards & Panels

- Use layered glassmorphic or bordered panels with appropriate depth.
- Consistent padding, border radius (or pixel edge treatment), and shadow/glow usage.
- Cards should have clear visual separation and hierarchy when grouped.
- Asset cards, info cards, and action cards should follow distinct but related patterns.

**Anti-pattern**: Using raw divs with custom borders/shadows instead of Design System Card components.

### Modals, Drawers & Overlays

- Use the approved modal and drawer components.
- Backdrop should feel intentional (subtle blur or dim).
- Header, body, and footer structure should be consistent.
- Escape key and click-outside behavior should be predictable.
- Nested modals should be avoided when possible.

**Anti-pattern**: Building custom overlay systems or using browser `alert()` / `confirm()`.

### Data Displays & Grids

- Asset grids, leaderboards, tables, and lists should use the approved DataGrid or equivalent components.
- Consistent column alignment, sorting indicators, and loading states.
- Rarity, rank, and metadata should be displayed using established visual treatments.
- Responsive behavior (stacking, horizontal scroll, card conversion) should follow defined breakpoints.

**Anti-pattern**: Building custom table or grid layouts from scratch for every feature.

### Forms & Inputs

- Use the Design System form components and validation patterns.
- Clear labeling, helper text, and error messaging.
- Consistent focus states and keyboard navigation.
- Loading and submission states should be handled gracefully.
- Group related inputs logically with appropriate spacing.

**Anti-pattern**: Mixing raw HTML inputs with Design System components or creating custom form styling.

### Navigation & Tabs

- Use approved navigation, tab, and sidebar components.
- Clear active states and visual hierarchy.
- Mobile navigation patterns should follow established responsive behavior.
- Breadcrumbs and contextual navigation should be used where helpful.

**Anti-pattern**: Creating custom navigation bars or tab systems that deviate from the Design System.

### Feedback & Status

- Toasts, banners, alerts, and progress indicators should use approved components.
- Success, warning, error, and info states should follow semantic color and icon usage.
- Empty states should be helpful and on-brand (use illustrations or friendly copy where appropriate).
- Loading states should feel fast and intentional (skeletons preferred over generic spinners when suitable).

**Anti-pattern**: Using generic browser alerts or building one-off feedback UI.

### Game-Like & Interactive Elements

- Voting, staking, claiming, and progression UI should feel rewarding and characterful.
- Use approved interactive components with appropriate micro-interactions and haptics.
- Visual feedback for successful actions should feel celebratory but not excessive.

---

## Composition Guidelines

- Build complex interfaces by composing smaller, approved components rather than creating monolithic custom components.
- Maintain consistent spacing scales and visual rhythm across screens.
- When a new variant or pattern is genuinely needed, propose it through the Design System rather than building it ad-hoc.

---

## Quality Bar

AAA-tier component usage in Px means:
- Every interface feels cohesive and intentional
- Components behave predictably across the ecosystem
- The retro + premium aesthetic is consistently reinforced
- Accessibility and responsiveness are non-negotiable
- Developers and designers spend time on product logic and experience, not reinventing UI primitives

---

## How This Connects to Other Standards

- **Visual Language & Aesthetic Guidelines**: Defines the overall look and feel these components must support.
- **Design System Alignment**: Mandates that all components come from the official system.
- **Motion & Haptics** (future): Will define animation and feedback behavior for these components.
- **Error Handling Patterns**: Defines the behavioral side of feedback components.

---

*This document raises the baseline for UI consistency and quality across all Px work. It should evolve alongside the Design System and real usage patterns.*

**Px Standards — Component Usage Standards**