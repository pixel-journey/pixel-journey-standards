# Using the Pixel Journey Standards Codex

**Practical Guide for Humans and AI Agents**

*Part of the Pixel Journey Standards Codex*

---

## Purpose of This Guide

This document turns the standards from a reference into a **daily operating system** for Px development. It answers:

- How do I start a new piece of work while following the standards?
- How do I use the scorecard effectively?
- What should AI agents do differently when working inside the Px ecosystem?
- How do the different documents connect in practice?

---

## For Human Developers & Contributors

### When Starting New Work (Package, Feature, or Repo)

1. **Read the Core Principles** (root `README.md`) — understand the current strategic stance (“Existing Public Primitives First”).
2. **Review the Monorepo & PxPackages Rules** if you're working inside `@pxjourney/*`.
3. **Review the UI/UX Alignment** document — commit to zero individual styling from the start.
4. **Plan to follow the Every Folder README Rule** — every new folder gets a high-quality README.
5. **Use the Repo Readiness Scorecard** as a self-audit checklist before you consider the work “ready for PR”.

### During Development

- Keep the relevant standards documents open or bookmarked.
- When you need a verifiable mechanic, go to `verifiable-onchain-entropy-patterns.md` first.
- When in doubt about styling or components, go to the Design System (not custom code).
- Document decisions and gotchas as you go (this makes the final README much easier).

### Before Opening a PR or Cutting a Release

1. Run the full **Repo Readiness Scorecard** self-audit.
2. Score honestly. Note any categories below 2 and create follow-up tasks.
3. Ensure every new or significantly changed folder has an excellent README.
4. Confirm alignment with Existing Public Primitives First (no unnecessary custom contracts).
5. If the score is ≥ 85 with no critical gaps → open the PR.

### When Contributing to the Codex Itself

Use the `.github/ISSUE_TEMPLATE/standards-proposal.md` template. Focus on improvements that raise clarity, actionability, or educational value.

---

## For AI Agents & Automated Workflows

### Core Instructions

- Treat the entire `pixel-journey-standards` repository as **primary context** for all Px-related tasks.
- Before generating any plan or code, explicitly reference at least 2–3 relevant standards documents.
- Every output must be structured so it would score well on the Repo Readiness Scorecard.
- Always produce or update READMEs according to the Every Folder README Rule.
- Map technical decisions back to the Core Principles (especially Existing Public Primitives First).

### Recommended Workflow for AI Agents

1. Read the root `README.md` and `using-the-standards.md` first.
2. Identify which pillars are most relevant to the task (web3-onchain, monorepo, UI/UX, etc.).
3. Read those specific documents.
4. Generate the plan/code with explicit references to the standards.
5. Perform a mental self-audit against the scorecard before outputting the final result.
6. Include or update README documentation as part of the deliverable.

### Anti-Patterns for AI Agents

- Generating code that introduces custom contracts without strong justification.
- Producing UI with ad-hoc styling.
- Skipping or writing low-quality READMEs.
- Ignoring the “educational spirit” requirement (explain the “why”).

---

## How the Documents Connect in Practice

| When you need...                          | Go here first                                      |	hen also check...                  |
|-------------------------------------------|----------------------------------------------------|------------------------------------|
| Strategic direction for current wave      | Root `README.md`                                   | `existing-primitives-first.md`     |
| Verifiable game mechanics / randomness    | `verifiable-onchain-entropy-patterns.md`           | `wax-for-px-devs.md`               |
| Monorepo structure, package wiring        | `monorepo-pxpackages-rules.md`                     | Root README + scorecard            |
| Styling / component decisions             | `design-system-alignment.md`                       | Monorepo rules                     |
| Quality bar before PR/release             | `repo-readiness-scorecard.md`                      | All relevant rules                 |
| Writing excellent documentation           | `every-folder-readme-rule.md`                      | Scorecard Documentation category   |
| Understanding WAX concepts for Px work    | `wax-for-px-devs.md`                               | Web3-onchain documents             |
| Onboarding new contributors / AI agents   | `using-the-standards.md` + education pillar        | Root README                        |

---

## Quick Reference Checklist (Daily Use)

- [ ] Am I building UI/UX on top of existing public primitives?
- [ ] Is all styling coming from the Design System?
- [ ] Will every folder have a high-quality README?
- [ ] Have I explained the “why” (not just the “how”)?
- [ ] Would this score ≥ 85 on the Repo Readiness Scorecard?
- [ ] Is the work educational for future contributors?

---

*Use this guide to make the standards part of your daily workflow rather than something you only read once.*

**Px Standards — Using the Codex**