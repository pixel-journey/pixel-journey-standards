# Px Empty, Loading & Error State Standards

**On-Brand, Helpful, and Characterful Treatments for Empty, Loading, and Error States Across Pixel Journey**

*Part of the Pixel Journey Standards Codex — UI/UX Pillar*

---

## Purpose

Empty, loading, and error states are some of the most visible parts of any interface. When done well, they reinforce the Pixel Journey personality, reduce user frustration, and make the overall experience feel premium and intentional. When done poorly, they make interfaces feel broken or generic.

This document defines the expected quality bar and patterns for these three critical states.

---

## Core Principles

1. **Never Leave Users in Limbo** — Every state should communicate clearly what is happening (or not happening) and what the user can do next.
2. **On-Brand Personality** — These states should feel like they belong to the Pixel Journey universe (retro pixel + premium glassmorphic + slightly joyful).
3. **Helpful & Actionable** — Especially for errors and empty states, give users clear next steps.
4. **Visually Consistent** — Use approved components, spacing, typography, and color treatments from the Design System.
5. **Fast & Responsive** — Loading states should feel quick; empty and error states should not feel like dead ends.
6. **Accessible** — All states must be readable, focusable where appropriate, and respectful of reduced motion preferences.

---

## Empty State Standards

Empty states should feel intentional and helpful rather than like something is broken or missing.

**Recommended approach**:
- Use a clear, friendly illustration or icon (where appropriate) that fits the retro pixel aesthetic.
- Pair with a short, human headline (e.g., “No votes yet”, “Your collection is empty”, “Nothing to claim right now”).
- Add a brief, helpful description.
- Include a clear primary action when relevant (e.g., “Browse Assets”, “Start Voting”, “Go to Staking”).
- Keep the tone warm and encouraging, not apologetic.

**Anti-patterns**:
- Completely blank screens with no guidance.
- Generic “No data” messages with no personality.
- Overly long or technical explanations.
- Missing clear next-step actions when one exists.

---

## Loading State Standards

Loading states should feel fast, alive, and intentional — never like the app is frozen.

**Recommended approach**:
- Prefer skeleton loaders for content-heavy views (grids, lists, cards) — they give a sense of structure while data loads.
- Use subtle, on-brand animations (gentle pulse, shimmer, or pixel-appropriate movement).
- For quick actions, show loading state directly on the triggering element (button spinner, progress on card, etc.).
- For longer operations, consider a more prominent but still elegant loading indicator with optional progress or status text.
- Always maintain visual hierarchy so users understand what is still loading.

**Anti-patterns**:
- Generic full-screen spinners with no context.
- Frozen or unresponsive UI during loading.
- Overly long or unexplained loading states.
- Using the same heavy loading treatment for both quick and slow operations.

---

## Error State Standards

Error states should be clear, non-shaming, and easy to recover from.

**Recommended approach**:
- Use a clear but calm icon or illustration.
- Short, human headline (e.g., “Something went wrong”, “Unable to load your assets”).
- Specific, actionable error message when possible (avoid generic “Error” or “Failed”).
- Primary recovery action (Retry, Go Back, Refresh) + secondary actions when helpful.
- Optional technical details (collapsible or in a small “Details” section) for power users.
- Tone should be helpful and slightly reassuring, not alarming or apologetic.

**Anti-patterns**:
- Scary red error screens with no recovery path.
- Vague or technical-only error messages (“ERR_429” or stack traces).
- No clear way to retry or recover.
- Treating every error the same regardless of severity or context.

---

## Integration with Other Patterns

- These states should use approved Design System components (cards, buttons, alerts, illustrations where available).
- Motion for these states should follow the Motion, Animation & Haptics Standards (subtle, intentional, respectful of reduced motion).
- Error states should align with the behavioral Error Handling Patterns from the engineering side.
- Empty states in game-like or collection features can lean slightly more playful while staying helpful.

---

## Quality Bar

AAA-tier empty, loading, and error states in Px means:
- Every state feels intentional and on-brand
- Users always know what is happening and what they can do next
- The retro pixel + premium glassmorphic identity is maintained even in these “in-between” moments
- Frustration is minimized and recovery is easy
- The interface feels complete and thoughtful, even when data is missing or an error occurs

---

## How This Connects to Other Standards

- **Component Usage Standards**: Use approved components for these states.
- **Visual Language & Aesthetic Guidelines**: Maintain the overall aesthetic personality.
- **Motion & Haptics Standards**: Subtle, appropriate motion for these states.
- **Form & Validation Patterns**: Overlaps with error messaging in forms.
- **Error Handling Patterns** (engineering): Behavioral side of error recovery.

---

*This document helps ensure that even the “in-between” moments in Px interfaces feel premium, helpful, and characterful.*

**Px Standards — Empty, Loading & Error State Standards**