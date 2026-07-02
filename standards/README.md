# standards/

**The Living Heart of the Pixel Journey Standards Codex**

This folder contains the core standards, rules, patterns, and guidance that define excellence across the Pixel Journey ecosystem.

The codex is designed to be practical and actionable for both human developers and AI agents working on Px projects, templates, and educational blueprints.

---

## How to Navigate This Section

The standards are organized into clear pillars. Start with the documents most relevant to your current work.

### 1. Strategy & Direction
- Root `README.md` (one level up) — Core Principles and overall vision
- `web3-onchain/existing-primitives-first.md` — The pragmatic current-era strategy
- `web3-onchain/future-custom-contracts-decision-framework.md` — When and how custom contracts might make sense in the future

### 2. Concrete Implementation Patterns
- `web3-onchain/verifiable-onchain-entropy-patterns.md` — Provably fair randomness using TX + block headers
- `engineering/recommended-hyperion-wharfkit-patterns.md` — Data fetching and wallet interaction patterns
- `engineering/recommended-state-management-patterns.md` — TanStack Query + Zustand best practices
- `engineering/recommended-error-handling-patterns.md` — Loading, error, and optimistic UI patterns
- `engineering/recommended-secure-vault-patterns.md` — Self-custody and encryption patterns
- `engineering/recommended-performance-patterns.md` — Keeping Px dApps fast and efficient
- `engineering/testing-standards.md` — Testing expectations and pyramid
- `engineering/versioning-and-release-standards.md` — Semantic Versioning, changelogs, and release practices
- `engineering/observability-standards.md` — Privacy-respecting logging, error tracking, and monitoring
- `engineering/security-review-and-hardening-standards.md` — Security review processes and application hardening

### 3. Quality & Daily Tools
- `quality-gates/repo-readiness-scorecard.md` — The primary quality gate (target ≥ 85/100)
- `px-work-checklist.md` — Daily working checklist for new work and PRs
- `using-the-standards.md` — How humans and AI agents should apply the codex

### 4. Structural & Process Rules
- `engineering/monorepo-pxpackages-rules.md` — Monorepo and package hygiene rules
- `documentation/every-folder-readme-rule.md` — Mandatory high-quality README requirement

### 5. UI/UX Design (Very Strong Pillar)
- `ui-ux-design/design-system-alignment.md` — Zero individual styling + mandatory Design System usage
- `ui-ux-design/visual-language-aesthetic-guidelines.md` — Retro pixel + premium glassmorphic philosophy and quality bar
- `ui-ux-design/component-usage-standards.md` — Detailed component usage and composition rules
- `ui-ux-design/motion-animation-haptics-standards.md` — Animation, timing, micro-interactions, and haptics
- `ui-ux-design/form-input-validation-patterns.md` — Forms, inputs, validation, and submission flows
- `ui-ux-design/empty-loading-error-state-standards.md` — Empty, loading, and error state treatments
- `ui-ux-design/accessibility-inclusive-design-baseline.md` — Accessibility and inclusive design requirements
- `ui-ux-design/data-visualization-grid-standards.md` — Leaderboards, grids, analytics, and data displays
- `ui-ux-design/responsive-context-standards.md` — Adaptation across desktop, mobile, PWA, and Chrome Extensions

### 6. Marketing, Press & Graphics (Solid Pillar)
- `marketing-press-graphics/visual-asset-and-graphics-standards.md` — Graphics, illustrations, memes, and visual asset quality
- `marketing-press-graphics/brand-voice-and-messaging-standards.md` — Tone, language, storytelling, and communication principles
- `marketing-press-graphics/press-kit-and-media-standards.md` — Press kits, media assets, and external communications
- `marketing-press-graphics/ai-and-generated-content-guidelines.md` — Responsible use of AI for graphics, copy, and content
- `marketing-press-graphics/social-media-community-content-standards.md` — X posts, educational content, and community communications

### 7. Scaffolds & Boilerplates (Alignment with Templates Repo)
- `scaffolds-and-boilerplates/standards-for-templates-and-scaffolds.md` — Quality bar and expectations for the templates repository
- `scaffolds-and-boilerplates/template-contribution-standards.md` — What makes a high-quality template contribution
- `scaffolds-and-boilerplates/recommended-template-structure.md` — Suggested structure and organization for templates
- `scaffolds-and-boilerplates/common-template-anti-patterns.md` — Common mistakes to avoid when building templates

### 8. Educational Blueprints (Alignment with Blueprint Catalog)
- `educational-blueprints/educational-blueprint-quality-standards.md` — Quality bar for educational blueprints in the catalog

### 9. AI-Assisted Development
- `ai-agent-workflow-guide.md` — How to effectively use the codex with AI agents (includes guidance on using prompts from templates repo)
- `templates/ai-agent-self-audit-checklist.md` — Self-audit checklist for AI-generated work

### 10. Education & Onboarding
- `education-onboarding/README.md` — Education pillar overview
- `education-onboarding/wax-for-px-devs.md` — Focused WAX concepts for Px developers

### 11. Ecosystem & Integration
- `ecosystem-integration.md` — How Standards connect to Design System, Templates, and Blueprint Catalog
- `glossary.md` — Key terms used across the codex

### 12. Templates & Practical Tools
- `templates/new-readme-template.md` — Ready-to-use README template
- `templates/new-package-scaffold-checklist.md` — Checklist for starting new packages
- `.github/PULL_REQUEST_TEMPLATE.md` — PR template that references the standards

---

## Quick Start by Role

**New to Px Standards?** Start here:
1. Root `README.md`
2. `existing-primitives-first.md`
3. `using-the-standards.md`
4. `px-work-checklist.md`

**Working on PxPackages / Monorepo?** Prioritize:
- `monorepo-pxpackages-rules.md`
- `ui-ux-design/design-system-alignment.md`
- `documentation/every-folder-readme-rule.md`
- `repo-readiness-scorecard.md`

**Using AI Agents Heavily?** Prioritize:
- `ai-agent-workflow-guide.md`
- `templates/ai-agent-self-audit-checklist.md`
- `px-work-checklist.md`

**Focusing on UI/UX Quality?** Prioritize:
- `ui-ux-design/visual-language-aesthetic-guidelines.md`
- `ui-ux-design/component-usage-standards.md`
- `ui-ux-design/motion-animation-haptics-standards.md`

**Working on Marketing, Press, or Graphics?** Prioritize:
- `marketing-press-graphics/visual-asset-and-graphics-standards.md`
- `marketing-press-graphics/brand-voice-and-messaging-standards.md`
- `marketing-press-graphics/press-kit-and-media-standards.md`
- `marketing-press-graphics/social-media-community-content-standards.md`

**Working with Templates / Scaffolds?** Prioritize:
- `scaffolds-and-boilerplates/standards-for-templates-and-scaffolds.md`
- `scaffolds-and-boilerplates/template-contribution-standards.md`
- `scaffolds-and-boilerplates/recommended-template-structure.md`

**Working with Educational Blueprints?** Prioritize:
- `educational-blueprints/educational-blueprint-quality-standards.md`

**Before any PR or Release**:
- Run `repo-readiness-scorecard.md`
- Use `px-work-checklist.md`

---

## Contribution

Improvements are welcome. Use the `standards-proposal` issue template when suggesting changes. Focus on clarity, actionability, and educational value.

This section evolves alongside PxPackages, beta portals, and the broader ecosystem.

---

*Part of the Pixel Journey Standards Codex — Built to raise the bar for everyone.*
