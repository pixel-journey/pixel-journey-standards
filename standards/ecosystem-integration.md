# Px Standards Ecosystem Integration

**How the Standards Codex Connects to Design System, Templates, and Blueprint Catalog**

*Part of the Pixel Journey Standards Codex*

---

## Purpose of This Document

The Pixel Journey GitHub Organization has several interconnected repositories that together form a complete development ecosystem. This document clarifies how the **Standards Codex** relates to and reinforces the other core repos:

- `pixel-journey-design-system`
- `pixel-journey-templates`
- `wax-ecosystem-blueprint-catalog`

Understanding these connections helps us maintain consistency and maximize the value of all repositories.

---

## The Four Pillars of the Px Development Ecosystem

| Repository                        | Primary Role                                      | Relationship to Standards Codex                          |
|-----------------------------------|---------------------------------------------------|----------------------------------------------------------|
| **pixel-journey-standards**       | Defines excellence, rules, patterns, and quality  | The "constitution" and operating system                |
| **pixel-journey-design-system**   | Visual language, components, tokens, retro aesthetic | The source of truth for all UI/UX implementation        |
| **pixel-journey-templates**       | Scaffolds and boilerplates for new work           | The practical implementation layer of the standards      |
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
- All templates and scaffolds must follow the **Standards for Templates and Scaffolds** (`scaffolds-and-boilerplates/standards-for-templates-and-scaffolds.md`).
- Template contributions should follow the **Template Contribution Standards** (`scaffolds-and-boilerplates/template-contribution-standards.md`).
- Templates should demonstrate best practices from the codex (UI/UX, state management, error handling, Existing Public Primitives First, etc.).
- Templates should be educational and make it easy to build standards-compliant applications.

**Templates provide**:
- Concrete, production-ready boilerplates that implement the standards.
- Fast starting points that reduce friction for new projects.
- Real-world feedback that can improve the standards over time.

**Recommended flow**: Start new work from Templates → apply Standards immediately. New template ideas should be guided by the scaffolds standards.

### 3. wax-ecosystem-blueprint-catalog

**Standards reference**:
- WAX best practices and patterns documented in the catalog.
- Hyperion, AtomicAssets, Alcor, and WharfKit usage patterns.
- On-chain primitives that Px work builds upon.

**Standards extend**:
- The catalog with Px-specific patterns (verifiable entropy, PxWallet vault patterns, monorepo wiring, UI/UX standards, etc.).
- Educational framing tailored to Px development style.

**Recommended flow**: Use the Blueprint Catalog as the broader knowledge base. Standards provide the Px-specific lens and rules on top of it.

---

## Recommended Workflows

### Starting a New PxPackage or Feature

1. Start from `pixel-journey-templates` (best scaffold).
2. Immediately apply relevant sections from `pixel-journey-standards` (especially UI/UX standards and monorepo rules).
3. Use components and tokens from `pixel-journey-design-system`.
4. Reference patterns from `wax-ecosystem-blueprint-catalog` where relevant.
5. Self-audit with the Repo Readiness Scorecard before first significant PR.

### Contributing to Any Px Repo

- Check the Standards Codex first for relevant rules or patterns.
- Follow the documentation and UI/UX rules.
- Use the PR template that references the scorecard.
- When in doubt, prefer composition of existing primitives (from Design System + Blueprint Catalog) over custom solutions.

### Contributing to Templates

- Follow the **Standards for Templates and Scaffolds** and **Template Contribution Standards** in the `scaffolds-and-boilerplates/` section.
- Ensure the template demonstrates high-quality, standards-aligned patterns.
- Include excellent documentation and educational value.

---

## Governance & Evolution

Changes to the Standards Codex that affect the templates repo should be coordinated. New patterns discovered while building templates should be proposed back into the standards repo.

Major updates to the Design System or new high-quality templates should be reviewed for alignment with current standards.

---

*This integration view helps keep the entire Px development ecosystem coherent and mutually reinforcing.*

**Px Standards — Ecosystem Integration**