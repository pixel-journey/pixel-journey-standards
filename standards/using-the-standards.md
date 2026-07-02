# Using the Standards

**Practical Guide for Humans and AI Agents**

*Part of the Pixel Journey Standards Codex*

---

## Overview

This document explains how to effectively use the Pixel Journey Standards Codex in daily work. It is designed for both human developers and AI agents.

---

## Core Mindset

When working with Px codebases, always ask:

> "Is this work excellent, educational, aligned with our current strategy, and built to last?"

If the answer is clearly yes across the board, we are shipping Px Standard work.

---

## Recommended Daily Workflow

### For Humans

1. **Start with the Quick Reference** — Keep `px-standards-at-a-glance.md` and `px-work-checklist.md` open.
2. **Check relevant standards early** — Before major implementation decisions, review the most applicable documents (especially UI/UX standards, monorepo rules, and patterns).
3. **Use the Scorecard as the quality gate** — Before opening a PR, honestly run the Repo Readiness Scorecard.
4. **Document as you go** — Follow the Every Folder README Rule. Good documentation is part of the work, not after.
5. **Reference standards in PRs** — Use the PR template and mention which standards influenced your decisions.

### For AI Agents

1. **Always start with context** — Provide Core Principles + relevant standards documents in your prompt.
2. **Use the AI Agent Workflow Guide** — Follow `ai-agent-workflow-guide.md` for best results.
3. **Run the AI Self-Audit Checklist** — Before finalizing output, use `templates/ai-agent-self-audit-checklist.md`.
4. **Map decisions back to standards** — Explicitly reference which standards influenced architectural or implementation choices.
5. **When working on templates** — Also reference the `scaffolds-and-boilerplates/` standards.

---

## Most Important Documents by Category

| Category                        | Key Documents                                              |
|---------------------------------|------------------------------------------------------------|
| Strategy                        | Root README + `existing-primitives-first.md`               |
| UI/UX                           | All documents in `ui-ux-design/`                           |
| Patterns                        | Various `recommended-*.md` files in `engineering/`         |
| Quality                         | `repo-readiness-scorecard.md` + `px-work-checklist.md`     |
| Documentation                   | `every-folder-readme-rule.md` + templates                  |
| Templates & Scaffolds           | `scaffolds-and-boilerplates/` section                      |
| AI Workflow                     | `ai-agent-workflow-guide.md`                               |

---

## Common Anti-Patterns When Using Standards

- Treating standards as optional or "nice to have"
- Only checking standards at the end of a task
- Not running the scorecard before PRs
- Writing poor documentation because "we'll fix it later"
- Ignoring UI/UX standards in favor of quick custom solutions
- Not referencing standards in PR descriptions

---

## Continuous Improvement

The standards codex improves through real usage and feedback. If you find gaps, unclear guidance, or new patterns while working, propose improvements via the standards-proposal issue template.

---

*Use the standards as a tool to raise quality, not as bureaucracy.*

**Px Standards — Using the Standards**