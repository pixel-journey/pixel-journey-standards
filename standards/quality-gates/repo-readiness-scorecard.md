# Repo Readiness Scorecard

**Quality Gate for Packages, Templates, and dApps**

*Part of the Pixel Journey Standards Codex*

---

## How to Use This Scorecard

Before opening a PR or releasing significant work, honestly score your repo/package against these criteria.

**Target**: ≥ 85/100 with no critical (0-point) gaps.

---

## Scoring Guide

- **3** = Excellent / Fully meets the standard
- **2** = Good / Mostly meets the standard with minor gaps
- **1** = Partial / Significant room for improvement
- **0** = Missing or critically insufficient (blocks release)

---

## 1. Strategy & Architecture (Max 15)

| Criterion | Score (0-3) | Notes |
|-----------|-------------|-------|
| Alignment with Existing Public Primitives First |   | |
| Clear architecture and data flow |   | |
| Avoidance of unnecessary custom contracts |   | |
| Use of recommended patterns (state, error handling, entropy, etc.) |   | |
| **Subtotal** | **/15** | |

## 2. Code Quality & Maintainability (Max 15)

| Criterion | Score (0-3) | Notes |
|-----------|-------------|-------|
| Strict TypeScript + good type coverage |   | |
| Clean, modular, readable code |   | |
| Proper separation of concerns |   | |
| Minimal unnecessary dependencies |   | |
| **Subtotal** | **/15** | |

## 3. Testing (Max 15)

| Criterion | Score (0-3) | Notes |
|-----------|-------------|-------|
| Critical paths have meaningful test coverage |   | |
| Tests are maintainable and reasonably fast |   | |
| Good coverage of error paths and edge cases |   | |
| Integration / E2E tests for key user flows (where applicable) |   | |
| **Subtotal** | **/15** | |

See [Testing Standards](../engineering/testing-standards.md) for detailed expectations.

## 4. Documentation (Max 15)

| Criterion | Score (0-3) | Notes |
|-----------|-------------|-------|
| High-quality READMEs in all meaningful folders |   | |
| Clear architecture and usage documentation |   | |
| Good in-code comments and JSDoc where helpful |   | |
| Changelog / migration notes for releases (where applicable) |   | |
| **Subtotal** | **/15** | |

See [Documentation Standards](../documentation/documentation-standards.md) and [Every Folder README Rule](../documentation/every-folder-readme-rule.md).

## 5. UI/UX & Design System (Max 15)

| Criterion | Score (0-3) | Notes |
|-----------|-------------|-------|
| All styling goes through the Design System (no individual styling) |   | |
| Consistent use of components, tokens, and patterns |   | |
| Proper motion, haptics, and micro-interactions |   | |
| Good handling of loading, error, and empty states |   | |
| Accessibility considerations |   | |
| **Subtotal** | **/15** | |

See the full [UI/UX Design](../ui-ux-design/) pillar.

## 6. Versioning, Releases & Maintainability (Max 10)

| Criterion | Score (0-3) | Notes |
|-----------|-------------|-------|
| Follows Semantic Versioning correctly |   | |
| Clear changelogs with breaking changes highlighted |   | |
| Proper release process and tagging |   | |
| **Subtotal** | **/10** | |

See [Versioning and Release Standards](../engineering/versioning-and-release-standards.md).

## 7. Security & Self-Custody (Max 10)

| Criterion | Score (0-3) | Notes |
|-----------|-------------|-------|
| Sensitive operations stay client-side |   | |
| Proper encryption / vault patterns where relevant |   | |
| No private key or seed exposure |   | |
| Security review process followed for sensitive changes |   | |
| **Subtotal** | **/10** | |

See [Secure Vault Patterns](../engineering/recommended-secure-vault-patterns.md) and [Security Review & Hardening Standards](../engineering/security-review-and-hardening-standards.md).

## 8. Educational Value & Polish (Max 5)

| Criterion | Score (0-3) | Notes |
|-----------|-------------|-------|
| Code and documentation help others learn |   | |
| Overall polish and attention to detail |   | |
| **Subtotal** | **/5** | |

---

## Final Score

**Total Score**: ___ / 100

**Critical Gaps (any 0s)**: 

**Overall Assessment**:

- Ready for release / PR? 
- Major areas to improve before next release:

---

## How to Use This Scorecard

- Be honest. The goal is improvement, not perfection.
- Use this as a self-audit tool before PRs and releases.
- Share results in PR descriptions when relevant.
- Use low scores as a roadmap for improvement.

---

*This scorecard helps maintain a consistently high quality bar across Px work.*

**Px Standards — Repo Readiness Scorecard**