# standards/

**The Living Heart of the Pixel Journey Standards Codex**

This folder contains the core standards, rules, patterns, and guidance that define excellence across the Pixel Journey ecosystem.

---

## How to Navigate This Section

The standards are organized into clear pillars. Start with the documents most relevant to your current work.

### Core Strategy & Principles
- `existing-primitives-first.md` — The pragmatic strategic stance for the current massive wave of Px Portal releases (UI/UX on top of existing public contracts).
- Root `README.md` (one level up) — Full vision, Core Architectural Principles, and overall codex overview.

### Concrete Implementation Patterns
- `web3-onchain/verifiable-onchain-entropy-patterns.md` — How to implement provably fair, verifiable game mechanics using only public TX + block header data (no custom contracts).
- `web3-onchain/existing-primitives-first.md` — Detailed decision framework and educational rationale.

### Quality & Excellence
- `quality-gates/repo-readiness-scorecard.md` — The practical  scoring system used before PRs and releases (target ≥ 85/100).
- `px-work-checklist.md` — Daily scannable checklist for starting new work, refactors, and PRs.

### Structural & Process Rules
- `engineering/monorepo-pxpackages-rules.md` — Rules for clean public APIs, package interaction, and monorepo hygiene during unification.
- `documentation/every-folder-readme-rule.md` — Mandatory high-quality README requirement for every folder (educational skeleton).
- `ui-ux-design/design-system-alignment.md` — Zero individual styling + pixel-perfect retro expectations.

### Engineering Foundations
- `engineering-overview.md` — TypeScript, refactoring discipline, AI-assisted development standards.
- `engineering/recommended-pxpackages-patterns.md` — Additional recommended patterns for PxPackages work.

### Education & Onboarding
- `education-onboarding/README.md` — Overview of the education pillar.
- `education-onboarding/wax-for-px-devs.md` — Focused WAX/Antelope concepts most relevant to current Px development.

### How to Use Everything
- `using-the-standards.md` — Practical guide for humans and AI agents on how to apply the codex in daily work.

---

## Quick Start Recommendations

**New to Px Standards?** Start here:
1. Root `README.md` (Core Principles)
2. `existing-primitives-first.md`
3. `using-the-standards.md`
4. `px-work-checklist.md`

**Working on PxPackages / Monorepo?** Prioritize:
- `monorepo-pxpackages-rules.md`
- `design-system-alignment.md`
- `every-folder-readme-rule.md`
- `repo-readiness-scorecard.md`

**Building Verifiable Game Mechanics?** Start with:
- `verifiable-onchain-entropy-patterns.md`
- `wax-for-px-devs.md`

**Before any PR or Release**:
- Run `repo-readiness-scorecard.md`
- Use `px-work-checklist.md`

---

## Contribution

Improvements to any document are welcome. Use the `standards-proposal` issue template (in `.github/ISSUE_TEMPLATE/`) when suggesting changes or new standards.

This section is designed to evolve alongside PxPackages unification, beta portals, and the broader ecosystem.

---

*Part of the Pixel Journey Standards Codex — Built to raise the bar for everyone.*
