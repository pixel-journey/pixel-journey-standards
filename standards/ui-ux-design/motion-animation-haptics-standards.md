# Px Motion, Animation & Haptics Standards

**Defining High-Quality, Characterful Motion and Feedback Across Pixel Journey Interfaces**

*Part of the Pixel Journey Standards Codex — UI/UX Pillar*

---

## Purpose

Motion and haptics are critical to the Pixel Journey experience. They reinforce the retro pixel soul while delivering a premium, modern feel. This document sets clear standards for animation, transitions, micro-interactions, and haptic feedback so that all Px interfaces feel cohesive, responsive, and delightful.

---

## Core Principles

1. **Intentional & Characterful** — Every animation should have a reason and contribute to the personality of the interface.
2. **Pixel-Snapped & Crisp** — Where possible, motion should feel pixel-perfect and aligned with the retro aesthetic.
3. **Premium but Not Heavy** — Animations should feel high-quality without introducing lag or excessive resource usage.
4. **Responsive Feedback** — Users should receive immediate, clear feedback on their actions.
5. **Respectful of User Preferences** — Full support for `prefers-reduced-motion`.
6. **Consistent Language** — Motion patterns should feel like they belong to the same design system across the ecosystem.

---

## Animation Timing & Easing

- Prefer spring-based physics (Framer Motion `spring` or equivalent) for most interactive elements — it feels more alive and premium than simple cubic-bezier easing.
- Use shorter, snappier durations for frequent actions (buttons, toggles, small state changes).
- Use slightly longer, more deliberate durations for major transitions (page changes, modal entrances, complex state shifts).
- Avoid overly long or floaty animations that feel slow or unresponsive.

**Recommended rough ranges** (adjust based on context):
- Micro-interactions: 150–300ms
- Standard transitions: 250–400ms
- Major view changes: 350–600ms

---

## Pixel-Snapped & Retro-Friendly Motion

- Where appropriate, use stepped or pixel-aligned motion rather than smooth sub-pixel animation.
- CRT-style effects, scanline movement, or phosphor bloom should be subtle and intentional — never distracting or performance-heavy.
- Icon and sprite animations should feel like they belong in a high-quality retro game interface.

---

## Micro-Interactions

- Every meaningful interactive element should have clear hover, press, and active states.
- Use scale, opacity, border, or glow changes thoughtfully.
- Combine multiple subtle properties (e.g., scale + shadow + glow) for richer feedback without being noisy.
- Loading states on buttons and actions should feel alive but not distracting.

**Examples of good micro-interactions**:
- Button press with slight scale down + glow increase
- Card hover with gentle lift + border highlight
- Success checkmark with a small satisfying “pop” or bounce

---

## Haptic Feedback

- Use haptics on high-engagement or game-like actions (voting, claiming rewards, important confirmations).
- Keep haptics subtle and tasteful — they should enhance, not overwhelm.
- Different actions can have different haptic profiles (light tap, medium impact, success buzz, error buzz).
- Always provide visual + audio fallback for devices without haptics or when haptics are disabled.

**Recommended approach**:
- Light tap for button presses and toggles
- Medium impact for important actions (stake, vote, claim)
- Distinct patterns for success vs error states

---

## Major Transitions & View Changes

- Page transitions and major modal entrances should feel deliberate and high-quality.
- Use shared element transitions or morphing where it meaningfully improves continuity (e.g., asset detail from grid to modal).
- Avoid excessive motion that could cause disorientation.
- Consider fade + scale or slide + fade combinations that feel premium and retro-appropriate.

---

## Performance & Accessibility

- All animations must respect `prefers-reduced-motion`. Provide instant or minimal-motion alternatives.
- Keep animation complexity reasonable — avoid heavy DOM thrashing or complex canvas animations on every interaction.
- Test on lower-powered devices and mobile.
- Use `will-change` and GPU-accelerated properties judiciously and clean them up after animations complete.

---

## Integration with Components

Motion and haptics behavior should be defined at the component level in the Design System where possible, so that using a Button, Card, or Modal automatically brings the correct motion profile.

When building custom interactive experiences (especially game-like features), follow the same timing, spring, and haptic principles.

---

## Quality Bar

AAA-tier motion and haptics in Px means:
- Every interaction feels responsive, intentional, and characterful
- The retro pixel + premium glassmorphic identity is reinforced through motion
- Animations enhance usability rather than getting in the way
- Haptics are used tastefully to increase engagement without becoming gimmicky
- Reduced motion preferences are fully respected
- Performance remains excellent across devices

---

## How This Connects to Other Standards

- **Visual Language & Aesthetic Guidelines**: Defines the overall personality that motion should support.
- **Component Usage Standards**: Components should carry appropriate motion behavior by default.
- **Error Handling Patterns**: Feedback animations for success/error states should align with these standards.

---

*This document helps ensure motion and haptics are a strength of the Pixel Journey experience rather than an afterthought.*

**Px Standards — Motion, Animation & Haptics Standards**