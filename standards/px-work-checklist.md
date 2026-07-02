# Px Work Checklist

**Daily Reference for Starting New Work, Refactors, and PRs**

*Part of the Pixel Journey Standards Codex — Keep this open while working.*

---

## When Starting New Work (Package, Feature, Major Refactor, or Blueprint)

### Strategic Alignment
- [ ] Does this work primarily deliver **UI/UX, client-side logic, or developer tooling** on top of existing public primitives?
- [ ] Have I reviewed `existing-primitives-first.md` and confirmed alignment with the current-era strategy?
- [ ] If creating or updating a template or educational blueprint, have I reviewed the `scaffolds-and-boilerplates/` and `educational-blueprints/` standards?

### Monorepo & Package Hygiene
- [ ] Will this package expose a **clean public API** with no internal implementation leakage?
- [ ] Am I committing to **zero individual styling** (all visuals via Design System)?
- [ ] Have I reviewed `monorepo-pxpackages-rules.md`?

### UI/UX
- [ ] Will all styling, components, tokens, and animations come from the Design System?
- [ ] Have I reviewed the relevant documents in `ui-ux-design/`?
- [ ] Does the work respect the retro pixel / glassmorphic / CRT aesthetic?

### Documentation
- [ ] Will every new or significantly changed folder have a high-quality README following the documentation standards?
- [ ] Have I reviewed `documentation-standards.md` and `every-folder-readme-rule.md`?

### Testing & Quality
- [ ] Have I considered appropriate testing coverage (see `testing-standards.md`)?
- [ ] Will I run the full **Repo Readiness Scorecard** self-audit before considering this work ready?
- [ ] Target: ≥ 85/100 with no critical gaps.

### Versioning & Releases
- [ ] Am I following proper versioning and changelog practices (see `versioning-and-release-standards.md`)?

---

## During Development

- [ ] When implementing verifiable mechanics, am I using the TX + block header entropy pattern?
- [ ] Am I explaining the "why" (not just the "how") in comments and documentation?
- [ ] Am I using WharfKit exclusively for wallet interactions?
- [ ] Is all data coming from Hyperion / public indexers + local-first state where appropriate?
- [ ] Am I composing Design System components instead of building custom styled ones?
- [ ] Am I following good observability and error tracking practices (see `observability-standards.md`)?
- [ ] Am I following appropriate security review practices for sensitive changes (see `security-review-and-hardening-standards.md`)?

---

## Before Opening a PR or Release

### Self-Audit
- [ ] Completed full **Repo Readiness Scorecard**
- [ ] Honest scoring with notes on any category below 2
- [ ] All new/changed folders have excellent READMEs
- [ ] No ad-hoc styling or unnecessary custom contracts
- [ ] Educational value is present

### Final Checks
- [ ] Score is ≥ 85 with no critical gaps → ready for PR
- [ ] If below threshold, created clear follow-up tasks
- [ ] PR description references relevant standards documents and scorecard results

---

## For AI Agents (Additional Rules)

- [ ] I have referenced at least 2–3 specific standards documents in my reasoning.
- [ ] My output is structured to score well on the Repo Readiness Scorecard.
- [ ] I am producing or updating READMEs according to the documentation standards.
- [ ] I am mapping decisions back to the Core Principles.
- [ ] When working on templates or educational blueprints, I have referenced the relevant scaffolds and educational-blueprints standards.

---

## Quick Reference — Most Used Documents

| Need                                      | Primary Document(s)                                      |
|-------------------------------------------|----------------------------------------------------------|
| Strategic direction                       | Root `README.md` + `existing-primitives-first.md`        |
| Verifiable mechanics                      | `verifiable-onchain-entropy-patterns.md`                 |
| UI/UX & Design System                     | `ui-ux-design/` pillar                                   |
| Monorepo / package structure              | `monorepo-pxpackages-rules.md`                           |
| Documentation quality                     | `documentation-standards.md` + `every-folder-readme-rule.md` |
| Testing                                   | `testing-standards.md`                                   |
| Versioning & Releases                     | `versioning-and-release-standards.md`                    |
| Observability                             | `observability-standards.md`                             |
| Security Review                           | `security-review-and-hardening-standards.md`             |
| Templates & Scaffolds                     | `scaffolds-and-boilerplate/` section                     |
| Educational Blueprints                    | `educational-blueprints/educational-blueprint-quality-standards.md` |
| Overall quality bar                       | `repo-readiness-scorecard.md`                            |
| How to use everything together            | `using-the-standards.md`                                 |

---

## Daily Mindset

> "Is this work excellent, educational, aligned with our current strategy, and built to last?"

If the answer is clearly yes across the board, we are shipping Px Standard work.

---

*Print this, bookmark it, or keep it open in your editor. It is designed to be used constantly.*

**Px Standards — Px Work Checklist**