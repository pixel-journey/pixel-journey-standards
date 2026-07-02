# AI Agent Workflow Guide

**How to Effectively Use the Px Standards Codex with AI-Assisted Development**

*Part of the Pixel Journey Standards Codex*

---

## Why This Guide Exists

We heavily leverage AI agents (Antigravity IDE, parallel Claude/Grok sessions, custom agents) for planning, code generation, refactoring, and audits. This guide ensures that AI outputs consistently align with Px Standards and produce high-quality, educational, production-ready work.

---

## Recommended Workflow When Using AI Agents

### Phase 1: Context Setup (Always Do This First)

Before asking the AI to generate anything significant:

1. Provide the **Core Principles** from the root `README.md`.
2. Share the relevant **concrete patterns** documents (e.g. verifiable entropy, Hyperion+WharfKit, state management).
3. Reference the **Repo Readiness Scorecard** as the target quality bar.
4. Mention key rules (monorepo, documentation, zero individual styling).

**Example prompt starter**:
> "We are working in the Pixel Journey ecosystem. Follow the Core Principles (Existing Public Primitives First, client-side state, on-chain entropy). Target ≥ 85 on the Repo Readiness Scorecard. Use the recommended patterns from [specific documents]."

### Phase 2: Task-Specific Guidance

For different types of tasks, prioritize different documents:

| Task Type                    | Primary Documents to Reference                              | Secondary Documents                     |
|-----------------------------|-------------------------------------------------------------|-----------------------------------------|
| New feature / package       | Monorepo rules + relevant patterns + Scorecard              | Documentation rule + UI/UX alignment    |
| Refactor / audit            | Scorecard + relevant patterns                               | Engineering overview                    |
| Verifiable mechanics        | `verifiable-onchain-entropy-patterns.md`                    | `existing-primitives-first.md`          |
| UI work                     | `design-system-alignment.md` + monorepo rules               | Error handling patterns                 |
| Documentation / READMEs     | `every-folder-readme-rule.md` + new-readme-template         | Ecosystem integration                   |
| Security-sensitive work     | `recommended-secure-vault-patterns.md`                      | Error handling + state management       |

### Phase 3: Self-Audit Before Accepting Output

Before accepting or merging AI-generated work:

- Run the **AI Agent Self-Audit Checklist** (`templates/ai-agent-self-audit-checklist.md`).
- Mentally score against the **Repo Readiness Scorecard**.
- Check that key decisions are explained (educational value).
- Verify alignment with Existing Public Primitives First.

### Phase 4: Documentation & Handoff

Require the AI to:
- Produce or update high-quality READMEs using the template.
- Document key decisions and rationale.
- Include relevant cross-references to standards documents.

---

## Best Practices for High-Quality AI Output in Px

- **Be explicit** about which standards documents apply to the current task.
- **Ask for ultra-detailed plans** first (100+ steps when appropriate), then code.
- **Require mapping** back to the Core Principles and scorecard categories.
- **Demand educational value** — the output should help future humans or agents understand the "why".
- **Iterate with feedback** using the scorecard as the rubric.
- **Track context** — keep relevant standards documents in the conversation or system prompt when possible.

## Common AI Pitfalls to Avoid in Px Work

- Generating custom contracts without strong justification.
- Introducing individual styling or bypassing the Design System.
- Producing vague or low-detail plans.
- Skipping or writing poor-quality documentation.
- Ignoring the "Existing Public Primitives First" principle.
- Creating overly complex solutions when simpler composition of existing primitives would suffice.

---

## Recommended System Prompt / Context Snippet

You can add something like this to your AI agent system prompts or long-running conversations:

> "You are working on Pixel Journey projects. Always follow the Px Standards Codex. Prioritize Existing Public Primitives First. Target high scores on the Repo Readiness Scorecard. Produce educational, well-documented output. Use the recommended patterns for state management, error handling, verifiable mechanics, and security. Never introduce individual styling."

---

## Continuous Improvement

As we refine the standards and add new patterns, update this workflow guide and your AI agent contexts accordingly.

Feedback on what works well (or doesn't) when using AI with these standards is very valuable.

---

*This guide helps us get the maximum value from AI collaboration while maintaining the high standards we expect across the Pixel Journey ecosystem.*

**Px Standards — AI Agent Workflow Guide**