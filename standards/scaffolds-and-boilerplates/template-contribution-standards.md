# Template Contribution Standards

**What Makes a High-Quality Template or Scaffold Contribution to the Pixel Journey Templates Repository**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

This document defines the expectations for anyone contributing new templates, improving existing ones, or submitting pull requests to the `pixel-journey-templates` repository. It ensures that contributions maintain a high bar of quality, educational value, and alignment with Pixel Journey standards.

---

## General Contribution Principles

All template contributions should:

- Follow the **Standards for Templates and Scaffolds** document.
- Prioritize clarity, maintainability, and educational value over clever abstractions.
- Make it easy for developers to build standards-compliant Px applications.
- Be well-documented and easy to understand.

---

## Requirements for New Templates

Before submitting a new template, contributors should ensure:

- The template solves a real, recurring need in the Px ecosystem.
- It demonstrates best practices from the standards codex (especially UI/UX, state management, error handling, and Existing Public Primitives First).
- It includes a high-quality `README.md` following the standards template guidelines.
- It contains clear architectural explanations and customization guidance.
- It has been tested with a realistic use case.
- It aligns with the Px visual language and brand voice where UI is involved.

---

## Code Quality Expectations

- Strict TypeScript with good type coverage.
- Use of recommended patterns (TanStack Query + Zustand, proper error handling, etc.).
- No individual styling — all UI must go through the Design System.
- Clean, modular structure that is easy to extend.
- No unnecessary dependencies.
- Good separation of concerns.

---

## Documentation Requirements

Every template should have:

- Excellent root `README.md`
- Clear "Getting Started" instructions
- Architecture overview
- How to customize / extend the template while staying standards-compliant
- Links to relevant standards documents
- Examples of common customizations

---

## AI Prompt Expectations (if included)

If a template includes AI prompts:
- They should follow the spirit of the AI Agent Workflow Guide.
- Prompts should be well-structured and effective.
- Consider contributing high-quality prompts to the shared `ai-prompts/` folder.

---

## Pull Request Quality

Good template PRs usually include:
- Clear description of what the template does and why it exists.
- Explanation of how it aligns with Px standards.
- Screenshots or demo links (for UI-related templates).
- Notes on what was intentionally kept simple vs. what can be extended.

---

## Review Criteria

When reviewing template contributions, maintainers should check:
- Does it follow the Standards for Templates and Scaffolds?
- Is it educational and well-documented?
- Does it make it easy to build high-quality Px applications?
- Is the code clean and maintainable?
- Does it respect the Px aesthetic and philosophy?

---

*This document helps maintain a consistently high quality bar for all contributions to the templates repository.*

**Px Standards — Template Contribution Standards**