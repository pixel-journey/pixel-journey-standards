# Recommended Patterns for PxPackages (Current Era)

**State Management, Data Fetching, and Hook Design for @pxjourney/* Packages**

*Part of the Pixel Journey Standards Codex — Engineering Pillar*

---

## Context

During the PxPackages unification and beta portal phase, we are building many interconnected packages that deliver UI/UX and client-side logic on top of existing WAX primitives (AtomicAssets, Hyperion, WharfKit, Alcor, etc.).

This document provides recommended patterns that balance:
- Clean separation of concerns
- Excellent developer experience
- Alignment with Existing Public Primitives First
- Compatibility with the Monorepo Rules and Design System

---

## Core Recommended Stack

| Layer                    | Recommended Choice              | Why |
|--------------------------|----------------------------------|-----|
| State Management         | Zustand                          | Minimal boilerplate, excellent DevTools, great with TypeScript |
| Data Fetching / Caching  | TanStack Query (v5)              | Powerful caching, background refetching, optimistic updates, great DX |
| Server Actions / Heavy work | Next.js Server Actions (where applicable) | Offload heavy computation while keeping source of truth client-side or on-chain |
| Wallet / Signing         | @wharfkit/session + ContractKit  | Modern, actively maintained, clean abstractions |
| On-chain Data            | Hyperion + AtomicAssets patterns | Public, reliable, no custom backend needed |

---

## Pattern 1: Package-Level State (Zustand)

Each package should own its state in a focused, exported store.

```ts
// @pxjourney/hot-or-not/src/store/hotOrNotStore.ts
import { create } from 'zustand';

import type { Pairing, LeaderboardEntry } from '../types';

interface HotOrNotState {
  currentPairing: Pairing | null;
  leaderboard: LeaderboardEntry[];
  isLoading: boolean;
  error: string | null;

  setCurrentPairing: (pairing: Pairing) => void;
  fetchLeaderboard: () => Promise<void>;
  // ...
}

export const useHotOrNotStore = create<HotOrNotState>((set, get) => ({
  currentPairing: null,
  leaderboard: [],
  isLoading: false,
  error: null,

  setCurrentPairing: (pairing) => set({ currentPairing: pairing }),

  fetchLeaderboard: async () => {
    set({ isLoading: true });
    try {
      const data = await fetchLeaderboardFromHyperion();
      set({ leaderboard: data, isLoading: false });
    } catch (err) {
      set({ error: err.message, isLoading: false });
    }
  },
}));

// Public hook for consumers
export const useHotOrNot = () => useHotOrNotStore();
```

**Rules**:
- Keep the store focused on one domain.
- Export a clean hook (`useHotOrNot`).
- Do not expose the raw `useHotOrNotStore` directly to consumers outside the package.

---

## Pattern 2: Data Fetching with TanStack Query + Hyperion

Use TanStack Query as the primary data fetching and caching layer.

```ts
// @pxjourney/hot-or-not/src/hooks/useLeaderboard.ts
import { useQuery } from '@tanstack/react-query';
import { fetchLeaderboard } from '../api/hyperion';

export function useLeaderboard() {
  return useQuery({
    queryKey: ['hot-or-not', 'leaderboard'],
    queryFn: fetchLeaderboard,
    staleTime: 1000 * 60 * 2, // 2 minutes
    refetchOnWindowFocus: false,
  });
}
```

**Benefits**:
- Automatic caching and background updates
- Easy optimistic updates for voting / actions
- Consistent loading/error states across the app
- Plays well with WharfKit transaction receipts (invalidate relevant queries after successful TX)

---

## Pattern 3: Composing with WharfKit

```ts
// Example: Performing a verifiable action (e.g. pxhot.pxj transfer)
import { useWharfKit } from '@pxjourney/wallet';

const { session, signTransaction } = useWharfKit();

const handleVote = async (amount: string, memo: string) => {
  const result = await signTransaction({
    action: {
      account: 'token.pxj',
      name: 'transfer',
      data: { from: session.actor, to: '...', quantity: amount, memo },
    },
  });

  // After successful TX, invalidate relevant queries
  queryClient.invalidateQueries({ queryKey: ['hot-or-not', 'leaderboard'] });

  // Optionally derive verifiable seed from result.transaction_id
};
```

---

## Pattern 4: Cross-Package Communication

- Prefer **hooks and context** over direct store access.
- When one package needs data from another, expose it through a clean hook or small SDK surface.
- Example: `@pxjourney/hot-or-not` consumes `@pxjourney/wallet` hooks but does **not** import internal Zustand stores from the wallet package.

---

## Anti-Patterns to Avoid

- Creating a massive global Zustand store that everything imports from
- Direct cross-package imports of internal implementation details
- Bypassing TanStack Query caching for frequently changing on-chain data
- Mixing WharfKit session logic with domain-specific state

These patterns will lower scores on the Repo Readiness Scorecard (Code Quality and Monorepo categories).

---

## Connection to Other Standards

- **Monorepo Rules**: These patterns support clean public APIs and loose coupling between packages.
- **UI/UX Alignment**: Loading, error, and data states should use Design System components.
- **Existing Public Primitives First**: All data ultimately comes from Hyperion, AtomicAssets, or WharfKit — not custom backends.
- **Repo Readiness Scorecard**: Following these patterns improves scores in Code Quality, Maintainability, and Educational Spirit.

---

## Checklist for New PxPackage Features

- [ ] State lives in a focused Zustand store with a clean exported hook
- [ ] Data fetching uses TanStack Query + Hyperion patterns
- [ ] Cross-package communication uses hooks/context, not internal implementation imports
- [ ] Transaction side-effects invalidate relevant queries
- [ ] Loading/error/empty states use Design System components
- [ ] Package README documents the patterns used

---

*These patterns are designed to scale cleanly during the current unification phase while remaining lightweight and educational.*

**Px Standards — Recommended PxPackages Patterns**