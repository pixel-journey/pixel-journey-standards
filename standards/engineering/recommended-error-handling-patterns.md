# Recommended Error Handling, Loading States & Optimistic UI Patterns

**Building Resilient and Delightful Px Experiences**

*Part of the Pixel Journey Standards Codex*

---

## Why This Matters

Great Px experiences feel responsive and trustworthy even when things go wrong or data is loading. Consistent, thoughtful handling of loading states, errors, and optimistic updates significantly improves perceived quality and user trust.

This document provides recommended patterns that align with our client-side state principles and Design System.

---

## Core Principles

1. **Never leave users in limbo** — Always show clear loading, error, or empty states.
2. **Optimistic UI when safe** — Update the interface immediately after user action when the outcome is highly likely to succeed.
3. **Graceful degradation** — The app should remain usable even if some data fails to load.
4. **Educational & transparent** — When possible, surface enough information for users (and developers) to understand what happened.

---

## Recommended Patterns

### 1. Loading States

Use consistent loading indicators from the Design System.

- For initial page/section load: Use skeleton loaders or a clear spinner + message.
- For background refetches: Prefer subtle indicators (e.g. stale data with a refresh indicator) rather than full-screen loaders.
- For button actions: Show loading state on the button itself when possible.

**Example with TanStack Query**:
```tsx
if (isLoading) return <LoadingSkeleton />;
if (isError) return <ErrorState error={error} onRetry={refetch} />;
```

### 2. Error States

- Always catch and display errors in a user-friendly way.
- Provide actionable recovery options (Retry, Go back, Contact support).
- Log detailed errors for developers (while showing minimal info to users).
- Use Design System `ErrorState` or `Alert` components.

**Recommended structure**:
- Clear icon + headline (“Something went wrong”)
- Short, friendly description
- Primary action (Retry) + secondary actions
- Optional technical details (collapsible for power users)

### 3. Empty States

- Use when there is genuinely no data (not an error).
- Make them helpful and on-brand (use illustrations or friendly copy where appropriate).
- Guide the user on what to do next.

### 4. Optimistic UI Updates

After a successful WharfKit transaction:
- Immediately update the UI to reflect the expected new state.
- Use TanStack Query’s optimistic update APIs or manually update Zustand state.
- If the transaction ultimately fails, revert the optimistic change and show an error.
- Only use optimistic updates for actions where failure is rare and the UX benefit is high.

**Good candidates**:
- Liking / voting actions
- Adding items to a local list
- Toggling settings

**Poor candidates**:
- Critical financial actions
- Actions with complex server-side validation

### 5. Transaction Feedback

For WharfKit transactions:
- Show clear “Confirm in wallet” state
- Show pending / confirming state after broadcast
- Show success with clear feedback (and optional link to transaction)
- Show failure with clear reason and retry option

Use Design System feedback components (toasts, banners, modals) consistently.

---

## Integration with State Management

- TanStack Query: Use `isLoading`, `isError`, `error`, and `isFetching` flags.
- Zustand: Maintain explicit `loading`, `error`, and `lastUpdated` state when needed.
- Combine both: Let TanStack Query handle server data, Zustand handle UI orchestration and optimistic state.

---

## Checklist

- [ ] Every data-fetching component has loading, error, and empty states
- [ ] Optimistic updates are used thoughtfully and safely
- [ ] Transaction flows have clear pending / success / failure feedback
- [ ] Error messages are user-friendly but informative
- [ ] Recovery actions (retry, etc.) are always available when relevant

---

*These patterns help Px experiences feel polished, resilient, and trustworthy.*

**Px Standards — Error Handling & Optimistic UI**