# Px Standards Glossary

**Key Terms and Concepts Used Across the Pixel Journey Standards Codex**

*Part of the Pixel Journey Standards Codex*

---

## Core Concepts

**Existing Public Primitives First**  
The current strategic stance (2026 wave) of building excellent UI/UX and client-side systems on top of battle-tested public WAX/Antelope infrastructure (AtomicAssets, Alcor AMM, Hyperion, eosio.msig, etc.) rather than introducing custom smart contracts.

**On-Chain Entropy**  
Deriving deterministic, provably fair randomness from public transaction hashes combined with recent block headers. Used for verifiable game mechanics without custom contracts or oracles.

**Client-Side State & Local-First**  
The principle of keeping state either on-chain (via public indexers like Hyperion) or in encrypted local browser storage, rather than relying on custom centralized backends.

**ZERO CUSTOM CONTRACT OVERHEAD (Historical)**  
The earlier, stricter version of the primitives-first philosophy. Now evolved into the more nuanced “Existing Public Primitives First (Current Era)” approach.

**Surviving Mint Rank**  
Within a template, re-ranking surviving (non-burned) assets by their original `template_mint` number. Rank 1 = the lowest original mint still alive.

**Weighted Rarity Score**  
A composite rarity score that combines statistical rarity with business rules (template supply weight, mint number bonuses, rarity name multipliers, variation multipliers).

---

## Technical Terms

**Hyperion**  
The primary public history/indexer API used for querying on-chain data (assets, transfers, actions, blocks) in Px work.

**WharfKit**  
The modern, recommended WAX wallet library (Session Kit, Contract Kit, Account Kit). Used exclusively for wallet interactions.

**TanStack Query**  
React Query library used for server-state management, caching, and data fetching from Hyperion and other APIs.

**Zustand**  
Lightweight state management library used for client-side/UI state.

**AtomicAssets**  
The dominant NFT/asset standard on WAX. Used for all Px PFPs, collectibles, and asset-based mechanics.

**Alcor AMM**  
The main concentrated liquidity automated market maker on WAX. Used for swaps, quotes, and DeFi features.

**Repo Readiness Scorecard**  
The primary quality gate document. Repos/packages target ≥ 85/100 with no critical gaps.

**Every Folder README Rule**  
The requirement that every meaningful folder must have a high-quality, educational README.md.

**Design System**  
`pixel-journey-design-system` — the single source of truth for all visual components, tokens, and retro pixel aesthetic.

**Existing Public Primitives**  
Public WAX/Antelope contracts and services (AtomicAssets, atomicmarket, alcorammswap, eosio.msig, Hyperion, etc.) that Px work builds upon.

---

## Process Terms

**Px Standard**  
Work that scores ≥ 85 on the Repo Readiness Scorecard with no critical (0-point) failures.

**PxPackages**  
The monorepo unification effort for `@pxjourney/*` shared packages.

**Beta Portals**  
Early public dApp experiences built on top of the unified PxPackages.

---

*This glossary will evolve as new terms and concepts are introduced.*

**Px Standards — Glossary**