# Standards for Templates and Scaffolds

**Rules, Quality Bar, and Expectations for the Pixel Journey Templates Repository**

*Part of the Pixel Journey Standards Codex*

---

## Purpose of This Document

The `pixel-journey-templates` repository contains production-ready boilerplates, scaffolds, and starter projects that help developers quickly build high-quality Px dApps and packages.

This document defines the **standards, principles, and quality expectations** that all templates and scaffolds in that repository must follow. It creates clear alignment between the two repos.

---

## Core Principles for All Templates & Scaffolds

All templates and scaffolds must adhere to the following:

### 1. Standards-First Design
- Every template must be built to comply with the current Pixel Journey Standards Codex (especially UI/UX, monorepo rules, and Existing Public Primitives First).
- Templates should make it *easy* to do the right thing and *hard* to do the wrong thing.

### 2. Educational Value
- Templates should be excellent learning resources, not just working code.
- Include clear comments, READMEs, and architectural explanations.
- Follow the spirit of the "Every Folder README Rule".

### 3. Production-Ready Quality
- Templates should be close to production quality (not toy examples).
- They must pass a high bar on the Repo Readiness Scorecard concepts (even if not using the full scorecard).
- Security, performance, and maintainability matter.

### 4. Consistency with Px Aesthetic & Philosophy
- UI templates should respect the retro pixel + premium glassmorphic visual language.
- All templates should feel like they belong in the Pixel Journey ecosystem.

### 5. Minimal but Extensible
- Start lean but make it easy to extend and customize following Px patterns.
- Avoid over-engineering for every possible use case.

---

## Required Elements for Every Template

Every template/scaffold should include:

- High-quality root `README.md` (following the standards template style)
- Clear explanation of what the template is for and who it's for
- Architecture / data flow overview
- Instructions on how to customize and extend it while staying standards-compliant
- Links to relevant standards documents
- At least one example of a realistic feature implementation

## Recommended Elements

- Use of the official Design System from day one
- Example of proper state management (TanStack Query + Zustand)
- Example of error handling, loading, and empty states
- Example of verifiable mechanics (if relevant)
- Good AI agent prompt examples in `ai-prompts/` (where helpful)

---

## What Templates Should *Not* Do

- Introduce custom smart contracts without very strong justification
- Use individual/ad-hoc styling instead of the Design System
- Ignore the Existing Public Primitives First principle
- Create overly complex abstractions that make simple things hard
- Deviate significantly from Px brand voice and visual language

---

## Relationship Between the Two Repos

| Repository                    | Primary Focus                          | Relationship to the Other |
|-------------------------------|----------------------------------------|---------------------------|
| `pixel-journey-standards`     | Principles, rules, quality bar, patterns | Defines the "why" and "what good looks like" |
| `pixel-journey-templates`     | Concrete boilerplates and starters     | Implements the standards in practical form |

Changes to core standards should be reflected in templates over time. New patterns discovered while building templates should be proposed back into the standards repo.

---

## Governance

- Major new templates or significant changes to existing ones should be reviewed against this document.
- The standards repo acts as the source of truth for quality expectations.
- Feedback from template usage should flow back into standards improvements.

---

*This document creates a clear contract between the standards codex and the templates repository.*

**Px Standards — Standards for Templates and Scaffolds**
