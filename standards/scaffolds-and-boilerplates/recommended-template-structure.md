# Recommended Template Structure

**Suggested Structure and Organization for High-Quality Pixel Journey Templates**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

This document provides a recommended structure for templates and scaffolds in the `pixel-journey-templates` repository. Following a consistent structure makes templates easier to understand, maintain, extend, and compare.

---

## Recommended Root Structure

```
template-name/
├── README.md                    # High-quality, standards-compliant README
├── package.json                 # Dependencies + scripts
├── tsconfig.json                # TypeScript configuration
├── next.config.js / similar     # Framework configuration (if applicable)
├── src/
│   ├── app/                     # App router pages/components (for Next.js)
│   ├── components/              # Reusable UI components
│   ├── lib/                     # Utilities, helpers, shared logic
│   ├── hooks/                   # Custom React hooks
│   ├── stores/                  # Zustand stores (if used)
│   ├── types/                   # TypeScript type definitions
│   └── styles/                  # Global styles (minimal, mostly via Design System)
├── public/                      # Static assets
├── docs/                        # Additional documentation (optional but recommended)
├── ai-prompts/                  # Role/task-specific prompts (optional but encouraged)
└── .env.example                 # Example environment variables
```

---

## Key Files and Their Purpose

### README.md (Required)
- Must follow the standards for high-quality READMEs.
- Include: purpose, architecture overview, getting started, customization guide, links to relevant standards.

### src/lib/
- Shared utilities and helper functions.
- Keep these small, focused, and well-documented.

### src/hooks/
- Custom React hooks that encapsulate reusable logic.
- Especially useful for data fetching, form handling, and wallet interactions.

### src/stores/
- Zustand stores for client-side state (when appropriate).
- Keep stores focused and well-organized.

### src/types/
- Shared TypeScript interfaces and types.
- Helps maintain consistency across the template.

### ai-prompts/ (Recommended)
- Include specialized AI prompts that help developers work with the template effectively.
- Follow the spirit of the AI Agent Workflow Guide.
- Can be general or role-specific (e.g., `feature-implementer.md`, `ui-polisher.md`).

### docs/
- Additional guides, architecture decisions, or examples.
- Especially useful for more complex templates.

---

## Design System & Styling

- All UI components should come from (or extend) the official Design System.
- Minimal custom CSS/Tailwind — prefer composition of existing components and tokens.
- Global styles should be very light and focused on layout resets or theme variables.

---

## State Management

- Prefer TanStack Query for server state and data fetching.
- Use Zustand for client-side/UI state when needed.
- Keep state management simple and predictable.
- Document why certain state decisions were made.

---

## Error Handling & UX States

- Include good examples of loading, error, and empty states.
- Follow the Error Handling Patterns and Empty/Loading/Error State Standards.
- Make these patterns visible and easy to reuse/extend.

---

## Documentation Quality

- Every folder should have a meaningful `README.md` when it adds clarity.
- Code should be well-commented, especially non-obvious logic.
- Architecture decisions should be explained (in README or `docs/`).

---

## What Good Templates Avoid

- Overly complex abstractions that make simple things hard.
- Heavy custom styling or design system bypasses.
- Mixing too many state management approaches.
- Poor separation between UI, logic, and data layers.
- Missing or low-quality documentation.

---

*This structure is a recommendation, not a strict requirement. The goal is consistency and high quality across templates.*

**Px Standards — Recommended Template Structure**