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
| **wax-ecosystem-blueprint-catalog** | High-quality educational examples and patterns | Educational demonstrations of the standards              |

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

**Recommended flow**: Standards define the *rule*. Design System provides the *tool*.

### 2. pixel-journey-templates

**Standards influence**:
- All templates and scaffolds must follow the **Standards for Templates and Scaffolds** and **Template Contribution Standards** (`scaffolds-and-boilerplates/`).
- Templates should demonstrate best practices from the codex.
- Templates should be educational and easy to extend while staying standards-compliant.

**Templates provide**:
- Concrete, production-ready boilerplates.
- Fast starting points that reduce friction.
- Real-world feedback that improves the standards.

### 3. wax-ecosystem-blueprint-catalog

**Standards influence**:
- All educational blueprints should follow the **Educational Blueprint Quality Standards** (`educational-blueprints/educational-blueprint-quality-standards.md`).
- Blueprints should demonstrate high-quality patterns from across the codex (especially UI/UX, Documentation, Testing, and Security standards).
- Blueprints should be clear, educational, and honest about trade-offs.

**Blueprint Catalog provides**:
- High-quality, real-world educational examples.
- Practical demonstrations of standards in action.
- Feedback loop that helps improve both blueprints and standards.

**Recommended flow**: Blueprints should be developed and reviewed against the Educational Blueprint Quality Standards. They serve as living examples that help developers understand how to apply the standards in practice.

---

## Recommended Workflows

### Starting a New Project

1. Start from `pixel-journey-templates` for a solid scaffold.
2. Reference relevant standards (especially UI/UX and patterns).
3. Look at examples in `wax-ecosystem-blueprint-catalog` for inspiration on how to apply standards in realistic scenarios.

### Creating or Reviewing a Blueprint

- Follow the **Educational Blueprint Quality Standards**.
- Ensure strong alignment with UI/UX, Documentation, and core engineering standards.
- Focus on clarity and educational value.

---

## Governance & Evolution

Changes to core standards should be reflected in both templates and educational blueprints over time. Feedback from blueprint usage should flow back into standards improvements.

---

*This integration view helps keep the entire Px development ecosystem coherent and mutually reinforcing.*

**Px Standards — Ecosystem Integration**