# AI Agent Self-Audit Checklist

**Use this before finalizing any significant output for Px work.**

*Part of the Pixel Journey Standards Codex — Helps AI agents produce high-quality, standards-aligned work.*

---

## Strategic Alignment

- [ ] I have referenced the Core Principles (especially **Existing Public Primitives First**)
- [ ] This work primarily delivers UI/UX, client-side logic, or developer tooling on top of existing public contracts/indexers
- [ ] I have avoided introducing custom smart contracts without strong justification meeting the high bar

## Code Quality

- [ ] Code is strict TypeScript with good type coverage
- [ ] No ad-hoc styling — all visuals use Design System tokens and components
- [ ] Follows recommended patterns (Hyperion + WharfKit, TanStack Query + Zustand, error handling, etc.)
- [ ] Clean, modular, and well-commented where non-obvious

## Documentation

- [ ] All new or significantly changed folders include high-quality READMEs (following the documentation rule and template)
- [ ] Key decisions, rationale, and gotchas are documented
- [ ] The work is educational for future contributors (explains the "why")

## Quality Gate

- [ ] I have mentally run (or will run) the **Repo Readiness Scorecard**
- [ ] Target: ≥ 85/100 with no critical gaps
- [ ] Any low-scoring areas have clear follow-up tasks noted

## Security & Self-Custody (if relevant)

- [ ] Sensitive data stays client-side
- [ ] Encryption / vault patterns are followed where appropriate
- [ ] No private keys or seeds are exposed

## Final Check

- [ ] Output maps back to at least 2–3 specific standards documents
- [ ] Work aligns with monorepo and package rules (if applicable)
- [ ] The result would be considered "Px Standard" work

---

*Use this checklist on every significant generation or refactor. It helps maintain high standards consistently.*

**Px Standards — AI Agent Self-Audit Checklist**