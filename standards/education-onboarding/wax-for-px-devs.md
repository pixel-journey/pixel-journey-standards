# WAX & Antelope for Px Developers (Current Era)

**A Focused, Practical Introduction for People Building on Pixel Journey**

*Part of the Pixel Journey Standards Codex — Education & Onboarding Pillar*

---

## Why This Guide Exists

Most general WAX tutorials are either too broad or too focused on smart contract development. As Px developers in the current wave, we primarily build **excellent UI/UX and client-side systems on top of existing public primitives**. We need a focused map of the concepts that actually matter for PxWallet, Px Hot or Not, PxPackages, beta portals, and similar work.

This guide prioritizes the primitives and patterns we use most heavily right now.

---

## Core Concepts You Need to Understand

### 1. AtomicAssets (NFTs, PFPs, Templates, Schemas)

**What it is**: The dominant standard for NFTs and digital assets on WAX. Almost all Px NFT/PFP work uses this.

**Why it matters for Px**:
- All our PFPs, collectibles, and asset-based mechanics go through AtomicAssets.
- Templates define immutable data + max supply.
- `template_mint` is crucial for features like surviving mint rank (see gkniftyheads-tracker patterns).
- We query assets heavily via Hyperion and the Atomic API.

**Key things to learn**:
- Difference between `asset`, `template`, and `schema`
- How to fetch assets efficiently (cursor pagination with `lower_bound` on `asset_id` is preferred over deep `page` queries)
- How burns affect surviving supply and rankings
- Trait exposure calculations (only among surviving assets)

**Relevant standards documents**: `existing-primitives-first.md`, `verifiable-onchain-entropy-patterns.md`

### 2. Hyperion History API

**What it is**: The best public indexer for historical on-chain data on WAX.

**Why it matters for Px**:
- Primary source of truth for most of our data needs (asset history, transfers, burns, transactions)
- Powers verifiable entropy patterns (TX + block data)
- Enables real-time-ish updates without running our own indexer
- Used heavily in Px Hot or Not, leaderboards, and analytics

**Key patterns**:
- Use it for delta syncs (new mints/burns since last timestamp)
- Combine with client-side caching (TanStack Query)
- Be mindful of rate limits and implement polite backoff

**Relevant standards**: `verifiable-onchain-entropy-patterns.md`

### 3. WharfKit (The Modern WAX Wallet Library)

**What it is**: The current recommended library for wallet connections, sessions, signing, and contract interactions on WAX.

**Why it matters for Px**:
- We use it exclusively (never legacy UAL or eosjs)
- Powers PxWallet god-mode features (encrypted vaults, multi-account, auto-sign)
- Session Kit + Contract Kit + Account Kit give us clean abstractions
- Works excellently with Next.js 15 and React

**Key concepts**:
- Sessions vs direct signing
- How to do secure cross-chain key derivation client-side
- Opt-in auto-sign patterns
- Content script isolation in Chrome extensions (MV3)

**Relevant standards**: Monorepo rules, Security patterns in engineering overview

### 4. Verifiable On-Chain Entropy (TX + Block Header Pattern)

**What it is**: Deriving deterministic, provably fair randomness from public transaction hashes and recent block headers — with zero custom contracts or oracles.

**Why it matters for Px**:
- Powers Px Hot or Not verifiable pairing and future game mechanics
- Completely free and trustless
- Excellent educational example of composing existing primitives creatively

**See**: `verifiable-onchain-entropy-patterns.md` for the full pattern and code example.

### 5. Alcor AMM (Swaps, Quotes, Liquidity)

**What it is**: The main concentrated liquidity AMM on WAX.

**Why it matters for Px**:
- Used for any DeFi features (swaps, quotes, routing) in PxTicker or future tools
- We compose on top of it rather than building our own AMM logic

**Key patterns**: Use their SDK or well-structured API calls for quotes and swaps. Keep routing logic client-side where possible.

### 6. Client-Side State + Local-First Architecture

**Why it matters for Px**:
- Aligns with our Core Principle #2 (State Patterns & Client-Side Rendering)
- PxWallet vaults are fully client-side and encrypted
- Most leaderboards, analytics, and game state are computed client-side from Hyperion data + local cache
- Reduces cost, improves performance, increases auditability and self-custody

**Technologies we favor**: TanStack Query + Zustand, Web Crypto API for encryption/derivation, IndexedDB for persistent local state.

---

## How These Concepts Connect in Real Px Work

**Example flow (Px Hot or Not style)**:
1. User performs an action (e.g. `pxhot.pxj` transfer with memo) — handled via WharfKit
2. We capture the TX hash and recent block data via Hyperion
3. We derive verifiable seed client-side using the TX + block header pattern
4. Pairing / matchup logic runs deterministically in the browser
5. Results and leaderboards are computed from surviving assets (AtomicAssets via Hyperion)
6. UI is built exclusively with Design System components

This entire flow uses **existing public primitives** + excellent client-side engineering + Design System visuals.

---

## Recommended Learning Path for New Px Devs / AI Agents

1. Read the Core Principles in the root `README.md`
2. Read `existing-primitives-first.md` (understand the current strategic stance)
3. Read `verifiable-onchain-entropy-patterns.md` (see a concrete powerful pattern in action)
4. Study this WAX for Px Devs guide
5. Read the Monorepo Rules and UI/UX Alignment documents
6. Use the Repo Readiness Scorecard on your first significant piece of work

---

## Further Resources

- Official AtomicAssets docs and Swagger
- Hyperion documentation (onblock.dev has excellent practical guides)
- WharfKit documentation and examples
- The gkniftyheads-tracker repo (outstanding real-world example of many of these patterns at scale)
- Pixel Journey Design System (for all visual work)

---

*This guide will evolve as we add more patterns and as the ecosystem grows. Feedback and contributions are welcome.*

**Px Standards — WAX for Px Developers**