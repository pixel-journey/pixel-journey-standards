# Recommended State Management Patterns

**TanStack Query + Zustand for PxPackages and Px dApps**

*Part of the Pixel Journey Standards Codex*

---

## Why This Document Exists

Most Px work involves fetching data from Hyperion/AtomicAssets, managing user sessions (via WharfKit), and maintaining derived/local UI state. Using consistent, high-quality state management patterns across packages improves maintainability, performance, and developer experience.

We recommend a **hybrid approach**:
- **TanStack Query** for server-state (data from Hyperion, Atomic API, etc.)
- **Zustand** for client-state (UI state, derived state, ephemeral data, session-related state that isn't purely server-driven)

This combination is lightweight, TypeScript-friendly, has excellent devtools, and aligns well with our client-side state principles.

---

## Core Recommendations

### 1. Use TanStack Query for Server State

**Pattern**: All data that originates from Hyperion, AtomicAssets, Alcor, or other external sources should be managed with TanStack Query.

**Why**:
- Excellent caching, background refetching, and stale-while-revalidate behavior
- Great TypeScript support and devtools
- Handles loading, error, and success states cleanly
- Works excellently with cursor-based pagination and infinite queries

**Key Guidelines**:
- Create thin, focused query hooks (e.g. `useUserAssets`, `useCollectionStats`)
- Use meaningful query keys that include all variables affecting the data
- Set appropriate `staleTime` and `cacheTime` based on how fresh the data needs to be
- Implement optimistic updates after successful WharfKit transactions when it improves UX

### 2. Use Zustand for Client State

**Pattern**: Use Zustand for UI state, derived/computed state, ephemeral data, and any state that doesn't come directly from the server.

**Why**:
- Minimal boilerplate compared to Redux or even Jotai in many cases
- Excellent TypeScript + middleware support (persist, devtools)
- Lightweight and tree-shakeable
- Easy to colocate stores with features when using the monorepo structure

**Key Guidelines**:
- Keep stores focused and avoid putting server data in Zustand
- Use middleware thoughtfully (especially `persist` for things that should survive refresh)
- Prefer multiple small stores over one giant store when it improves separation of concerns
- Expose clean hooks from each store

### 3. Recommended Hybrid Pattern

```ts
// Example structure in a PxPackage

// server-state.ts (TanStack Query)
export function useUserAssets(owner: string) {
  return useQuery({
    queryKey: ['userAssets', owner],
    queryFn: () => fetchUserAssets(owner),
    staleTime: 30_000,
  });
}

// client-state.ts (Zustand)
interface UIState {
  selectedAssetId: string | null;
  isModalOpen: boolean;
  setSelectedAsset: (id: string | null) => void;
  setModalOpen: (open: boolean) => void;
}

export const useUIState = create<UIState>()(
  devtools(
    (set) => ({
      selectedAssetId: null,
      isModalOpen: false,
      setSelectedAsset: (id) => set({ selectedAssetId: id }),
      setModalOpen: (open) => set({ isModalOpen: open }),
    })
  )
);
```

### 4. Optimistic Updates & Transactions

After a successful WharfKit transaction:
- Use TanStack Query's `setQueryData` or optimistic update APIs when appropriate
- Invalidate relevant queries so fresh data is fetched
- Consider using Zustand for short-lived "pending" UI states during the transaction

### 5. Persistence

Use Zustand's `persist` middleware only for data that genuinely needs to survive page refresh (e.g. user preferences, last selected filters).

Avoid persisting large amounts of server data — let TanStack Query handle caching.

---

## When to Choose One Over the Other

| Type of State                    | Recommended Tool     | Reason |
|----------------------------------|----------------------|--------|
| Data from Hyperion / Atomic      | TanStack Query       | Server state, caching, background updates |
| UI state, modals, selections     | Zustand              | Lightweight client state |
| Derived/computed values          | Zustand or TanStack Query selectors | Depends on source of truth |
| Form state (complex)             | React Hook Form + Zustand | Better ergonomics for forms |
| Ephemeral game state             | Zustand              | Fast, local, often doesn't need server caching |

---

## Checklist for State Management in Px Work

- [ ] Server data is managed with TanStack Query
- [ ] Client/UI state is managed with Zustand (or minimal React state for very simple cases)
- [ ] Query keys are stable and descriptive
- [ ] Appropriate caching and stale times are configured
- [ ] Optimistic updates are used thoughtfully after transactions
- [ ] Stores are kept focused and well-documented

---

*These patterns help keep PxPackages and dApps maintainable, performant, and aligned with our client-side state principles while providing excellent developer experience.*

**Px Standards — State Management Patterns**