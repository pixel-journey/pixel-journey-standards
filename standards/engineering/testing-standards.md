# Px Testing Standards

**Expectations for Testing in Pixel Journey Codebases**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

High-quality testing improves reliability, maintainability, and confidence in changes. While we value pragmatic development, we also expect a reasonable level of testing that scales with the complexity and risk of the code.

This document defines the testing expectations for Px work.

---

## Core Principles

1. **Test the Risky Parts** — Focus testing effort where bugs would be most painful (critical user flows, financial logic, security-sensitive code, complex state).
2. **Tests Should Be Maintainable** — Brittle or overly complex tests create more problems than they solve.
3. **Tests Should Be Fast** — Slow test suites discourage running them.
4. **Tests Should Be Readable** — Other developers (and AI agents) should be able to understand what is being tested and why.
5. **Prefer Integration + E2E for Critical Flows** — Unit tests are useful, but integration and end-to-end tests often provide higher confidence for user-facing behavior.

---

## Recommended Testing Pyramid for Px

- **Unit Tests** — For complex pure functions, utility libraries, and isolated logic.
- **Integration Tests** — For component behavior, hook logic, and service interactions (preferred over many shallow unit tests).
- **End-to-End / Playwright Tests** — For critical user flows (recommended for dApps and templates).
- **Visual / Screenshot Testing** — Useful for UI-heavy work (especially when using Design System components).
- **Contract / API Tests** — When integrating with external services or contracts.

We generally prefer fewer, high-value tests over high test coverage with low-value tests.

---

## What Should Be Tested

### Must Test
- Financial / token movement logic
- Authentication and wallet connection flows
- Critical state transitions (staking, voting, claiming, etc.)
- Error handling paths for important operations
- Security-sensitive utilities (encryption, key handling, signature verification)

### Should Test
- Complex custom hooks and state management logic
- Form validation and submission flows
- Data fetching and caching behavior
- Responsive behavior on key screens

### Nice to Have
- Simple presentational components (often covered well enough by visual testing or manual review)
- Very stable third-party integrations (unless the integration itself is risky)

---

## Testing Tools & Patterns

- Use **Vitest** or **Jest** for unit/integration tests.
- Use **Playwright** for end-to-end testing (recommended for dApps).
- Use **Storybook + Chromatic** or similar for visual regression testing when appropriate.
- Keep test files close to the code they test (co-location preferred).
- Use descriptive test names that explain the expected behavior.

---

## Documentation of Tests

- Complex test setups should be documented.
- Important test cases (especially security or financial ones) should be explained in code comments or architecture docs.
- When a test is intentionally skipped or marked as TODO, add a clear reason.

---

## Quality Bar

AAA-tier testing in Px means:
- Critical paths have meaningful test coverage
- Tests are fast, readable, and maintainable
- Testing effort is focused on risk rather than vanity metrics (e.g., code coverage percentage)
- New features include appropriate tests from the beginning
- Tests serve as living documentation of expected behavior

---

## How This Connects to Other Standards

- **Error Handling Patterns**: Tests should cover error paths.
- **UI/UX Standards**: Visual and interaction testing should align with component and motion standards.
- **Security Patterns**: Security-sensitive code requires stronger testing.

---

*This document sets a pragmatic but meaningful baseline for testing across Px work.*

**Px Standards — Testing Standards**