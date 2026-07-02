# When & How to Introduce Custom pixel-journey Contracts

**Decision Framework for Future On-Chain Logic**

*Part of the Pixel Journey Standards Codex*

---

## Strategic Context

During the current massive first wave of Px Portal releases (2026), we are deliberately focusing on building world-class UI/UX, client-side architecture, and developer tooling **on top of existing public WAX/Antelope primitives** (AtomicAssets, Alcor AMM, Hyperion, eosio.msig, etc.).

This approach allows us to ship faster, keep technical debt low, and produce highly educational reference implementations.

However, we recognize that there may come a time when introducing custom `pixel-journey` smart contracts becomes the right decision. This document provides a clear, high-bar framework for making that call.

---

## The High Bar for Custom Contracts

A custom `pixel-journey` contract should only be introduced when **all** of the following conditions are met:

### 1. Genuine Gap
There is a clear, well-defined user or ecosystem need that cannot be reasonably solved through creative composition of existing public primitives (even with advanced client-side logic, Hyperion queries, and verifiable TX-based patterns).

### 2. Minimal Scope
The contract does **one thing extremely well** and does not attempt to become a general-purpose platform or duplicate functionality that already exists.

### 3. Educational Goldmine
The contract must come with **exceptional documentation**, examples, integration guides, and educational content that actively helps the broader WAX/Antelope community understand advanced patterns.

### 4. Security & Audit Rigor
It has gone through rigorous security review (and ideally formal methods or multiple independent audits where appropriate).

### 5. Complementary, Not Competitive
It enhances and composes well with existing primitives rather than creating unnecessary fragmentation or duplication in the ecosystem.

### 6. Clear Long-Term Value
There is a strong, defensible case that the contract will deliver meaningful, lasting value to Px users and the broader ecosystem that justifies the added complexity, deployment cost, RAM usage, and maintenance burden.

---

## Examples of Potential Justified Use Cases (Illustrative Only)

These are **not commitments** — only examples of areas where a custom contract *might* eventually make sense if the high bar above is met:

- Advanced on-chain staking or reward distribution logic requiring atomic, verifiable state transitions that are difficult to express cleanly via existing indexers and asset transfers.
- Specialized game mechanics needing on-chain commitments, hidden state, or complex multi-party interactions that are expensive or awkward to handle purely client-side.
- Cross-collection or cross-game composability primitives that the current AtomicAssets schema and transfer model do not support elegantly.
- Novel verifiable randomness or commitment schemes that go meaningfully beyond what TX hash + block header patterns can provide.

Even in these areas, we would first exhaust creative client-side + existing primitive solutions before considering a custom contract.

---

## Process for Proposing a Custom Contract

1. Open a detailed proposal in the Standards Codex (or relevant repo) that addresses all six criteria above.
2. Demonstrate why existing primitives + client-side composition are insufficient.
3. Provide a minimal viable contract scope and clear educational value proposition.
4. Secure alignment from core maintainers and, where appropriate, broader ecosystem input.
5. Plan for rigorous auditing and exceptional documentation from the start.

---

## Current Default Stance (2026 Wave)

**Until a proposal clearly meets the full high bar above, the default position remains: build excellent UI/UX and client-side systems on top of existing public primitives.**

This keeps us fast, lightweight, educational, and maximally aligned with the current phase of Px growth.

---

*This framework protects the lightweight, educational, and community-aligned spirit of Pixel Journey while leaving a responsible path open for future on-chain innovation.*

**Px Standards — Custom Contracts Decision Framework**