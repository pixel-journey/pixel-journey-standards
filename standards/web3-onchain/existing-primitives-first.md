# Existing Public Primitives First — Current Era Strategy (2026 Px Portal Wave)

**Part of the Pixel Journey Standards Codex**  
*Strategic guidance for the massive first wave of Px releases: PxWallet, Px Hot or Not, PxPackages unification, beta dApp portals, and all foundational UI/UX work.*

---

## Strategic Context

During this foundational growth phase (2026), **Pixel Journey's primary focus is on delivering exceptional UI/UX, client-side architecture, developer tooling, and educational experiences** on top of the powerful existing public contracts and indexers already available in the WAX and Antelope ecosystems.

We are not (yet) in the business of deploying new custom smart contracts as our main deliverable. Instead, we are becoming **masters of composition** — showing what is possible when you combine battle-tested primitives with pixel-perfect frontend craft, rigorous client-side state management, and thoughtful educational documentation.

This approach lets us:
- Ship **much faster** and at higher quality.
- Create **reference implementations** that teach the broader community how to use `atomicassets`, `alcorammswap`, Hyperion, WharfKit, and verifiable on-chain patterns at the highest level.
- Keep our current packages (`@pxjourney/*`) lightweight, maintainable, and focused on user delight rather than contract complexity.
- Build strong foundations so that when we *do* introduce custom `pixel-journey` contracts in the future, they will be minimal, purposeful, and surrounded by excellent tooling and education.

---

## Core Rule for the Current Wave

> **Build the best possible UI/UX and developer experience on top of existing public contracts. Showcase, educate, and enable their usage.**

### What This Means in Practice

| Area                        | Preferred Approach (Current Era)                                                                 | Avoid (for now)                          | Educational Opportunity                          |
|-----------------------------|--------------------------------------------------------------------------------------------------|------------------------------------------|--------------------------------------------------|
| **NFTs / PFPs / Assets**    | `atomicassets` + `atomicmarket` for all mint, transfer, burn, listing, and metadata operations  | Custom NFT or asset contracts            | Deep guides on AtomicAssets best practices, cursor pagination, trait exposure, surviving mint ranks |
| **Swaps / DeFi / Routing**  | `alcorammswap` (Concentrated Liquidity AMM v2) for quotes, swaps, limit orders, and routing     | Custom AMM, orderbook, or router contracts | Showcasing advanced Alcor usage, concentrated liquidity patterns, quote freshness, slippage handling |
| **Verifiable Randomness / Game Mechanics** | TX hash + block header entropy via WharfKit broadcast + Hyperion queries (e.g. Px Hot or Not pairing) | Custom RNG contracts or oracle dependencies | Teaching provably fair mechanics without hidden costs or trust assumptions |
| **Governance / Treasury**   | `eosio.msig` for any on-chain multi-sig actions                                                  | Custom governance or voting contracts    | Clear patterns for safe, auditable on-chain coordination |
| **Data & History**          | Hyperion History API + Light-API as primary source of truth                                      | Custom indexing backend or subgraph      | Excellent Hyperion query patterns, real-time subscription strategies, caching layers |
| **Wallet & Signing**        | `@wharfkit/session`, `ContractKit`, `AccountKit`                                                 | Legacy UAL, eosjs, or direct private key handling | Modern self-custody patterns, session management, auto-sign opt-in, cross-chain derivation |

---

## When Might We Introduce Custom pixel-journey Contracts Later?

We leave the door open — but the bar is deliberately high. A custom contract would only be justified when **all** of the following are true:

1. **Genuine Gap**: There is a clear user or ecosystem need that cannot be reasonably solved with existing public primitives (even with creative client-side composition).
2. **Minimal Scope**: The contract does one thing extremely well and does not attempt to become a general-purpose platform.
3. **Educational Goldmine**: The contract comes with exceptional documentation, examples, and integration guides that actively help others understand advanced WAX/Antelope patterns.
4. **Audit & Safety**: It has gone through rigorous security review (and ideally formal verification where applicable).
5. **Complementary, Not Replacement**: It enhances the existing primitive ecosystem rather than duplicating or competing with it unnecessarily.

Examples of potential future areas (not commitments):
- Advanced on-chain staking or reward distribution logic that requires atomic, verifiable state transitions beyond what current indexers expose cleanly.
- Specialized game mechanics needing on-chain commitments that are expensive or awkward to express purely via asset transfers + memos.
- Cross-collection or cross-game composability primitives that the current AtomicAssets schema system does not yet support elegantly.

Until such a clear case emerges and meets the bar above, **we win by mastering and showcasing the existing stack**.

---

## How This Strategy Serves the Broader Mission

By focusing on UI/UX excellence + deep education on existing primitives during this wave, we:

- Accelerate adoption of WAX and Antelope by making their best features feel delightful and accessible.
- Create living reference implementations (PxWallet, Px Hot or Not, PxTicker, etc.) that others can study and build upon.
- Keep technical debt extremely low while we scale the number of packages and beta portals.
- Position Pixel Journey as **the premier showcase** of what thoughtful frontend craft + public infrastructure can achieve together.
- Build the muscle and reputation needed so that when we eventually ship custom contracts, the community already trusts our engineering judgment and educational quality.

---

## Checklist for Any Current-Era Px Feature or Package

- [ ] Does this feature primarily deliver UI/UX, client-side logic, or developer tooling?
- [ ] Does it leverage existing public contracts/indexers as the source of truth?
- [ ] Does it include educational content (README section, inline comments, or separate guide) that helps others understand the underlying primitive better?
- [ ] Would a new contributor or AI agent reading this code learn something valuable about WAX/Antelope best practices?
- [ ] Have we avoided introducing custom contract dependencies that could have been solved with composition + client-side work?

If the answer to any of these is weak, reconsider the approach before proceeding.

---

*This document reflects the pragmatic, education-first strategy for the 2026 Px Portal first wave. It will be revisited when the ecosystem and our internal needs evolve.*

**Px Standards — Existing Public Primitives First (Current Era)**
