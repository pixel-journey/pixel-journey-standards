# Px Observability Standards

**Guidelines for Logging, Monitoring, Error Tracking, and Analytics in Pixel Journey dApps**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

Observability helps us understand how our applications behave in production, detect issues early, and improve user experience. In the context of self-custody Web3 dApps, we must balance observability with user privacy and security.

This document sets pragmatic standards for observability across Px work.

---

## Core Principles

1. **Privacy First** — Never log or send sensitive user data (private keys, seeds, transaction details that could deanonymize, etc.).
2. **Client-Side First** — Prefer client-side error tracking and analytics that don’t require sending everything to a central server.
3. **Actionable Over Comprehensive** — Focus on signals that help us actually fix problems or improve the product.
4. **Respect User Consent** — Where analytics or error reporting is optional, make it opt-in and clearly communicated.
5. **Low Overhead** — Observability tooling should not meaningfully degrade performance.

---

## Recommended Observability Layers

### 1. Error Tracking & Crash Reporting

- Use a privacy-respecting error tracking service (e.g., Sentry with proper data scrubbing).
- Always scrub sensitive data before sending reports.
- Capture unhandled errors and promise rejections.
- Include useful context (browser, wallet type, route) without exposing user identity.
- Make error reporting opt-in where possible, especially for non-critical errors.

### 2. Logging

- Use structured logging in development.
- In production, avoid logging sensitive information.
- Consider lightweight client-side logging that can be enabled for debugging sessions.
- Never log private keys, seeds, or raw transaction data.

### 3. Performance Monitoring

- Use browser performance APIs and tools like Web Vitals where relevant.
- Monitor key user flows (connect wallet, sign transaction, load portfolio, etc.).
- Track slow operations and large bundle impacts.
- Consider Real User Monitoring (RUM) for critical dApps.

### 4. Analytics (Optional but Recommended)

- Use privacy-friendly analytics (e.g., Plausible, self-hosted Matomo, or custom lightweight solutions).
- Prefer event-based analytics over pageviews when possible.
- Avoid tracking personally identifiable information.
- Make analytics optional when feasible and clearly communicate what is being tracked.
- Focus analytics on product improvement rather than surveillance.

### 5. On-Chain Observability

- Use public indexers (Hyperion, etc.) to monitor on-chain activity where relevant.
- Avoid building custom centralized backends just for observability.
- Consider lightweight on-chain event tracking for important protocol actions when it provides real value.

---

## What Not to Do

- Logging or sending private keys, seeds, or sensitive transaction metadata.
- Using heavy analytics scripts that degrade performance.
- Collecting user data without clear consent or purpose.
- Relying solely on server-side logs when most logic is client-side.
- Over-instrumenting to the point of noise.

---

## Quality Bar

AAA-tier observability in Px means:
- We have good visibility into errors and performance issues without compromising user privacy or security.
- Error tracking helps us fix real problems quickly.
- Analytics (when used) genuinely informs product decisions.
- Users feel their data is respected.
- Observability tooling adds value without adding significant risk or performance cost.

---

## How This Connects to Other Standards

- **Error Handling Patterns**: Good error tracking complements good error handling in code.
- **Security Patterns**: Observability must never compromise security or self-custody guarantees.
- **UI/UX Standards**: Performance monitoring should align with user experience goals.

---

*This document provides a pragmatic, privacy-respecting approach to observability for Px dApps.*

**Px Standards — Observability Standards**