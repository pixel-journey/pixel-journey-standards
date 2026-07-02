# Every Folder README Rule

**Mandatory High-Quality README Requirement for Every Meaningful Folder**

*Part of the Pixel Journey Standards Codex*

---

## Why This Rule Exists

Good documentation is one of the highest-leverage things we can do. A high-quality README in every folder dramatically improves developer experience, reduces onboarding friction (for both humans and AI agents), and increases the long-term value of our work.

This rule is non-negotiable for maintaining high standards across the Pixel Journey ecosystem.

---

## Scope

This rule applies to:
- Every folder that contains meaningful code, configuration, or documentation
- Root folders of packages and templates
- Feature folders inside larger applications
- Shared library folders

It does **not** apply to trivial folders (e.g., `node_modules`, `.git`, build output folders).

---

## Minimum Requirements

Every folder that falls under this rule **must** have a `README.md` that includes at least the following sections:

1. **Purpose** — What does this folder contain and why does it exist?
2. **Architecture / Data Flow** — How does data move through this module? (Simple diagram or description)
3. **Usage** — How do other parts of the codebase use this?
4. **Key Decisions & Rationale** — Important technical or architectural decisions and why they were made.
5. **Pitfalls & Gotchas** — Common mistakes and edge cases to be aware of.
6. **Related Standards & References** — Links to relevant documents in this codex.

See the [Documentation Standards](documentation-standards.md) and the [New README Template](../../templates/new-readme-template.md) for more detailed guidance.

---

## Quality Expectations

READMEs should be:
- Clear and scannable
- Honest about limitations and trade-offs
- Educational (they should help the next person understand the "why")
- Kept reasonably up to date

See the full [Documentation Standards](documentation-standards.md) for deeper guidance on audience-aware documentation, ADRs, in-code comments, and overall documentation quality.

---

## Enforcement

- New folders should include a README from the start.
- Significant changes to a folder should include README updates.
- Before merging PRs that touch multiple folders, check that READMEs are still accurate and high-quality.
- The Repo Readiness Scorecard includes documentation quality as an evaluation criterion.

---

## Related Standards

- [Documentation Standards](documentation-standards.md) — Broader documentation guidelines
- [New README Template](../../templates/new-readme-template.md) — Ready-to-use template
- [Template Contribution Standards](../scaffolds-and-boilerplates/template-contribution-standards.md) — Documentation expectations for templates

---

*This rule, combined with the broader Documentation Standards, helps us maintain consistently high documentation quality across the entire ecosystem.*

**Px Standards — Every Folder README Rule**