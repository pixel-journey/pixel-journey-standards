# Px Standards at a Glance

**Quick Reference for Daily Use Across the Pixel Journey Ecosystem**

*Part of the Pixel Journey Standards Codex*

---

## Core Principles (Current Era)

1. **Existing Public Primitives First** — Build excellent UI/UX and client-side systems on top of public WAX/Antelope infrastructure.
2. **Client-Side State & Local-First** — Use Hyperion + encrypted local storage as the source of truth.
3. **On-Chain Entropy** — Use TX hash + block header derivation for verifiable mechanics.

Future custom `pixel-journey` contracts must meet a very high bar.

---

## Most Used Documents

| Need                                | Primary Document(s)                                              |
|-------------------------------------|------------------------------------------------------------------|
| Strategic direction                 | Root `README.md` + `existing-primitives-first.md`                |
| Verifiable mechanics                | `verifiable-onchain-entropy-patterns.md`                         |
| Hyperion + WharfKit patterns        | `recommended-hyperion-wharfkit-patterns.md`                      |
| State management                    | `recommended-state-management-patterns.md`                       |
| Error handling & optimistic UI      | `recommended-error-handling-patterns.md`                         |
| UI/UX philosophy & quality bar      | `ui-ux-design/visual-language-aesthetic-guidelines.md`           |
| Component usage                     | `ui-ux-design/component-usage-standards.md`                      |
| Motion & haptics                    | `ui-ux-design/motion-animation-haptics-standards.md`             |
| Forms & validation                  | `ui-ux-design/form-input-validation-patterns.md`                 |
| Empty / Loading / Error states      | `ui-ux-design/empty-loading-error-state-standards.md`            |
| Accessibility baseline              | `ui-ux-design/accessibility-inclusive-design-baseline.md`        |
| Data visualization & grids          | `ui-ux-design/data-visualization-grid-standards.md`              |
| Responsive / Context adaptation     | `ui-ux-design/responsive-context-standards.md`                   |
| Monorepo & package rules            | `engineering/monorepo-pxpackages-rules.md`                       |
| Documentation quality               | `documentation/every-folder-readme-rule.md`                      |
| Quality gate                        | `quality-gates/repo-readiness-scorecard.md`                      |
| Daily checklist                     | `px-work-checklist.md`                                           |
| AI agent workflow                   | `ai-agent-workflow-guide.md`                                     |

---

## Before Any PR or Release

- Run the **Repo Readiness Scorecard** (target ≥ 85/100, no critical gaps)
- Use the **Px Work Checklist**
- Ensure all new/changed folders have high-quality READMEs
- Reference relevant standards in the PR description

---

## Quick Quality Bar

**Px Standard work** means:
- Aligns with Existing Public Primitives First
- Uses the Design System (no individual styling)
- Follows recommended patterns (state, error handling, verifiable mechanics, etc.)
- Has excellent documentation
- Scores ≥ 85 on the Repo Readiness Scorecard
- Is educational for future contributors

---

## Most Important Mindset

> "Is this work excellent, educational, aligned with our current strategy, and built to last?"

If the answer is clearly yes across the board, we are shipping Px Standard work.

---

*Keep this open while working. It is designed to be used constantly.*

**Px Standards — At a Glance**