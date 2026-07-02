# UI/UX & Design System Alignment

**Rules and Patterns for Pixel-Perfect, Retro-Inspired Interfaces Across All Px Work**

*Part of the Pixel Journey Standards Codex*  
*This document works together with the Monorepo Rules and Repo Readiness Scorecard.*

---

## Core Principle

**All visual presentation in Pixel Journey products must come from the Design System.**

There is no acceptable middle ground during the current wave:

> No package, component, or feature may introduce its own Tailwind classes, custom CSS, or inline styles for brand, layout, or visual identity elements.

This is not a preference. It is a hard requirement for anything that wants to be considered Px Standard.

---

## Why This Rule Exists

- **Consistency**: Every Px experience (PxWallet, Px Hot or Not, beta portals, mini-games, etc.) must feel like part of the same premium retro pixel universe.
- **Maintainability**: Global changes (new CRT filter, theme variants, high-contrast mode) become trivial when everything routes through the Design System.
- **Speed with Quality**: Once the Design System is mature, building new interfaces becomes faster because the hard visual decisions are already made.
- **Educational Clarity**: It forces us to think in terms of tokens, variants, and composition rather than ad-hoc styling.

---

## Mandatory Rules

### 1. Zero Individual Styling

- Never write `className="bg-zinc-900 text-white p-4 rounded-xl"` (or similar) for anything that is part of the Px visual language.
- All spacing, colors, typography, borders, shadows, glassmorphism, CRT effects, animations, and haptics must come from Design System tokens or components.
- Temporary inline styles during rapid prototyping are allowed **only** if they are removed before the PR is opened.

### 2. Use Components and Variants First

Prefer composing existing Design System components and their variants over building new presentational components.

Example flow:
1. Need a modal? → Use the Design System `Modal` component + appropriate variant.
2. Need a card with glass effect? → Use `GlassCard` or the glass variant of `Card`.
3. Need special retro button states? → Use the button component with the correct variant prop, not a custom styled button.

Only create new presentational components when the Design System genuinely cannot express the needed pattern (and even then, contribute the pattern back to the Design System).

### 3. Token Usage Over Magic Values

- Use semantic tokens (`--px-color-bg-elevated`, `--px-radius-lg`, `--px-font-display`, etc.) instead of raw values.
- Never hardcode colors, spacing, or typography that should be controlled by the Design System.
- When in doubt, check the Design System documentation first.

### 4. Retro Pixel Aesthetic as Default

The default visual language for Px interfaces is:
- Glassmorphic or CRT-inspired treatments where appropriate
- Press Start 2P or equivalent pixel/retro display fonts for headings and key UI text
- 120Hz fluid motion with thoughtful spring physics (Framer Motion)
- Subtle haptics and micro-interactions that feel premium and game-like
- Dark, luxurious base with high-contrast accents

Deviations from this aesthetic require explicit justification and Design System team alignment.

---

## How This Connects to Other Standards

| Standard                        | Connection to UI/UX Alignment                          |
|---------------------------------|---------------------------------------------------------|
| Monorepo & PxPackages Rules     | Zero individual styling is one of the core monorepo rules |
| Repo Readiness Scorecard        | Directly impacts the UI/UX category score               |
| Every Folder README Rule        | Package READMEs must document which Design System components/variants they use |
| Existing Public Primitives First| UI/UX excellence is how we deliver delightful experiences on top of public contracts |

---

## Common Anti-Patterns to Reject

- Building a "quick custom button" because the Design System one "doesn't have the exact variant yet"
- Using arbitrary Tailwind colors or spacing because "it looked good in the mockup"
- Creating parallel component libraries inside individual packages
- Hardcoding animation values instead of using Design System motion tokens
- Treating the Design System as optional or "for later"

These patterns will be caught by the Repo Readiness Scorecard review.

---

## Practical Guidance for PxPackages & Beta Portals

During the current unification and beta portal phase:

- Every new UI surface should be built by composing Design System primitives.
- If you find yourself fighting the Design System, stop and open a discussion in the Design System repo instead of working around it.
- Document in your package README exactly which Design System components and tokens you are using. This helps others learn the system and surfaces gaps.

---

## Checklist for Any New UI Work

- [ ] All visual styling routes through the Design System (no ad-hoc classes or styles)
- [ ] Used existing components/variants wherever possible
- [ ] Semantic tokens used instead of magic values
- [ ] Retro pixel / glassmorphic / CRT aesthetic respected
- [ ] Package README documents Design System usage
- [ ] Self-scored against the UI/UX section of the Repo Readiness Scorecard

---

*This rule protects the soul of the Pixel Journey brand while making long-term maintenance dramatically easier.*

**Px Standards — UI/UX & Design System Alignment**