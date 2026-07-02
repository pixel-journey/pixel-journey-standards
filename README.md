# pixel-journey-standards

**The Official Pixel Journey Standards Codex**  
*Defining & Upholding the Highest Levels of Excellence Across the Entire Px Ecosystem*

> **Version**: v0.2 — Nuanced Principles Update  
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
1. Read the **Core Architectural Principles** (current strategic stance for the 2026 Px Portal wave).
2. Before starting work on any Px repo, review the relevant **standards/** section.
3. Use the **Quality Scorecard** (below) as a self-audit before opening a PR.
4. Reference **Reference Implementations** for concrete examples of excellence.
5. Propose upgrades via issues or PRs — this codex improves through real usage.

### For AI Agents & Automated Workflows
- Treat this README + `/standards/` as your primary context for all Px development tasks.
- Every generated plan, refactor, or code must explicitly map back to the current strategic principles.
- Use the checklists in `standards/quality-gates/` for structured self-review before outputting final code.

---

## Core Architectural Principles (Current Strategic Stance — 2026 Px Portal Wave)

These principles govern our **current massive first wave** of Px Portal ecosystem releases (PxWallet, Px Hot or Not alpha, PxPackages unification, beta dApp portals, etc.). They prioritize **maximum leverage of existing public infrastructure** while delivering pixel-perfect, educational, production-grade experiences.

### 1. Existing Public Primitives First (Current Era Strategy)
> For the current wave of Px releases, we build **UI/UX layers, client-side state machines, and developer tooling on top of battle-tested public contracts and indexers** rather than introducing new custom smart contracts.

**Why this approach right now**:
- Enables us to ship **massive amounts of high-quality, educational, pixel-perfect UI/UX** extremely fast.
- Showcases and teaches the WAX/Antelope ecosystem how to use existing powerful primitives (`atomicassets`, `atomicmarket`, `alcorammswap`, Hyperion, WharfKit, eosio.msig, etc.) at the highest possible level.
- Keeps the current PxPackages and beta portals **lightweight, auditable, and low-maintenance**.
- Avoids unnecessary contract deployment costs, RAM allocation, and audit surface during this foundational growth phase.

**Enforced Patterns in Current Wave**:
- **NFTs, PFPs, Assets**: Exclusively use `atomicassets` + `atomicmarket` for minting, transfers, burns, trading, and metadata. No custom NFT contracts in this phase.
- **DeFi / Swaps / Quotes / Routing**: Use `alcorammswap` (Concentrated Liquidity AMM v2) for all swap, limit order, and routing logic.
- **Verifiable Game Mechanics** (e.g. Px Hot or Not pairing): Derive entropy and verifiable seeds from public transaction hashes + block headers via WharfKit broadcast receipts + Hyperion queries. No oracles or custom RNG contracts.
- **Multi-sig / Governance actions**: Use `eosio.msig` where on-chain coordination is needed.
- **Data & History**: Hyperion History APIs + Light-API as the primary source of truth for all on-chain state and events.

**Future Flexibility**:
There **will** be a future for custom `pixel-journey` contracts (e.g. advanced on-chain game logic, staking mechanics, or verifiable randomness that exceeds simple TX-hash entropy). When that time comes, any new contract must meet an extremely high bar: solve a genuine gap that public primitives cannot, be minimal in scope, thoroughly audited, and accompanied by exceptional educational documentation.

**For now (2026 Portal Wave)**: We win by becoming **masters of the existing primitives** and delivering delightful, educational UI/UX on top of them.

### 2. State Patterns & Client-Side Rendering
> Never rely on custom centralized backend databases. All state is either on-chain (via public indexers) or local-first in the browser.

**Enforced Patterns**:
- Use **Hyperion History APIs**, **Light-API**, or native RPC state table queries for all historical/on-chain data.
- **Local browser storage** (IndexedDB / localStorage with encryption for sensitive vaults) + **TanStack Query** / **Zustand** for client-side caching and optimistic UI.
- **Server Actions** (Next.js 15) only for resource delegation or heavy computation offload — never as source of truth.
- PxWallet example: Encrypted master password vault lives 100% client-side. Cross-chain key derivation happens in-browser via Web Crypto API. No server ever sees private keys.

**Why**: True self-custody, instant loads via CDN/static JSON (GitOps patterns), full auditability, zero ongoing server costs.

### 3. On-Chain Entropy & Verifiable Randomness
> For randomized game mechanics in the current wave, use deterministic client-side parsing of WharfKit broadcast transaction hashes combined with recent block headers.

**Enforced Patterns**:
- In Px Hot or Not, verifiable seed/pairing is derived from the `pxhot.pxj` transfer TX memo + recent block headers (queryable via Hyperion).
- No RAM tables for RNG state. No oracle fees. No trusted third parties.
- Result is **provably fair**, reproducible by anyone with the TX ID, and completely free.

**Why**: Aligns with Web3 ethos of trustlessness while delivering delightful retro-game UX without hidden costs or centralization risks during this phase.

---

## The Px Repo Quality Scorecard (Benchmark for Excellence)

Every repository, package, or major release in the Pixel Journey org is measured against this scorecard. A repo is considered "Px Standard" when it scores **≥ 85/100** and has no critical gaps.

| Category                        | Criteria (Must-Have for High Score)                                                                 | Weight | Gold-Standard Example Reference                  | Status in Current Px Repos |
|--------------------------------|-----------------------------------------------------------------------------------------------------|--------|--------------------------------------------------|----------------------------|
| **Documentation Excellence**   | Every folder/subfolder contains a detailed, educational README.md explaining purpose, architecture, usage, pitfalls, and fit in the larger ecosystem. Root README contains architecture diagram (text/Mermaid), data flow, troubleshooting table, migration path, and full file-by-file map. | 25%    | gkniftyheads-tracker (every folder has README; exhaustive root handbook) | Needs systematic uplift   |
| **Educational Spirit**         | Explains the "why" behind every decision. Includes WAX/Antelope best practices, common pitfalls, edge cases, and onboarding guidance for new devs/AI agents. | 20%    | Same — onblock.dev citations, migration sections, "Russian-doll layering" explanations | Partial (improving in PxPackages) |
| **Architectural Clarity**      | Clear visual/text diagrams, layering descriptions, config-driven design, and explicit mapping to the current strategic principles. | 15%    | gkniftyheads-tracker (data flow diagrams, layering explanation) | In progress via PxPackages unification |
| **Code Quality & Modularity**  | Strict TypeScript. Clean, annotated, modular code. No bloat. Progressive enhancement. Full type-safety interfaces. Uses WharfKit (Session/Contract/Account Kit) exclusively — never legacy UAL/eosjs. | 15%    | PxWallet & Px Hot or Not refactors (150+ item roadmaps, TDZ fixes, userPfp dedup) | Strong in active packages |
| **Security & Self-Custody**    | Encrypted local vaults, no private key exposure, cross-chain derivation via Web Crypto, opt-in auto-sign, content-script isolation (Chrome MV3). Explicit warnings against common Web3 footguns. | 10%    | PxWallet god-mode vault design | Core strength of Px ecosystem |
| **UI/UX Pixel-Perfect**        | Adherence to Design System (glassmorphic/CRT/haptics, Press Start 2P fonts, 120Hz fluid, luxury-dark). No individual component styling — all via unified design tokens. Responsive + accessible retro aesthetic. | 10%    | demo/index.html in high-quality trackers + future Px design-system integration | Needs stronger enforcement |
| **GitOps & Maintainability**   | GitHub Actions for zero-cost daily syncs/validations. Static JSON + CDN delivery where possible. Versioned data. Easy to extend. Conventional commits + clear PR templates. | 5%     | .github/workflows/daily-sync.yml + scripts/ in reference tracker | Emerging in PxPackages |

**Scoring Guidance**: Use `standards/quality-gates/repo-readiness-scorecard.md` for detailed self-assessment before every major PR or release.

---

## Repository Structure (The Educational Skeleton)

This repo itself must exemplify the standards it defines. Proposed canonical structure (being implemented iteratively):

```
 pixel-journey-standards/
├── README.md                  # ← You are here (North Star Handbook)
├── CONTRIBUTING.md            # Contribution guidelines + upgrade process
├── LICENSE                    # MIT (open for WAXFAMs & broader ecosystem)
├── .github/
│   ├── workflows/             # standards-validation.yml, link-checker, etc.
│   └── ISSUE_TEMPLATE/        # For proposing new standards, reporting gaps
├── standards/
│   ├── README.md
│   ├── engineering/           # TypeScript, monorepo, refactoring, AI-assisted dev
│   ├── web3-onchain/          # Existing Primitives First strategy + future contract criteria
│   ├── ui-ux-design/          # Pixel-perfect, design-system alignment, retro CRT/glass
│   ├── documentation/         # Every-folder-README rule, educational guidelines, Mermaid standards
│   ├── quality-gates/         # Pre-merge checklists, scorecards, audit playbooks
│   └── education-onboarding/  # WAX 101 for Px devs, vision deep-dives, contributing guides
├── templates/                 # Reusable boilerplates (PR descriptions, new package scaffolds, audit reports)
├── examples/                  # Annotated real-world excerpts from Px repos (with permission)
└── tools/                     # Future: validation scripts, linters for standards compliance
```

**Rule**: No file or folder exists without its own `README.md` (or clear inline docs) explaining its purpose and how it advances Px excellence.

---

## Reference Implementations of Px-Quality

These external or sibling repositories currently best exemplify the documentation, architectural clarity, and educational spirit we demand:

- **gkniftyheads-tracker** (inspiration benchmark): Exhaustive per-folder READMEs, full script documentation, WAX API best practices, troubleshooting tables, migration paths, config-driven pipeline, beautiful self-contained demo. A masterclass in GitOps serverless + educational value.
- **pixel-journey-design-system** (sibling): Source of truth for all visual tokens, components, and retro pixel themes. All Px UI work must import from here — no ad-hoc styling.
- **pixel-journey-templates** (sibling): Boilerplate scaffolds for new PxPackages, mini-dApps, and GitHub repos. New work starts here.
- **wax-ecosystem-blueprint-catalog** (sibling): Curated, living catalog of WAX patterns, contracts, and tools. Standards here reference and extend it.

When building or auditing any Px artifact, ask: "Does this match or exceed the clarity and completeness of the gkniftyheads-tracker model?"

---

## Current Status & Master Upgrade Roadmap

### Phase 0 — Foundation (This Conversation — v0.2)
- [x] Establish comprehensive root README as the North Star with nuanced "Existing Public Primitives First" principle.
- [x] Upgrade `standards/engineering-overview.md` with monorepo, TypeScript, and AI standards.
- [x] Add balanced `standards/web3-onchain/existing-primitives-first.md`.
- [ ] Polish CONTRIBUTING.md and add LICENSE.
- [ ] Create initial .github/ ISSUE_TEMPLATE for standards proposals.

### Phase 1 — Deepen Web3-OnChain & Education Pillars
- Full decision framework for future custom contracts.
- Concrete integration patterns (WharfKit hooks, Hyperion + AtomicAssets best practices, verifiable entropy).
- Educational deep-dives that help the broader WAX community use these primitives better.

### Phase 2 — Quality Gates & Documentation Enforcement
- Full `repo-readiness-scorecard.md` (inspired by gkniftyheads-tracker excellence).
- Pre-merge checklist + automated validation workflow.

### Phase 3 — UI/UX + Design System Lock-in + Monorepo Maturity
- Strict design-system token enforcement.
- PxPackages unification standards finalized.

### Phase 4 — Education, Onboarding & Ecosystem Integration
- WAX 101 tailored for Px devs (pixel-perfect + verifiable).
- Full mapping of how Standards connect the entire Px ecosystem.

**Success Metric**: When a new PxPackage can be scaffolded from templates, pass the Quality Scorecard on first PR, and its documentation helps others understand both the UI excellence *and* the underlying WAX primitives it showcases.

---

## Immediate Next Steps (This Conversation)

We are moving with precision and educational intent:

1. **This turn**: Nuanced Core Principle #1 + new `existing-primitives-first.md` document is now live.
2. **Next micro-turn**: We can either:
   - Deepen the new web3-onchain strategy document with concrete code patterns and examples from Px Hot or Not / PxWallet.
   - Create the first version of the `repo-readiness-scorecard.md`.
   - Expand `standards/engineering/` with monorepo wiring rules specific to the current "UI on top of existing contracts" era.

Your direction wanted: Which thread should we pull on next to keep building the highest standard possible?

This codex is becoming exactly what the Pixel Journey ecosystem needs — clear, pragmatic, educational, and forward-looking without being dogmatic.

**Let's continue.**

---

*Part of the Pixel Journey GitHub Organization — Built for the WAXFAMs community & all future Px, Web3, and Antelope developers.*

**Px Standards v0.2 — Nuanced Principles + Strategic Clarity Established.**
