# Recommended Hyperion + WharfKit Patterns

**Practical Integration Patterns for PxPackages and Px dApps**

*Part of the Pixel Journey Standards Codex*

---

## Why This Document Exists

Most Px work (PxWallet, Px Hot or Not, PxTicker, beta portals, analytics features) requires reading on-chain data and interacting with user wallets. Hyperion (for history/indexed data) and WharfKit (for wallet sessions and signing) are the two most important libraries we use.

This document provides recommended patterns that balance correctness, performance, developer experience, and alignment with our "Existing Public Primitives First" strategy.

---

## Core Recommendations

### 1. Use Hyperion as Primary Data Source

**Pattern**: Treat Hyperion as the source of truth for historical and indexed on-chain data. Combine it with client-side caching (TanStack Query) and local storage.

**Why**:
- Avoids running our own indexer
- Excellent query capabilities for assets, transfers, actions, and blocks
- Works well with the verifiable entropy patterns we use
- Public, reliable, and actively maintained by the WAX ecosystem

**Implementation Tips**:
- Use cursor-based pagination (`lower_bound` + `sort=asset_id`) for large collections instead of deep `page` queries.
- Implement polite rate limiting and exponential backoff.
- Cache responses with appropriate TTLs using TanStack Query.
- For real-time needs, combine Hyperion with short-polling or WebSocket subscriptions where available.

### 2. Use WharfKit for All Wallet Interactions

**Pattern**: Use `@wharfkit/session`, `ContractKit`, and `AccountKit` exclusively. Never fall back to legacy UAL or direct `eosjs` usage.

**Why**:
- Modern, actively maintained API
- Excellent TypeScript support
- Clean session management
- Good support for Chrome extensions (MV3) and web apps
- Aligns with our security and self-custody standards

**Key Patterns**:
- Create a single shared `SessionKit` instance at the app root
- Use React Context or a Zustand store to expose the current session
- Prefer `transact` with `ContractKit` for typed contract calls
- Handle session expiration and re-authentication gracefully
- For Chrome extensions, properly separate content script and background script responsibilities

### 3. Recommended Data Flow Pattern

```
User Action
   → WharfKit (sign & broadcast)
   → Hyperion (confirm + fetch updated state)
   → TanStack Query (cache + optimistic update)
   → Zustand (local derived state)
   → UI (via Design System components)
```

This flow keeps us aligned with client-side state principles while leveraging public infrastructure.

### 4. Error Handling & Resilience

- Always implement proper loading, error, and empty states
- Use Hyperion fallbacks or multiple public endpoints when possible
- Implement retry logic with exponential backoff for transient failures
- Surface clear, user-friendly error messages (especially for transaction failures)

### 5. Performance Considerations

- Batch requests where the API supports it
- Use `limit` and cursor pagination aggressively for large datasets
- Cache block headers and common asset data locally with reasonable TTLs
- Prefer optimistic UI updates after successful WharfKit transactions

---

## Example: Basic Hyperion + WharfKit Hook Pattern

```ts
// Recommended pattern for PxPackages

import { useQuery } from '@tanstack/react-query';
import { useSession } from '@pxjourney/wallet'; // or your session context

import { getAssets } from '@pxjourney/hyperion'; // wrapper or direct

interface UseUserAssetsOptions {
  owner: string;
  collection?: string;
}

export function useUserAssets({ owner, collection }: UseUserAssetsOptions) {
  const { session } = useSession();

  return useQuery({
    queryKey: ['userAssets', owner, collection],
    queryFn: async () => {
      if (!owner) return [];
      
      const assets = await getAssets({
        owner,
        collection_name: collection,
        limit: 100,
        // cursor-based pagination in real implementation
      });
      
      return assets;
    },
    enabled: !!owner,
    staleTime: 30_000, // 30 seconds
  });
}
```

---

## When to Add Custom Logic vs Use Primitives

- Add custom logic only when it significantly improves UX or developer experience on top of the primitives.
- Never duplicate what Hyperion or WharfKit already do well.
- If you find yourself writing complex workarounds, consider contributing improvements back to the ecosystem or opening a discussion.

---

## Checklist for Hyperion + WharfKit Usage

- [ ] Using WharfKit exclusively for all signing and session management
- [ ] Using Hyperion (or official public indexers) as primary data source
- [ ] Implementing proper caching, pagination, and error handling
- [ ] Following client-side state principles
- [ ] Documenting any custom wrappers or patterns in the relevant README

---

*These patterns are designed to help PxPackages and dApps stay lightweight, maintainable, and aligned with our core principles while delivering excellent developer and user experiences.*

**Px Standards — Hyperion + WharfKit Patterns**