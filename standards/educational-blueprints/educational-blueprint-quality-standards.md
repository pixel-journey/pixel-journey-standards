# Educational Blueprint Quality Standards

**What Makes a Blueprint "Px Perfect" — Standards for High-Quality Educational Examples in the WAX Ecosystem**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

The `wax-ecosystem-blueprint-catalog` exists to provide high-quality, educational, real-world examples that help developers build on WAX and Antelope. For these blueprints to be truly valuable, they must meet a high and consistent quality bar.

This document defines the **Educational Blueprint Quality Standards** — the criteria that make a blueprint "Px Perfect" from an educational and standards perspective. It serves as the authoritative reference that the blueprint catalog should align with.

---

## Core Philosophy

Educational blueprints should be:

- **Clear and Learnable** — A developer should be able to understand the architecture and key decisions quickly.
- **Production-Minded** — Not toy examples. They should reflect real patterns used in production Px dApps.
- **Standards-Aligned** — They should demonstrate best practices from the Pixel Journey Standards Codex.
- **Well-Documented** — Documentation should be excellent, not an afterthought.
- **Visually Consistent** — When UI is involved, it should follow the Px visual language and Design System.
- **Honest** — Show realistic trade-offs, limitations, and decision-making.

---

## Required Quality Criteria

Every educational blueprint should meet the following standards:

### 1. Alignment with Px Standards

- Follows the **Existing Public Primitives First** principle.
- Uses recommended patterns from the standards codex (state management, error handling, verifiable mechanics, etc.).
- Respects UI/UX standards when building interfaces (Design System, motion, component usage, accessibility, etc.).
- Follows documentation and versioning standards.

### 2. Educational Clarity

- Clear architecture overview and data flow explanation.
- Explains *why* certain decisions were made (not just *how*).
- Includes realistic usage examples and common customization paths.
- Highlights important patterns, anti-patterns, and gotchas.
- Uses clear, scannable documentation (good headings, bullet points, code examples).

### 3. Code Quality

- Clean, maintainable, and well-structured code.
- Proper TypeScript usage with good typing.
- Reasonable test coverage for critical paths (see Testing Standards).
- Follows the Recommended Template Structure and avoids common anti-patterns (see Scaffolds & Boilerplates section).

### 4. Documentation Quality

- Excellent root `README.md` following the standards template.
- Clear "Getting Started" and customization sections.
- Architecture Decision Records (ADRs) or equivalent explanations for significant choices.
- In-code comments that explain *why*, especially for non-obvious logic.

### 5. Visual & UX Consistency (when applicable)
- All UI follows the Px Design System and visual language.
- Proper handling of loading, error, and empty states.
- Consistent motion, haptics, and micro-interactions.
- Accessibility considerations are addressed.

### 6. Security & Self-Custody Awareness
- Demonstrates secure patterns (especially around keys, signing, and sensitive data).
- Clearly communicates security assumptions and best practices.

---

## What Educational Blueprints Should Avoid

- Overly simplistic or unrealistic examples that don't reflect real usage.
- Poor or missing documentation.
- Bypassing the Design System or Px UI/UX standards.
- Mixing too many patterns or creating confusing architecture.
- Hiding important complexity or trade-offs.
- Using outdated patterns that contradict current standards.

---

## Relationship to Other Standards

Educational blueprints should be viewed as **practical demonstrations** of the standards codex. They should reference and align with:

- UI/UX Design pillar
- Scaffolds & Boilerplates standards
- Documentation Standards
- Testing Standards
- Versioning and Release Standards
- Error Handling & Observability Standards
- Security patterns

---

## Governance

- New blueprints submitted to the catalog should be reviewed against these quality standards.
- Significant updates to existing blueprints should maintain or improve alignment.
- Feedback from blueprint usage should be used to improve both the blueprints and the standards themselves.

---

*This document defines the quality bar for educational blueprints and serves as the bridge between the standards codex and the blueprint catalog.*

**Px Standards — Educational Blueprint Quality Standards**