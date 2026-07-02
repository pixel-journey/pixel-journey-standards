# Engineering Standards Overview (v0.1)

**Part of the Pixel Journey Standards Codex**  
*Core rules for TypeScript, monorepo architecture, refactoring discipline, and AI-assisted development across all @pxjourney/* packages and dApps.*

---

## 1. Foundational Mandates

### Strict TypeScript Everywhere
- **No `any` except in explicitly typed external API response wrappers** (and even then, immediately narrow).
- Full interface/type definitions for every data shape (assets, templates, leaderboards, user state, WharfKit sessions).
- Use `satisfies` and `as const` for config objects and magic-number maps.
- Path aliases via `tsconfig.json` (`@pxjourney/*`, `@/components`, etc.) for monorepo clarity.

### Monorepo & PxPackages Unification Rules (Non-Negotiable)
From the PxPackages unification effort (May–Jun 2026):

- **Single source of truth for wiring**: All inter-package communication goes through a small set of well-typed SDK hooks or context providers. No direct imports of internal implementation details between packages.
- **Zero individual styling**: Every UI component **must** import tokens, variants, and primitives exclusively from `pixel-journey-design-system`. No Tailwind classes or inline styles that duplicate design tokens. This ensures pixel-perfect consistency and easy theme swaps (CRT, glassmorphic, high-contrast retro).
- **Unified exports**: Each `@pxjourney/*` package exposes a clean public API surface. Internal files are not importable from outside the package.
- **Shared build/test/lint pipeline**: Turborepo or equivalent. One `pnpm` workspace root. Consistent `tsup` / `tsup` or Next.js build configs.
- **Versioning**: Changes that affect multiple packages trigger coordinated version bumps and changelogs. Use Changesets or similar.

### Refactoring & Audit Discipline
All major refactors (PxWallet 150+ item / 26-phase master plan, Px Hot or Not alpha, PxPackages 92-point upgrade) must follow this pattern:

1. **Deep Audit First** — Read every relevant file. Map data flow, identify TDZ, duplicate logic (e.g. userPfp), prop drilling, any deviation from the 3 Core Principles.
2. **Produce Living Roadmap** — Numbered phases, concrete file targets, estimated lines changed, risk assessment.
3. **Implement in Small, Verifiable Chunks** — Each chunk must build and pass lint/typecheck.
4. **Self-Review Against Scorecard** — Before PR, run the Quality Gate checklist.
5. **Document the "Why"** — Every non-obvious decision gets a comment or ADR entry.

---

## 2. Recommended Tech Stack (Px Standard)

| Layer                    | Standard Choice                  | Rationale & Notes                                                                 |
|--------------------------|----------------------------------|-----------------------------------------------------------------------------------|
| Language                 | TypeScript (strict)             | Type safety + excellent DX for complex on-chain + client state                    |
| Frontend Framework       | Next.js 15+ (App Router)        | Server Actions for heavy lifting, excellent streaming, built-in optimizations     |
| Alternative (light)      | Vite + React / SvelteKit        | For mini-dApps, Chrome extensions, or ultra-light packages                        |
| State Management         | Zustand + TanStack Query        | Minimal boilerplate, excellent caching, devtools                                  |
| Styling                  | Tailwind + Design System tokens | Never raw Tailwind for brand elements — always via design-system primitives       |
| Animations               | Framer Motion                   | 120Hz fluid, spring physics, exit/enter orchestration for retro modals            |
| Wallet / Auth            | @wharfkit/session + ContractKit | Modern, actively maintained WAX standard. Full Session Kit + Account Kit support  |
| On-Chain Data            | Hyperion + AtomicAssets SDK     | Public indexers, no custom backend. Cursor pagination for large collections       |
| Randomness (games)       | TX hash + block header parsing  | On-chain entropy, zero RAM/oracle cost, provably fair                             |
| Build / Monorepo         | Turborepo + pnpm workspaces     | Fast incremental builds, shared scripts, consistent publishing                    |

---

## 3. AI-Assisted Development Standards

We heavily leverage parallel AI (Grok + Claude in Antigravity IDE + custom agents).

**Rules for High-Quality AI Output in Px**:
- Always start with full context (latest src zip or monorepo tree + relevant standards section).
- Demand **ultra-detailed production-ready plans** (100+ steps, phase breakdowns, edge cases).
- Require explicit mapping back to Core Principles and this codex.
- After generation, human/AI lead performs **standards scorecard review** before merge.
- Track AI credit usage and task progress (Pixel Journey AI Agent Index pattern).

**Anti-Patterns to Reject**:
- Vague or hand-wavy plans.
- Code that introduces custom contract dependencies.
- Styling that bypasses the Design System.
- Missing error states, loading states, or accessibility considerations.

---

## 4. Checklist for Any Engineering PR

- [ ] All new code is strict TypeScript with full type coverage.
- [ ] No styling outside Design System tokens/primitives.
- [ ] Follows monorepo wiring rules (clean public exports, no cross-package implementation imports).
- [ ] Maps explicitly to at least one Core Architectural Principle.
- [ ] Includes or updates relevant documentation (README or inline).
- [ ] Passes local `pnpm lint && pnpm typecheck && pnpm build`.
- [ ] Self-scored against `standards/quality-gates/repo-readiness-scorecard.md` (when available).

**This checklist is non-negotiable for Px Standard work.**

---

*Iteratively expanded from real PxWallet, Px Hot or Not, and PxPackages unification audits (2026).*