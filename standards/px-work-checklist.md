# Px Work Checklist

**Daily Reference for Starting New Work, Refactors, and PRs**

*Part of the Pixel Journey Standards Codex — Keep this open while working.*

---

## When Starting New Work (Package, Feature, Major Refactor)

### Strategic Alignment
- [ ] Does this work primarily deliver **UI/UX, client-side logic, or developer tooling** on top of existing public primitives?
- [ ] Have I reviewed `existing-primitives-first.md` and confirmed alignment with the current-era strategy?
- [ ] If any custom contract is being considered, does it clearly meet the high bar defined in `existing-primitives-first.md`?

### Monorepo & Package Hygiene (if inside @pxjourney/*)
- [ ] Will this package expose a **clean public API** with no internal implementation leakage?
- [ ] Am I committing to **zero individual styling** (all visuals via Design System)?
- [ ] Have I reviewed `monorepo-pxpackages-rules.md`?

### UI/UX
- [ ] Will all styling, components, tokens, and animations come from the Design System?
- [ ] Have I reviewed `design-system-alignment.md`?
- [ ] Does the work respect the retro pixel / glassmorphic / CRT aesthetic?

### Documentation
- [ ] Will every new or significantly changed folder have a high-quality README following the `every-folder-readme-rule.md`?
- [ ] Will the root/package README explain purpose, architecture, usage, pitfalls, and educational value?

### Quality Bar
- [ ] I will run the full **Repo Readiness Scorecard** self-audit before considering this work ready for PR.
- [ ] Target: ≥ 85/100 with no critical (0-point) gaps.

---

## During Development

- [ ] When implementing verifiable mechanics, am I using the TX + block header entropy pattern from `verifiable-onchain-entropy-patterns.md`?
- [ ] Am I explaining the "why" (not just the "how") in comments and documentation?
- [ ] Am I using WharfKit exclusively for wallet interactions?
- [ ] Is all data coming from Hyperion / public indexers + local-first state where appropriate?
- [ ] Am I composing Design System components instead of building custom styled ones?

---

## Before Opening a PR or Release

### Self-Audit
- [ ] Completed full **Repo Readiness Scorecard** (`repo-readiness-scorecard.md`)
- [ ] Honest scoring with notes on any category below 2
- [ ] All new/changed folders have excellent READMEs
- [ ] No ad-hoc styling or unnecessary custom contracts
- [ ] Educational value is present (future contributors will learn from this)

### Final Checks
- [ ] Score is ≥ 85 with no critical gaps → ready for PR
- [ ] If below threshold, created clear follow-up tasks
- [ ] PR description references relevant standards documents and scorecard results

---

## For AI Agents (Additional Rules)

- [ ] I have referenced at least 2–3 specific standards documents in my reasoning.
- [ ] My output is structured to score well on the Repo Readiness Scorecard.
- [ ] I am producing or updating READMEs according to the documentation rule.
- [ ] I am mapping decisions back to the Core Principles (especially Existing Public Primitives First).
- [ ] I am avoiding anti-patterns listed in `using-the-standards.md`.

---

## Quick Reference — Most Used Documents

| Need                                      | Primary Document(s)                                      |
|-------------------------------------------|----------------------------------------------------------|
| Strategic direction                       | Root `README.md` + `existing-primitives-first.md`        |
| Verifiable mechanics                      | `verifiable-onchain-entropy-patterns.md`                 |
| Monorepo / package structure              | `monorepo-pxpackages-rules.md`                           |
| Styling & components                      | `design-system-alignment.md`                             |
| Documentation quality                     | `every-folder-readme-rule.md`                            |
| Overall quality bar                       | `repo-readiness-scorecard.md`                            |
| How to use everything together            | `using-the-standards.md`                                 |
| WAX concepts for Px work                  | `wax-for-px-devs.md`                                     |

---

## Daily Mindset

> "Is this work excellent, educational, aligned with our current strategy, and built to last?"

If the answer is clearly yes across the board, we are shipping Px Standard work.

---

*Print this, bookmark it, or keep it open in your editor. It is designed to be used constantly, not read once.*

**Px Standards — Px Work Checklist**