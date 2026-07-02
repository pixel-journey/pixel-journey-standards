# Repo Readiness Scorecard v0.1

**The Practical Quality Gate for Pixel Journey Repositories, Packages & Releases**

*Part of the Pixel Journey Standards Codex*  
*Use this before every major PR, package release, beta portal launch, or public demo.*

---

## Purpose

This scorecard turns our high-level principles into a **measurable, actionable quality gate**. It ensures that every artifact shipping under the Pixel Journey brand meets our standards of excellence in documentation, education, architecture, code quality, security, UI/UX, and strategic alignment.

A repo, package, or major feature is considered **"Px Standard"** when it achieves **≥ 85/100** with no critical (0-point) failures.

It is designed to be used by:
- Human maintainers before opening PRs or cutting releases
- AI agents as a structured self-review before generating final output
- The broader community when evaluating Px work

---

## How to Use This Scorecard

1. **Self-audit** before you consider a PR or release "ready".
2. **Score honestly** — the goal is continuous improvement, not perfection on the first try.
3. **Document gaps** — if a category scores low, note what is missing and create a follow-up task.
4. **Reference the linked standards documents** for deeper guidance.
5. **Update this scorecard** as we learn (it is a living document).

**Scoring Scale**:
- **2 points** = Excellent / Fully meets or exceeds the criteria
- **1 point** = Acceptable but could be stronger
- **0 points** = Missing, weak, or violates a core principle (blocks "Px Standard" status)

---

## Scorecard

### 1. Documentation Excellence (Max 20 points)

| # | Criterion | Score (0-2) | Notes / Evidence |
|---|-----------|-------------|------------------|
| 1.1 | Root README contains clear vision, architecture overview (text/Mermaid), data flow or layering explanation, quickstart, troubleshooting, and file-by-file map | | |
| 1.2 | Every major folder/subfolder has its own high-quality README explaining purpose, how it fits the larger system, usage, pitfalls, and educational value | | |
| 1.3 | All public APIs, hooks, and major functions have clear JSDoc / inline documentation | | |
| 1.4 | Configuration is centralized and well-documented (no magic numbers scattered in code) | | |
| 1.5 | Changelog or release notes exist and are kept up to date | | |

**Subtotal** (Max 10) | | | |

*Reference*: `standards/documentation/every-folder-readme-rule.md` (when complete)

### 2. Educational Spirit & Ecosystem Value (Max 15 points)

| # | Criterion | Score (0-2) | Notes / Evidence |
|---|-----------|-------------|------------------|
| 2.1 | The work explains the "why" behind key decisions (not just the "how") | | |
| 2.2 | Includes concrete examples, edge cases, or common pitfalls that help others learn | | |
| 2.3 | Actively showcases or teaches usage of existing WAX/Antelope public primitives (AtomicAssets, Alcor, Hyperion, WharfKit, etc.) | | |
| 2.4 | A new contributor or AI agent reading the code/docs would learn something valuable about modern WAX patterns | | |
| 2.5 | Documentation or comments would still be useful 6–12 months from now | | |

**Subtotal** (Max 10) | | | |

*Strongly aligned with the gkniftyheads-tracker benchmark of excellence.*

### 3. Strategic Alignment — Existing Public Primitives First (Max 15 points)

| # | Criterion | Score (0-2) | Notes / Evidence |
|---|-----------|-------------|------------------|
| 3.1 | The feature/package primarily delivers UI/UX, client-side logic, or developer tooling on top of existing public contracts/indexers | | |
| 3.2 | Avoids introducing custom smart contracts unless a genuine gap exists and the high bar in `existing-primitives-first.md` is met | | |
| 3.3 | Verifiable mechanics (if any) use TX hash + block header entropy patterns (see `verifiable-onchain-entropy-patterns.md`) | | |
| 3.4 | Data fetching and state use Hyperion / public indexers + local-first patterns rather than custom backends | | |
| 3.5 | The work helps others understand and adopt existing WAX primitives more effectively | | |

**Subtotal** (Max 10) | | | |

### 4. Code Quality, Modularity & Maintainability (Max 15 points)

| # | Criterion | Score (0-2) | Notes / Evidence |
|---|-----------|-------------|------------------|
| 4.1 | Strict TypeScript with comprehensive type coverage (minimal `any`) | | |
| 4.2 | Clean modular architecture with clear public API surfaces (especially important for @pxjourney/* monorepo packages) | | |
| 4.3 | No individual component styling — all UI uses tokens and primitives from the Design System | | |
| 4.4 | Uses WharfKit (Session/Contract/Account Kit) exclusively for wallet interactions | | |
| 4.5 | Code is readable, well-commented where non-obvious, and free of obvious duplication or technical debt | | |

**Subtotal** (Max 10) | | | |

### 5. Security & Self-Custody (Max 10 points)

| # | Criterion | Score (0-2) | Notes / Evidence |
|---|-----------|-------------|------------------|
| 5.1 | Sensitive data (private keys, seeds, master passwords) never leaves the client | | |
| 5.2 | Encrypted local vaults or secure storage patterns are used where appropriate (PxWallet model) | | |
| 5.3 | Cross-chain key derivation (if any) happens client-side via Web Crypto API | | |
| 5.4 | Auto-sign / transaction signing is opt-in and clearly communicated to the user | | |
| 5.5 | Chrome extension (if applicable) follows MV3 best practices with proper content script / background isolation | | |

**Subtotal** (Max 10) | | | |

### 6. UI/UX Pixel-Perfect & Design System Alignment (Max 10 points)

| # | Criterion | Score (0-2) | Notes / Evidence |
|---|-----------|-------------|------------------|
| 6.1 | All visual elements use Design System tokens, variants, and primitives (no ad-hoc Tailwind or inline styles for brand elements) | | |
| 6.2 | Retro pixel aesthetic (glassmorphic/CRT where appropriate), 120Hz fluid animations, haptics, and Press Start 2P typography are respected | | |
| 6.3 | Loading, error, empty, and edge states are thoughtfully designed and implemented | | |
| 6.4 | Responsive and accessible (keyboard navigation, screen reader support, high-contrast considerations) | | |
| 6.5 | Modals, tabs, and complex interactions feel polished and "pixel-perfect" | | |

**Subtotal** (Max 10) | | | |

### 7. GitOps, Testing & Release Hygiene (Max 5 points)

| # | Criterion | Score (0-2) | Notes / Evidence |
|---|-----------|-------------|------------------|
| 7.1 | Uses conventional commits and clear PR descriptions that reference relevant standards or scorecards | | |
| 7.2 | Includes or updates tests where appropriate (unit, integration, or visual) | | |
| 7.3 | GitHub Actions or equivalent automation is used for builds, linting, type-checking, and deployments where applicable | | |

**Subtotal** (Max 6) | | | |

---

## Final Scoring

| Category | Max Points | Your Score |
|----------|------------|------------|
| Documentation Excellence | 10 | |
| Educational Spirit | 10 | |
| Strategic Alignment (Primitives First) | 10 | |
| Code Quality & Modularity | 10 | |
| Security & Self-Custody | 10 | |
| UI/UX & Design System | 10 | |
| GitOps & Release Hygiene | 6 | |

**Total Score** | **66** | **Your Total** |

**Px Standard Threshold**: ≥ 85/100 with **no 0-point failures** in critical areas (especially Strategic Alignment and Security).

**Status**:
- **≥ 85 + no critical gaps** → Ready for merge/release (Px Standard)
- **70–84** → Needs targeted improvements before merge
- **< 70** → Major gaps — do not merge until addressed

---

## Notes & Continuous Improvement

- This scorecard is intentionally strict. Our goal is not to slow down shipping, but to ensure that what we ship is **excellent and educational**.
- Low scores in any category should trigger a follow-up task or issue rather than shame.
- As we complete more standards documents (documentation rules, monorepo wiring, etc.), this scorecard will be updated.
- Feedback on the scorecard itself is welcome via the `standards-proposal` issue template.

**Current Version**: v0.1 — Created during the initial codex build-out (July 2026). Will evolve with PxPackages unification and beta portal learnings.

---

*Use this scorecard. Improve it. Hold the entire Pixel Journey ecosystem to the highest possible standard.*

**Px Standards — Quality Gates**