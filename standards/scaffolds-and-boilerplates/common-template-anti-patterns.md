# Common Template Anti-Patterns

**What to Avoid When Building Templates and Scaffolds for Pixel Journey**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

This document highlights common anti-patterns seen in templates and scaffolds. Avoiding these helps maintain high quality, educational value, and alignment with Pixel Journey standards.

---

## Anti-Patterns to Avoid

### 1. Over-Engineering for Flexibility
Creating overly complex abstractions, plugin systems, or configuration layers "just in case" someone might need them. This often makes simple use cases harder and increases cognitive load.

**Better approach**: Start simple. Make the common path easy. Add extensibility only when there's a clear, recurring need.

### 2. Bypassing the Design System
Using raw Tailwind classes, custom CSS, or one-off styled components instead of the official Design System. This breaks visual consistency and makes future updates harder.

**Better approach**: Compose existing Design System components and tokens. Only create new variants through proper channels.

### 3. Mixing State Management Approaches
Using a combination of Context, Redux, Zustand, Jotai, and TanStack Query state in inconsistent ways. This leads to confusion and bugs.

**Better approach**: Follow the recommended state management patterns (TanStack Query for server state + Zustand for client state).

### 4. Poor or Missing Documentation
Templates with minimal or low-quality READMEs, no architecture explanation, and no guidance on how to customize or extend them.

**Better approach**: Invest in excellent documentation. Follow the Every Folder README Rule and the standards for high-quality READMEs.

### 5. Ignoring Existing Public Primitives
Building custom solutions for things that can be handled elegantly with Hyperion, AtomicAssets, Alcor, or other public primitives.

**Better approach**: Follow the Existing Public Primitives First principle. Only add custom logic when there's a clear gap.

### 6. Creating "Everything" Templates
Trying to include too many features, auth methods, payment integrations, admin panels, etc., in one template. This results in bloated, hard-to-understand codebases.

**Better approach**: Create focused templates that solve one primary use case well. Users can compose multiple focused templates if needed.

### 7. Weak Error Handling & UX States
Templates that crash on errors, show blank screens during loading, or have no empty states. This teaches bad habits.

**Better approach**: Include good examples of error handling, loading states, and empty states following the relevant standards.

### 8. Inconsistent or Ad-Hoc Styling
Different components using completely different visual treatments, spacing, colors, or interaction patterns.

**Better approach**: Strict adherence to the Design System and UI/UX standards from the beginning.

### 9. Heavy Custom Smart Contracts
Introducing custom contracts in templates without strong justification or clear educational value.

**Better approach**: Stick to public primitives unless there's a compelling reason. If including contracts, document the decision thoroughly.

### 10. Treating Templates as Throwaway Code
Writing low-quality, poorly structured code because "it's just a template."

**Better approach**: Treat templates as first-class code. They often become the starting point for real production applications.

---

## Summary

Good templates are:
- Simple where possible
- Well-documented and educational
- Consistent with Px standards and aesthetic
- Easy to understand and extend
- Focused on solving real problems cleanly

Avoiding these anti-patterns helps keep the quality bar high across the templates repository.

**Px Standards — Common Template Anti-Patterns**