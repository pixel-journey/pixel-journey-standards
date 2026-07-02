# Monorepo & PxPackages Rules (Current Era)

**Guidance for @pxjourney/* Packages, Unification, and Beta Portals**

*Part of the Pixel Journey Standards Codex*  
*This document is especially important during the PxPackages unification and beta portal phase (2026).*

---

## Strategic Context

We are currently in a major unification phase. Multiple packages (`@pxjourney/*`) are being standardized, wired together cleanly, and prepared for beta dApp portals. At the same time, we are deliberately operating under the **Existing Public Primitives First** strategy — meaning most of our value delivery is in excellent UI/UX, client-side state, hooks, and developer tooling layered on top of existing WAX contracts and indexers.

This creates specific requirements for how our monorepo and packages should be structured.

---

## Core Rules

### 1. Clean Public API Surfaces (Non-Negotiable)

Every `@pxjourney/*` package **must** expose a clean, well-documented public API.

- Internal implementation details must **not** be importable from outside the package.
- Use `package.json` `exports` field (or equivalent) to control what is public.
- Consumers should only ever import from the package root or clearly documented subpaths.
- Example good pattern:
  ```ts
  import { usePxHotOrNot } from '@pxjourney/hot-or-not';
  import { createWallet } from '@pxjourney/wallet';
  ```

**Why**: Prevents tight coupling, enables independent evolution of packages, and makes the monorepo maintainable as it grows.

### 2. Zero Individual Styling (Design System Enforcement)

**No package or component may introduce its own Tailwind classes, inline styles, or custom CSS for brand/visual elements.**

- All visual styling, tokens, variants, spacing, typography, colors, glassmorphic/CRT effects, animations, and haptics **must** come from `pixel-journey-design-system`.
- This rule applies even (especially) during rapid development.
- The only exception is temporary prototyping that is never committed.

**Why**: Guarantees pixel-perfect consistency across all Px experiences. Enables global theme changes. Prevents style drift. Makes the Design System the single source of truth.

### 3. Package Interaction Patterns (Current Era)

Because we are building UI/UX layers on top of existing primitives:

- Packages should communicate through **well-typed hooks, context providers, or small SDK surfaces**.
- Avoid direct imports of another package's internal state machines or implementation details.
- Prefer composition over inheritance.
- When two packages need to share logic, extract it into a shared lower-level package (e.g. `@pxjourney/core` or `@pxjourney/utils`) rather than duplicating or tightly coupling.

**Example healthy pattern**:
- `@pxjourney/wallet` exposes session and signing hooks.
- `@pxjourney/hot-or-not` consumes those hooks + uses Hyperion + AtomicAssets patterns.
- They do **not** reach into each other's internal Zustand stores or API clients.

### 4. Unified Build, Test, and Lint Pipeline

- All packages in the monorepo should use the same core tooling (Turborepo / pnpm workspaces recommended).
- Consistent TypeScript config, ESLint rules, and Prettier config across packages.
- Shared scripts for building, type-checking, and testing.
- Changes that affect multiple packages should be coordinated (Changesets or similar for versioning).

### 5. Documentation Discipline

Every package **must** follow the Every Folder README Rule.

In addition:
- The package root README must clearly state:
  - What the package does
  - Its public API surface
  - How it aligns with Existing Public Primitives First
  - Dependencies on other `@pxjourney/*` packages or external primitives
  - Example usage for the most common consumer flows

### 6. Versioning & Release Coordination

- Use semantic versioning.
- Breaking changes to public APIs require major version bumps and clear migration guides.
- Coordinated releases across packages that depend on each other are preferred during the unification phase.
- Changelog entries should mention impact on beta portals and other Px dApps.

---

## Decision Matrix: When to Create a New Package vs Extend Existing One

| Situation                                      | Recommended Approach                          | Rationale |
|------------------------------------------------|-----------------------------------------------|---------|
| New feature area with clear boundaries         | New dedicated package                         | Keeps packages focused and maintainable |
| Small utility or shared hook used in 2+ places | Add to existing shared package (`@pxjourney/utils` or `@pxjourney/core`) | Avoids package explosion |
| UI component or pattern                        | Must live in / be contributed to Design System first | Enforces zero individual styling |
| Complex domain logic tightly coupled to one dApp | Consider co-locating in the dApp repo temporarily | Only promote to shared package when it proves reusable |

---

## How This Supports the Current Wave

These rules help us:
- Move fast on PxPackages unification without creating technical debt
- Deliver consistent, pixel-perfect experiences across beta portals
- Keep packages lightweight and focused on UI/UX + client-side excellence
- Make it easy for future contributors (and AI agents) to understand how everything fits together
- Maintain the ability to evolve packages independently while still composing beautiful experiences

---

## Connection to Other Standards

- **Repo Readiness Scorecard**: Monorepo hygiene, Design System compliance, and documentation directly impact scores in Code Quality, UI/UX, and Documentation categories.
- **Every Folder README Rule**: Mandatory for every package.
- **Existing Public Primitives First**: These structural rules exist to support clean layering on top of public contracts and indexers.

---

## Checklist for Any New or Refactored @pxjourney/* Package

- [ ] Clean public exports with no internal implementation leakage
- [ ] Zero individual styling (all visuals via Design System)
- [ ] High-quality root README following the Every Folder rule
- [ ] Clear documentation of how it uses existing WAX primitives
- [ ] Consistent build/lint/test setup with the rest of the monorepo
- [ ] Self-scored against the Repo Readiness Scorecard before PR

---

*These rules are designed to serve us well during the current unification and beta portal phase while remaining lightweight enough not to slow down delivery.*

**Px Standards — Monorepo & PxPackages Rules**