# Recommended Performance & Optimization Patterns

**Keeping Px dApps Fast, Lightweight, and Scalable**

*Part of the Pixel Journey Standards Codex*

---

## Why This Matters

Even though we prioritize client-side architecture and existing primitives, performance still matters significantly for user experience — especially on mobile, in Chrome extensions, and for data-heavy features like leaderboards, analytics, and asset browsing.

This document provides practical patterns for keeping Px work fast and efficient while staying aligned with our core principles.

---

## Core Principles

1. **Minimize unnecessary work** — Especially on initial load and frequent interactions.
2. **Leverage caching aggressively** — Both at the TanStack Query level and locally.
3. **Be thoughtful with data fetching** — Use pagination, cursors, and selective queries.
4. **Keep bundles small** — Especially important for Chrome extensions and PWAs.
5. **Optimize for perceived performance** — Fast feedback loops matter as much as raw speed.

---

## Recommended Patterns

### 1. Aggressive but Smart Caching

- Use TanStack Query’s `staleTime` and `cacheTime` appropriately (longer for relatively static data like templates, shorter for dynamic leaderboards).
- Implement local persistence (IndexedDB) for large datasets that don’t change often.
- Cache block headers and common asset metadata with reasonable TTLs.

### 2. Efficient Data Fetching

- Always prefer cursor-based pagination over deep `page` queries when working with large collections (AtomicAssets, etc.).
- Use `limit` and selective field queries where the API supports it.
- Batch requests when possible.
- Consider background prefetching for likely next actions.

### 3. Optimistic UI + Smart Invalidation

- Use optimistic updates after successful WharfKit transactions when safe.
- Invalidate only the minimal necessary queries after mutations.
- Combine TanStack Query with Zustand for derived UI state to reduce re-renders.

### 4. Bundle & Runtime Optimization

- Use code splitting and lazy loading for non-critical routes/features.
- Tree-shake aggressively.
- Be mindful of large dependencies in Chrome extensions and PWAs.
- Consider lighter alternatives for very constrained environments when appropriate.

### 5. Perceived Performance

- Always show immediate feedback on user actions (even if the real result comes later).
- Use skeleton loaders and progressive loading for data-heavy views.
- Prioritize above-the-fold content.

---

## Checklist

- [ ] Caching strategy is intentional and documented
- [ ] Data fetching uses efficient pagination and selective queries
- [ ] Optimistic updates are used where they meaningfully improve UX
- [ ] Bundle size and runtime performance have been considered
- [ ] Loading states feel fast and responsive

---

*These patterns help Px experiences feel fast and polished while staying lightweight and aligned with our client-side principles.*

**Px Standards — Performance & Optimization Patterns**