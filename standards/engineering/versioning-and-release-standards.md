# Px Versioning and Release Standards

**Guidelines for Versioning Packages, Templates, and Releases**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

Consistent and predictable versioning helps users, developers, and AI agents understand the impact of changes. This document defines the versioning and release expectations for Px packages and templates.

---

## Core Principles

1. **Follow Semantic Versioning (SemVer)** — We use MAJOR.MINOR.PATCH versioning.
2. **Be Conservative with Major Versions** — Breaking changes should be rare and well-justified.
3. **Communicate Impact Clearly** — Changelog entries and version bumps should make the impact of changes obvious.
4. **Release with Intention** — Don’t release just because “it’s been a while.” Release when there is meaningful value or fixes.

---

## Semantic Versioning Rules

| Change Type                    | Version Bump | Examples                                      |
|--------------------------------|--------------|-----------------------------------------------|
| Breaking changes               | MAJOR        | API removal, major behavior change, new required peer dependency |
| New features (non-breaking)    | MINOR        | New optional feature, new component variant   |
| Bug fixes & improvements       | PATCH        | Bug fix, performance improvement, docs update |

### What Counts as Breaking
- Removing or renaming public exports
- Changing function signatures in a backward-incompatible way
- Changing default behavior that existing code relies on
- Upgrading a peer dependency to a new major version

### What Does *Not* Count as Breaking
- Adding new exports
- Internal refactoring that doesn’t affect public API
- Bug fixes that restore correct behavior
- Documentation improvements

---

## Changelog Requirements

Every release should include a clear `CHANGELOG.md` entry (or equivalent) that includes:

- Version number and date
- Summary of changes
- Breaking changes (clearly marked)
- New features
- Bug fixes and improvements
- Migration notes when relevant

We recommend following the [Keep a Changelog](https://keepachangelog.com/) format.

---

## Release Process Expectations

- Use conventional commits or clear PR titles to help automate changelogs when possible.
- Tag releases properly in git.
- Publish to npm (for packages) with appropriate dist tags (`latest`, `next`, `beta`, etc.).
- Update dependent templates and examples when breaking changes are released.
- Communicate major releases through appropriate channels (X, Discord, GitBook).

---

## Pre-releases and Beta Versions

- Use `beta`, `rc`, or `next` dist tags for pre-releases.
- Clearly communicate the stability level in the release notes.
- Avoid publishing unstable code under the `latest` tag.

---

## Versioning for Templates

Templates should also follow semantic versioning when they introduce breaking changes to their structure or API.
- Major version bumps are appropriate when the template’s recommended architecture or file structure changes significantly.
- Minor/patch bumps are suitable for improvements and fixes that don’t require major migration effort.

---

## Quality Bar

AAA-tier versioning and releases in Px means:
- Version numbers accurately reflect the impact of changes
- Changelogs are clear and helpful
- Releases are intentional and well-communicated
- Breaking changes are rare and come with clear migration paths
- Users and contributors can easily understand what changed and why

---

## How This Connects to Other Standards

- **Documentation Standards**: Changelogs and migration guides are part of good documentation.
- **Template Contribution Standards**: Template releases should follow these versioning rules.

---

*This document helps create predictable and professional release practices across Px packages and templates.*

**Px Standards — Versioning and Release Standards**