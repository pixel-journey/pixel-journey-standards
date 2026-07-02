# pixel-journey-standards

**The Official Pixel Journey Standards Codex**  
*Defining & Upholding the Highest Levels of Excellence Across the Entire Px Ecosystem*

> **Version**: v0.1 — Foundational Release  
> **Status**: Living Document — Iteratively Refined with every PxPackages unification, beta portal, and major release  
> **Purpose**: The single source of truth for what "Px Brand Standards & Levels of Excellence" means for code, design, documentation, security, education, and on-chain architecture.

---

## Vision & Mission

**Pixel Journey (Px)** exists to blend **serious Web3 engineering** with **joyful retro pixel culture** — building accessible, verifiable, community-owned tools on WAX & Antelope that feel like premium 90s/early-2000s games while leveraging the best of modern decentralized infrastructure.

This standards repository is our **North Star Codex**. It exists so that:

- Every PxPackage, dApp (PxWallet, Px Hot or Not, PxTicker), mini-game, educational post, and GitBook entry meets a consistently elite bar.
- New contributors (human or AI) can onboard in hours, not weeks, and immediately produce production-grade, educational, pixel-perfect work.
- We maintain **zero technical debt** in our monorepo unification (@pxjourney/* packages) and beta portals.
- Our commitment to **ZERO CUSTOM CONTRACT OVERHEAD**, **client-side state**, **on-chain entropy**, and **self-custody** remains ironclad.

If a repo, package, or piece of content in the Pixel Journey GitHub Organization does not align with the principles and checklists here, it is not yet "Px Standard."

---

## How to Use This Codex

### For Human Developers & Contributors
1. Read the **Core Architectural Principles** (non-negotiable foundation).
2. Before starting work on any Px repo, review the relevant **standards/** section.
3. Use the **Quality Scorecard** (below) as a self-audit before opening a PR.
4. Reference **Reference Implementations** for concrete examples of excellence (e.g. high-quality educational structure).
5. Propose upgrades via issues or PRs — this codex improves through real usage.

### For AI Agents & Automated Workflows
- Treat this README + `/standards/` as your primary context for all Px development tasks.
- Every generated plan, refactor, or code must explicitly map back to at least 3 principles from this codex.
- Use the checklists in `standards/quality-gates/` for structured self-review before outputting final code.

---

## Core Architectural Principles (The Immutable Foundation)

These three principles, expanded from our Lead Core Web3 Architect mandate, govern **every** technical decision in the Px ecosystem:

### 1. ZERO CUSTOM CONTRACT OVERHEAD
> Maximize existing, public on-chain infrastructure. Never deploy custom smart contracts when public primitives suffice.

**Enforced Patterns**:
- **NFTs & PFPs**: Exclusively use `atomicassets` + `atomicmarket` for all minting, transfers, burns, and trading. No custom NFT contracts.
- **DeFi / Swaps / Liquidity**: Use `alcorammswap` (Concentrated Liquidity AMM v2) for all routing, quotes, limit orders. No custom AMM or orderbook contracts.
- **Multi-sig & Governance**: Use `eosio.msig` for any on-chain proposals or treasury actions.
- **Verifiable Mechanics** (e.g. Px Hot or Not pairing seeds): Derive entropy from public transaction hashes + block headers via WharfKit broadcast receipts. Never introduce oracles or custom RNG contracts.

**Why**: Eliminates deployment costs, audit surface, RAM bloat, and upgrade complexity. Keeps the ecosystem lightweight, auditable, and truly decentralized.

### 2. STATE PATTERNS & CLIENT-SIDE RENDERING
> Never rely on custom centralized backend databases. All state is either on-chain (via public indexers) or local-first in the browser.

**Enforced Patterns**:
- Use **Hyperion History APIs**, **Light-API**, or native RPC state table queries for all historical/on-chain data.
- **Local browser storage** (IndexedDB / localStorage with encryption for sensitive vaults) + **TanStack Query** / **Zustand** for client-side caching and optimistic UI.
- **Server Actions** (Next.js 15) only for resource delegation or heavy computation offload — never as source of truth.
- PxWallet example: Encrypted master password vault lives 100% client-side. Cross-chain key derivation happens in-browser via Web Crypto API. No server ever sees private keys.

**Why**: True self-custody, instant loads via CDN/static JSON (see GitOps patterns), full auditability, zero ongoing server costs.

### 3. ON-CHAIN ENTROPY (Provably Fair Randomness)
> For all randomized game mechanics, use deterministic client-side parsing of WharfKit broadcast transaction hashes combined with block headers.

**Enforced Patterns**:
- In Px Hot or Not, verifiable seed/pairing is derived from the `pxhot.pxj` transfer TX memo + recent block headers.
- No RAM tables for RNG state. No oracle fees. No trusted third parties.
- Result is **provably fair**, reproducible by anyone with the TX ID, and completely free.

**Why**: Aligns with Web3 ethos of trustlessness while delivering delightful retro-game UX without hidden costs or centralization risks.

---

## The Px Repo Quality Scorecard (Benchmark for Excellence)

Every repository, package, or major release in the Pixel Journey org is measured against this scorecard. A repo is considered "Px Standard" when it scores **≥ 85/100** and has no critical gaps.

| Category                        | Criteria (Must-Have for High Score)                                                                 | Weight | Gold-Standard Example Reference                  | Status in Current Px Repos |
|--------------------------------|-----------------------------------------------------------------------------------------------------|--------|--------------------------------------------------|----------------------------|
| **Documentation Excellence**   | Every folder/subfolder contains a detailed, educational README.md explaining purpose, architecture, usage, pitfalls, and fit in the larger ecosystem. Root README contains architecture diagram (text/Mermaid), data flow, troubleshooting table, migration path, and full file-by-file map. | 25%    | gkniftyheads-tracker (every folder has README; exhaustive root handbook) | Needs systematic uplift   |
| **Educational Spirit**         | Explains the "why" behind every decision. Includes WAX/Antelope best practices (citing onblock.dev where relevant), common pitfalls, edge cases, and onboarding guidance for new devs/AI agents. | 20%    | Same — onblock.dev citations, migration sections, "Russian-doll layering" explanations | Partial (improving in PxPackages) |
| **Architectural Clarity**      | Clear visual/text diagrams, "Russian-doll" layering descriptions, config-driven design (all magic numbers in `config.json`), and explicit mapping to the 3 Core Principles above. | 15%    | gkniftyheads-tracker (data flow diagrams, layering explanation) | In progress via PxPackages unification |
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
│   └── ISSUE_TEMPLATE/        # bug_report.md, standards-proposal.md, etc.
├── standards/                 # The living heart of the codex
│   ├── README.md
│   ├── engineering/           # TypeScript, monorepo, refactoring, AI-assisted dev
│   ├── web3-onchain/          # ZERO CUSTOM CONTRACT, WharfKit, AtomicAssets, verifiable entropy
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

### Phase 0 — Foundation (This Conversation — v0.1)
- [x] Establish this comprehensive root README as the North Star.
- [ ] Polish CONTRIBUTING.md and add LICENSE.
- [ ] Create initial `standards/` subfolder structure with high-quality starter content for Engineering + Web3-OnChain pillars.
- [ ] Add basic .github/ ISSUE_TEMPLATE for standards proposals.

### Phase 1 — Core Engineering & Monorepo Standards (Next 1–2 turns)
- Full `standards/engineering/` deep-dives: TypeScript strictness, PxPackages monorepo wiring rules (no individual styling, unified exports), refactoring playbooks (150+ item style from PxWallet audits), AI agent orchestration standards.

### Phase 2 — Web3 & On-Chain Excellence
- `standards/web3-onchain/zero-custom-contract-philosophy.md` (expanded manifesto + decision matrix)
- WharfKit + AtomicAssets + Hyperion integration patterns
- Verifiable on-chain mechanics (TX memo seeds, block-header entropy)
- Security self-custody vault standards (encrypted master pw, cross-chain derivation)

### Phase 3 — UI/UX, Documentation & Quality Gates
- Tight integration with Design System repo
- Every-folder README enforcement + educational spirit rubric
- Repo Readiness Scorecard v1.0 + automated validation workflow

### Phase 4 — Education, Onboarding & Ecosystem Integration
- WAX 101 tailored for Px devs (pixel-perfect + verifiable)
- Full mapping of how Standards → PxPackages → Design System → Templates → Blueprint Catalog work together
- GitBook knowledge bank alignment

**Success Metric**: When a new PxPackage can be scaffolded from `templates/`, pass the Quality Scorecard on first PR, and its documentation is referenced by future contributors within days — we have succeeded.

---

## Immediate Next Steps (This Conversation)

We will work **bit by bit**, iterating with precision:

1. **Right now**: This README v0.1 is live. The foundation is set.
2. **Next micro-turn**: I will expand `standards/engineering-overview.md` and `standards/web3-onchain/` with concrete, actionable content drawn from our PxWallet, Px Hot or Not, and PxPackages unification work.
3. **Your input welcome**: Which section should we deepen first? Engineering monorepo rules? The Zero Custom Contract decision matrix? UI/UX enforcement? Or shall we add a new `standards/quality-gates/pre-merge-checklist.md`?

This codex will become the most valuable document in the entire Pixel Journey organization — the document every AI dev bot, new contributor, and core maintainer reaches for first.

**Let's build the highest possible standard. Together.**

---

*Part of the Pixel Journey GitHub Organization — Built for the WAXFAMs community & all future Px, Web3, and Antelope developers.*

**Px Standards v0.1 — Foundation Established.**
