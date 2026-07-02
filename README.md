# pixel-journey-standards

**The Official Pixel Journey Standards Codex**  
*Defining & Upholding the Highest Levels of Excellence Across the Entire Px Ecosystem*

> **Version**: v0.3 — Strong Foundation Complete  
> **Status**: Living Document — Iteratively Refined with every PxPackages unification, beta portal, and major release  
> **Purpose**: The single source of truth for what "Px Brand Standards & Levels of Excellence" means for code, design, documentation, security, education, and on-chain architecture.

---

## Vision & Mission

**Pixel Journey (Px)** exists to blend **serious Web3 engineering** with **joyful retro pixel culture** — building accessible, verifiable, community-owned tools on WAX & Antelope that feel like premium 90s/early-2000s games while leveraging the best of modern decentralized infrastructure.

This standards repository is our **North Star Codex**. It exists so that:

- Every PxPackage, dApp (PxWallet, Px Hot or Not, PxTicker), mini-game, educational post, and GitBook entry meets a consistently elite bar.
- New contributors (human or AI) can onboard in hours, not weeks, and immediately produce production-grade, educational, pixel-perfect work.
- We maintain **zero technical debt** in our monorepo unification (@pxjourney/* packages) and beta portals.
- Our current strategic focus is on **building world-class UI/UX layers on top of existing public contracts**, while showcasing and educating the ecosystem on how to use those primitives at the highest level.

If a repo, package, or piece of content in the Pixel Journey GitHub Organization does not align with the principles and checklists here, it is not yet "Px Standard."

---

## How to Use This Codex

### For Human Developers & Contributors
1. Start with the **Core Architectural Principles** (current strategic stance).
2. Before starting significant work, review the **Repo Readiness Scorecard**.
3. Follow the **Every Folder README Rule** and **Monorepo & PxPackages Rules**.
4. Use the web3-onchain patterns documents for verifiable mechanics and primitive usage.
5. Propose upgrades via the standards-proposal issue template.

### For AI Agents & Automated Workflows
- Treat this entire repository (especially README + scorecard + monorepo rules) as primary context.
- Every plan or code output must map back to the principles and pass a mental self-audit against the scorecard.
- Always produce or update READMEs according to the documentation rule.

---

## Core Architectural Principles (Current Strategic Stance — 2026 Px Portal Wave)

These principles govern our **current massive first wave** of Px Portal ecosystem releases.

### 1. Existing Public Primitives First (Current Era Strategy)
> For the current wave, we build **UI/UX layers, client-side state machines, and developer tooling on top of battle-tested public contracts and indexers** rather than introducing new custom smart contracts.

**Enforced Patterns**: `atomicassets` + `atomicmarket`, `alcorammswap`, Hyperion, WharfKit, eosio.msig, TX + block header entropy.

**Future Flexibility**: High bar for custom `pixel-journey` contracts later (genuine gap + minimal scope + exceptional education + audit).

### 2. State Patterns & Client-Side Rendering
> Hyperion + local-first encrypted storage + TanStack Query as source of truth.

### 3. On-Chain Entropy & Verifiable Randomness
> TX hash + block header derivation for game mechanics (see `verifiable-onchain-entropy-patterns.md`).

---

## The Px Repo Quality Scorecard

Every repository, package, or major release is measured against `standards/quality-gates/repo-readiness-scorecard.md`.

**Px Standard threshold**: ≥ 85/100 with no critical (0-point) failures.

Use it before every major PR or release.

---

## Repository Structure (Current)

```
 pixel-journey-standards/
├── README.md
├── CONTRIBUTING.md
├── LICENSE
├── .github/ISSUE_TEMPLATE/standards-proposal.md
├── standards/
│   ├── engineering/
│   │   ├── engineering-overview.md
│   │   └── monorepo-pxpackages-rules.md          ← New
│   ├── web3-onchain/
│   │   ├── existing-primitives-first.md
│   │   └── verifiable-onchain-entropy-patterns.md
│   ├── quality-gates/
│   │   └── repo-readiness-scorecard.md
│   ├── documentation/
│   │   └── every-folder-readme-rule.md             ← New
│   └── ...
```

---

## Current Status & Master Upgrade Roadmap

**Foundation Phase (v0.3) — Largely Complete**
- Strong strategic principles with pragmatic nuance for the current wave
- Concrete implementation patterns (verifiable entropy)
- Practical quality gate (scorecard)
- Documentation enforcement rule
- Monorepo & PxPackages structural rules

**Next Priorities**
- UI/UX & Design System alignment pillar
- Education & onboarding deep-dives (WAX 101 for Px devs)
- Further concrete integration patterns (Hyperion + WharfKit hooks)
- Automation (validation workflow against the scorecard)

---

## Immediate Next Steps

We now have a very strong, usable foundation. The next natural expansions are:

1. UI/UX alignment with the Design System (zero individual styling enforcement in more detail)
2. Education-onboarding pillar
3. More concrete code patterns for common Px use cases

Which direction would serve the current PxPackages unification and beta portal work best right now?

This codex is becoming a genuine force multiplier for quality across the entire organization.

**Px Standards v0.3 — Strong, Practical Foundation Established.**
