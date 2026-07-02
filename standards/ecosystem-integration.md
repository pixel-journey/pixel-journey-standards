# Px Standards Ecosystem Integration

**How the Standards Codex Connects to Design System, Templates, and Blueprint Catalog**

*Part of the Pixel Journey Standards Codex*

---

## Purpose of This Document

The Pixel Journey GitHub Organization has several interconnected repositories that together form a complete development ecosystem. This document clarifies how the **Standards Codex** relates to and reinforces the other core repos:

- `pixel-journey-design-system`
- `pixel-journey-templates`
- `wax-ecosystem-blueprint-catalog`

Understanding these connections helps us maintain consistency and maximize the value of all four repositories.

---

## The Four Pillars of the Px Development Ecosystem

| Repository                        | Primary Role                                      | Relationship to Standards Codex                          |
|-----------------------------------|---------------------------------------------------|----------------------------------------------------------|
| **pixel-journey-standards**       | Defines excellence, rules, patterns, and quality  | The "constitution" and operating system                |
| **pixel-journey-design-system**   | Visual language, components, tokens, retro aesthetic | The source of truth for all UI/UX implementation        |
| **pixel-journey-templates**       | Scaffolds and boilerplates for new work           | The starting point that should already follow standards  |
| **wax-ecosystem-blueprint-catalog** | Curated WAX/Antelope patterns and best practices | The broader ecosystem knowledge base that standards reference and extend |

---

## How the Standards Codex Interacts with Each Repo

### 1. pixel-journey-design-system

**Standards enforce**:
- Zero individual styling — all visual work must route through the Design System.
- Use of semantic tokens, variants, and primitives instead of raw Tailwind or custom CSS.
- Retro pixel / CRT / glassmorphic aesthetic as the default language.

**Design System provides**:
- The actual implementation (components, tokens, motion, haptics).
- Visual examples that standards can reference.

**Recommended flow**: Standards define the *rule*. Design System provides the *tool*. New UI work starts in the Design System when possible.

### 2. pixel-journey-templates

**Standards influence**:
- New package and project scaffolds should include high-quality READMEs from day one (using the standards template).
- Scaffolds should encourage (or enforce) use of the Repo Readiness Scorecard and relevant patterns.
- Templates should align with monorepo rules and Existing Public Primitives First philosophy.

**Templates provide**:
- Fast starting points that already follow many standards.
- Reduced friction for new contributors and AI agents.

**Recommended flow**: Start new work from Templates → apply Standards immediately.

### 3. wax-ecosystem-blueprint-catalog

**Standards reference**:
- WAX best practices and patterns documented in the catalog.
- Hyperion, AtomicAssets, Alcor, and WharfKit usage patterns.
- On-chain primitives that Px work builds upon.

**Standards extend**:
- The catalog with Px-specific patterns (verifiable entropy, PxWallet vault patterns, monorepo wiring, etc.).
- Educational framing tailored to Px development style.

**Recommended flow**: Use the Blueprint Catalog as the broader knowledge base. Standards provide the Px-specific lens and rules on top of it.

---

## Recommended Workflows

### Starting a New PxPackage or Feature

1. Start from `pixel-journey-templates` (best scaffold).
2. Immediately apply relevant sections from `pixel-journey-standards` (monorepo rules, documentation rule, UI/UX alignment).
3. Use components and tokens from `pixel-journey-design-system`.
4. Reference patterns from `wax-ecosystem-blueprint-catalog` where relevant.
5. Self-audit with the Repo Readiness Scorecard before first significant PR.

### Contributing to Any Px Repo

- Check the Standards Codex first for relevant rules or patterns.
- Follow the documentation and UI/UX rules.
- Use the PR template that references the scorecard.
- When in doubt, prefer composition of existing primitives (from Design System + Blueprint Catalog) over custom solutions.

---

## Governance & Evolution

Changes to the Standards Codex that affect the other three repos should be coordinated (especially UI/UX rules and monorepo patterns).

Major updates to Design System tokens/components or new templates should be reviewed against the current standards to maintain alignment.

---

*This integration view helps keep the entire Px development ecosystem coherent and mutually reinforcing.*

**Px Standards — Ecosystem Integration**