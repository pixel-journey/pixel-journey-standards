# Px Form, Input & Validation Patterns

**Consistent, On-Brand Patterns for Forms, Inputs, and User Data Entry Across Pixel Journey**

*Part of the Pixel Journey Standards Codex — UI/UX Pillar*

---

## Purpose

Forms and inputs appear across nearly every Px feature — staking, voting, claiming rewards, settings, onboarding, asset management, and more. Having consistent, high-quality, on-brand patterns for forms, validation, and feedback is essential for both usability and the overall Pixel Journey feel.

This document defines the expected patterns and quality bar for all form-related UI.

---

## Core Principles

1. **Clarity First** — Users should always understand what is being asked and why.
2. **Immediate & Helpful Feedback** — Validation should happen as early and helpfully as possible.
3. **Consistent Visual Language** — All forms should feel like they belong to the same design system and aesthetic.
4. **Accessible & Keyboard-Friendly** — Every form must be fully usable via keyboard and assistive technologies.
5. **Graceful Error Handling** — Errors should be clear, non-shaming, and easy to recover from.
6. **On-Brand Personality** — Form interactions should feel premium, retro-pixel appropriate, and slightly joyful where context allows.

---

## Input Field Standards

- Use Design System Input components exclusively.
- Clear, visible labels above or beside fields (never rely on placeholders alone).
- Consistent helper text placement and styling.
- Required vs optional fields should be clearly distinguished (use “(optional)” or asterisks consistently).
- Focus states should be strong and on-brand (glow, border highlight, or pixel-appropriate treatment).
- Disabled and read-only states should be visually distinct and accessible.

**Anti-pattern**: Using raw `<input>` elements or mixing multiple input styles on one form.

---

## Validation Patterns

- **Real-time / On-blur validation** is preferred for most fields (especially format validation like addresses, amounts, percentages).
- **On-submit validation** should be used for complex cross-field rules.
- Error messages should be specific, actionable, and friendly (e.g., “Please enter a valid WAX account name” instead of “Invalid input”).
- Success states can be subtle (green check, cleared error) — avoid over-celebrating routine valid input.
- Validation should not block the user unnecessarily while they are still typing.

**Recommended flow**:
1. User types → real-time format validation where helpful
2. User leaves field (on blur) → full validation + error display if needed
3. User submits form → final cross-field validation + clear error summary if needed

---

## Form Layout & Grouping

- Use consistent spacing and visual grouping for related fields.
- Section headers or subtle dividers can help organize complex forms.
- Mobile/responsive behavior should stack fields cleanly with appropriate touch targets.
- Primary action button should be prominent and clearly associated with the form.

---

## Error & Success Feedback

- Use Design System Alert, Toast, or inline error components.
- Error messages should appear close to the relevant field(s).
- For form-level errors, use a prominent but non-alarming summary banner.
- Success feedback can use toasts or subtle inline confirmation (especially after async actions like staking or voting).
- Avoid generic “Something went wrong” messages — be specific when possible.

---

## Loading & Submission States

- Buttons should show clear loading state during async operations (staking, claiming, voting, etc.).
- Disable or visually indicate that the form is processing.
- Do not allow duplicate submissions while a request is in flight.
- Provide clear success or error feedback after the operation completes.

---

## Special Input Types

- **Amount / Number inputs**: Use appropriate steppers or incrementers when helpful. Show token symbol or unit clearly.
- **Account name inputs**: Strong real-time validation against WAX naming rules.
- **Percentage / Slider inputs**: Combine slider with direct number input when precision matters.
- **Checkbox / Toggle / Radio groups**: Use approved components with clear labels and consistent spacing.

---

## Accessibility

- All inputs must have proper labels (visible or aria-label).
- Error messages must be programmatically associated with their fields.
- Keyboard navigation and focus management must work correctly.
- Color alone should never be the only indicator of state (pair with icons or text).

---

## Quality Bar

AAA-tier form patterns in Px means:
- Every form feels clear, consistent, and on-brand
- Validation is helpful rather than frustrating
- Errors are easy to understand and recover from
- The retro pixel + premium feel is maintained even in data-entry flows
- Accessibility is non-negotiable
- Users complete forms successfully and confidently

---

## How This Connects to Other Standards

- **Component Usage Standards**: Forms should be built from approved input, button, and feedback components.
- **Motion & Haptics Standards**: Form interactions (focus, validation, submission) should use appropriate motion and haptic feedback.
- **Error Handling Patterns**: Behavioral side of form errors and recovery.
- **Visual Language Guidelines**: Overall aesthetic that forms must support.

---

*This document helps ensure that form experiences across Px are consistently high-quality and aligned with the broader design language.*

**Px Standards — Form, Input & Validation Patterns**