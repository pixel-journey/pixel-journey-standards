# Every Folder Must Have an Excellent README

**The Documentation Rule for Pixel Journey Repositories**

*Part of the Pixel Journey Standards Codex*  
*This rule is non-negotiable for any repo that wants to be considered Px Standard.*

---

## Why This Rule Exists

The single biggest differentiator between good Web3 projects and truly excellent ones is **documentation quality**. The gkniftyheads-tracker benchmark you shared succeeds largely because every folder (`scripts/`, `data/`, `demo/`, `.github/`, etc.) has a rich, educational README that explains purpose, architecture, usage, pitfalls, and how it fits into the larger system.

We want every Px repo, package, and beta portal to reach (and eventually exceed) that level of clarity and educational value.

This rule ensures that:
- New contributors and AI agents can onboard rapidly
- Knowledge is not trapped in individual heads
- The "why" behind decisions is preserved
- Our work serves as teaching material for the broader WAX/Antelope ecosystem

---

## The Rule (Mandatory)

**Every folder and subfolder that contains meaningful code, configuration, data, or documentation must have its own `README.md`.**

This applies to:
- Root of every Px repository
- `src/`, `app/`, `components/`, `lib/`, `hooks/`, `utils/`, `types/`, `contracts/`, `scripts/`, `data/`, `demo/`, `examples/`, `.github/`, `standards/`, `templates/`, etc.
- Any package inside a monorepo (`@pxjourney/*`)

**Exception**: Purely internal folders that are never accessed by anyone outside the immediate team (e.g. `.next/`, `dist/`, `node_modules/`, `.turbo/`) do not require READMEs.

---

## What "Excellent" Means (Quality Bar)

A README is considered excellent when it satisfies **all** of the following:

### 1. Purpose & Context (Why it exists)
- Clearly states what this folder/package contains
- Explains how it fits into the larger Px ecosystem or specific dApp (PxWallet, Px Hot or Not, PxPackages, beta portals, etc.)
- Answers "Why was this built this way?"

### 2. Architecture & Data Flow
- Includes a simple text diagram, Mermaid diagram, or clear description of how data moves through this module
- Shows relationships to other folders/packages
- Mentions key technologies and why they were chosen (especially alignment with Existing Public Primitives First)

### 3. Usage & Quickstart
- How to use the code, scripts, or data in this folder
- Common commands or import patterns
- Example usage where helpful

### 4. Pitfalls & Edge Cases
- Documents common mistakes, gotchas, or non-obvious behaviors
- Includes troubleshooting guidance
- Notes performance, security, or maintenance considerations

### 5. Educational Value
- A new developer or AI agent should learn something valuable about WAX patterns, modern frontend architecture, or Px philosophy by reading it
- References related standards documents or other Px repos where relevant
- Preserves institutional knowledge

### 6. Maintenance
- Kept reasonably up to date as the code evolves
- Uses clear, scannable formatting (headings, tables, code blocks, checklists)
- Avoids walls of text

---

## Recommended README Structure (Template)

```markdown
# Folder / Package Name

**One-sentence description of what this is and why it matters.**

## Purpose & Context

## Architecture / Data Flow

## Usage

## Key Decisions & Rationale

## Pitfalls & Gotchas

## Related Standards & References

## Maintenance Notes
```

You are encouraged to expand or adapt this structure, but the six quality criteria above must be met.

---

## How This Connects to the Repo Readiness Scorecard

This rule directly supports **Category 1 (Documentation Excellence)** and **Category 2 (Educational Spirit)** of the scorecard. Repos that consistently follow this rule will score significantly higher and be much more likely to achieve "Px Standard" status (≥ 85/100).

When performing a self-audit with the scorecard, ask:
> "If someone opened this folder for the first time in 6 months, would the README give them everything they need to understand and contribute effectively?"

---

## Enforcement & Culture

- **Before merging** any significant new folder or package, the author is responsible for adding or updating the README.
- **AI agents** generating code or folder structures must include a high-quality README as part of the output.
- **Code review checklist** should include: "Does every new or changed folder have an excellent README?"
- Over time, we will raise the bar further (e.g. requiring Mermaid diagrams in complex areas, or auto-generated API docs).

---

## Examples of Excellence (Reference)

- The `scripts/`, `data/`, `demo/`, and `.github/` folders in high-quality trackers like gkniftyheads-tracker
- The new `standards/web3-onchain/` documents in this codex itself (they aim to meet this bar)
- Future PxPackages that adopt this rule from day one

We are not aiming for perfect prose. We are aiming for **clarity, education, and preservation of knowledge**.

---

*This rule is one of the highest-leverage ways we can ensure the entire Pixel Journey ecosystem remains excellent, educational, and welcoming to new contributors (human and AI) as we scale.*

**Px Standards — Documentation Rule**