# Monorepo PxPackages Rules

**Rules for Package Structure, Interaction, and Hygiene in the Pixel Journey Monorepo**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

As we unify our packages under `@pxjourney/*`, we need clear rules to maintain consistency, reduce coupling, and ensure packages remain maintainable and composable.

These rules apply to all packages in the Px monorepo.

---

## Core Principles

1. **Public API First** — Every package should expose a clean, well-documented public API. Internal implementation details should not leak.
2. **Loose Coupling** — Packages should interact through well-defined interfaces rather than direct internal imports.
3. **Single Responsibility** — Each package should have a clear, focused purpose.
4. **Composability** — Packages should be easy to use together.
5. **Documentation & Education** — Packages should be easy to understand and extend.

---

## Package Interaction Rules

- Do **not** import from another package's internal folders (e.g., `src/internal`, `src/lib/private`).
- Use the public exports defined in each package's main entry point.
- When two packages need to share logic, consider extracting it into a new shared package or using a well-defined interface.
- Avoid circular dependencies between packages.

---

## Package Structure Expectations

See the [Recommended Template Structure](../scaffolds-and-boilerplates/recommended-template-structure.md) for a suggested folder layout.

Every package should have:
- Clear public API surface
- Good TypeScript types
- High-quality root `README.md`
- Proper testing coverage for important functionality (see [Testing Standards](testing-standards.md))
- Clear versioning and changelog practices (see [Versioning and Release Standards](versioning-and-release-standards.md))

---

## Documentation Requirements

Every package must follow the [Every Folder README Rule](../documentation/every-folder-readme-rule.md) and the broader [Documentation Standards](../documentation/documentation-standards.md).

---

## When to Create a New Package

Create a new package when:
- The functionality is reusable across multiple dApps or other packages.
- It has a clear, focused responsibility.
- It would benefit from independent versioning and releases.

Avoid creating new packages for:
- One-off features specific to a single dApp
- Very small utilities that don't justify the overhead

See the decision matrix and contribution standards in the `scaffolds-and-boilerplates/` section for more guidance.

---

## Quality Expectations

All packages should aim to score well on the Repo Readiness Scorecard, especially in areas of:
- Code quality and maintainability
- Documentation quality
- Testing coverage for critical paths
- Adherence to UI/UX standards (when applicable)

---

## Related Standards

- [Testing Standards](testing-standards.md)
- [Versioning and Release Standards](versioning-and-release-standards.md)
- [Documentation Standards](../documentation/documentation-standards.md)
- [Scaffolds & Boilerplates Standards](../scaffolds-and-boilerplates/)

---

*These rules help keep the Px monorepo healthy, composable, and aligned with our overall standards.*

**Px Standards — Monorepo PxPackages Rules**