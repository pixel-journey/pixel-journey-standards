# Px Documentation Standards

**Comprehensive Guidelines for High-Quality Documentation Across Pixel Journey**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

Good documentation is one of the highest-leverage activities we can do. It improves developer experience, reduces support burden, helps onboard new contributors (human and AI), and increases the long-term value of our work.

This document expands on the basic **Every Folder README Rule** and sets broader expectations for documentation quality across the ecosystem.

---

## Core Principles

1. **Documentation is Part of the Work** — Not an afterthought.
2. **Write for the Next Person** — Assume the reader is intelligent but unfamiliar with the specific code.
3. **Be Clear and Scannable** — Use structure, headings, bullet points, and examples.
4. **Keep It Up to Date** — Outdated documentation is often worse than no documentation.
5. **Educational Spirit** — Good documentation teaches, not just describes.

---

## Required Documentation

### Every Folder
- Must have a `README.md` (see `every-folder-readme-rule.md` for the minimum structure).

### Every Public Package / Template
- High-quality root `README.md`
- Clear installation and usage instructions
- Architecture / design decisions explanation
- Customization and extension guide
- Links to relevant standards and related packages

### Breaking Changes & Releases
- Clear changelog entries (following Versioning and Release Standards)
- Migration guides when needed

---

## Recommended Documentation

### Architecture Decision Records (ADRs)
For significant architectural decisions, consider creating lightweight ADRs in a `docs/decisions/` folder. This helps future contributors understand *why* things were done a certain way.

### API / Public Interface Documentation
For packages with public APIs:
- Use TypeScript types + JSDoc comments for exported functions and components.
- Consider generating API documentation if the surface is large.

### In-Code Documentation
- Comment *why*, not *what* (the code should be readable).
- Explain complex algorithms, business rules, or non-obvious trade-offs.
- Document workarounds and known limitations.

### Examples
- Include realistic usage examples in READMEs and docs.
- For complex features, provide small, focused example projects or code snippets.

---

## Documentation for Different Audiences

| Audience              | What They Need                                      | Recommended Formats             |
|-----------------------|-----------------------------------------------------|---------------------------------|
| New developers        | Getting started, clear examples, mental model       | README, Getting Started guide   |
| Experienced developers| Architecture, extension points, edge cases          | Architecture docs, ADRs         |
| AI Agents             | Clear structure, explicit rules, examples           | Well-structured READMEs + types |
| End users             | What the feature does and how to use it             | In-app copy, user-facing docs   |

---

## Tools & Formats

- Markdown is preferred for most documentation.
- Use consistent heading structure across documents.
- Consider lightweight tools like Mintlify, Nextra, or GitBook when maintaining larger documentation sites.
- Keep diagrams simple and version-controlled (Mermaid is encouraged).

---

## Quality Bar

AAA-tier documentation in Px means:
- Documentation is clear, accurate, and up to date
- New contributors (human or AI) can get productive quickly
- The “why” behind decisions is explained
- Documentation reduces friction instead of creating it
- Future maintainers thank you for writing it

---

## How This Connects to Other Standards

- **Every Folder README Rule**: The baseline requirement.
- **Template Contribution Standards**: Templates must include excellent documentation.
- **Versioning and Release Standards**: Releases should be accompanied by good changelogs and migration guides.

---

*This document raises the overall standard for documentation quality across Px work.*

**Px Standards — Documentation Standards**