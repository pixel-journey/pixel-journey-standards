# New Package / Project Scaffold Checklist

**Use this when starting a new @pxjourney/* package or major Px project.**

*Part of the Pixel Journey Standards Codex — Helps you start on the right foot.*

---

## Before You Start

- [ ] Reviewed the Core Principles in the root `README.md`
- [ ] Reviewed `existing-primitives-first.md` (understand the current strategic stance)
- [ ] Reviewed `monorepo-pxpackages-rules.md` (if this is a shared package)
- [ ] Reviewed `design-system-alignment.md` (UI/UX expectations)

## Structural Decisions

- [ ] Decided on clear public API surface (no internal implementation leakage)
- [ ] Planned how this package will interact with other `@pxjourney/*` packages (clean hooks / context, not direct internal imports)
- [ ] Confirmed this should be a new package vs extending an existing one (see decision matrix in monorepo rules)

## Documentation Plan

- [ ] Will create a high-quality root README using the `new-readme-template.md`
- [ ] Will follow the `every-folder-readme-rule.md` for all subfolders
- [ ] Planned where to document key decisions and gotchas

## Quality & Process

- [ ] Will use the `repo-readiness-scorecard.md` as a self-audit before first PR
- [ ] Will follow conventional commits and reference relevant standards in PRs
- [ ] Will use the PR Description Template

## Technical Stack Alignment

- [ ] Will use WharfKit for all wallet interactions
- [ ] Will use Hyperion as primary data source (with TanStack Query caching)
- [ ] Will use TanStack Query + Zustand for state management (per recommended patterns)
- [ ] Will use Design System for all visual components and styling
- [ ] Will follow error handling, loading states, and optimistic UI patterns

## Security & Self-Custody (if applicable)

- [ ] Sensitive operations stay client-side
- [ ] Encrypted local storage / vault patterns considered where relevant
- [ ] Auto-sign is opt-in and clearly communicated

## Final Check

- [ ] This work aligns with **Existing Public Primitives First**
- [ ] This work will be educational for future contributors
- [ ] I am ready to run the full Repo Readiness Scorecard before significant PRs

---

*Print or copy this checklist when starting new work. It helps ensure new packages and projects begin aligned with Px Standards.*

**Px Standards — New Package Scaffold Checklist**