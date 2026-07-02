# Px Security Review & Hardening Standards

**Guidelines for Security Review Processes and Application Hardening**

*Part of the Pixel Journey Standards Codex*

---

## Purpose

Security is critical for self-custody tools and Web3 applications. While we have specific patterns for secure vaults and key management, we also need broader processes for reviewing code for security issues and hardening applications against common threats.

This document provides guidance on security review practices and hardening measures.

---

## Core Principles

1. **Defense in Depth** — Rely on multiple layers of protection rather than a single control.
2. **Least Privilege** — Only grant the minimum permissions and access required.
3. **Fail Securely** — When something goes wrong, the system should default to a safe state.
4. **Keep Security Simple** — Complex security controls are more likely to have flaws or be misconfigured.
5. **Review Early and Often** — Security should be considered throughout development, not just at the end.

---

## Security Review Practices

### Code Review Focus Areas

When reviewing code (especially for packages and critical dApp features), pay special attention to:

- Handling of sensitive data (keys, seeds, transaction data)
- Input validation and sanitization
- Authentication and authorization flows
- Use of cryptography and randomness
- Error handling that could leak information
- Dependencies and supply chain risks
- Client-side vs server-side trust boundaries

### Recommended Review Process

- Security-sensitive changes should receive extra scrutiny during code review.
- For major releases or new packages, consider a dedicated security review pass.
- Use checklists or automated tools where helpful (e.g., dependency scanning, static analysis).
- Document significant security decisions and their rationale.

---

## Application Hardening Measures

### Client-Side Hardening

- Minimize the attack surface (reduce unnecessary permissions, features, and dependencies).
- Use Content Security Policy (CSP) where applicable in web applications.
- Protect against common web vulnerabilities (XSS, CSRF, clickjacking).
- Validate and sanitize all external input.
- Use secure defaults for wallet connections and signing requests.

### Cryptographic & Key Management Hardening

- Follow the [Secure Local Vault Patterns](../recommended-secure-vault-patterns.md).
- Use well-vetted cryptographic libraries.
- Avoid custom cryptography implementations.
- Ensure proper key derivation, storage, and zeroization practices.
- Consider hardware wallet support and secure enclave usage where feasible.

### Dependency & Supply Chain Hardening

- Regularly audit and update dependencies.
- Use lockfiles and reproducible builds where possible.
- Consider tools for dependency vulnerability scanning.
- Be cautious with new or poorly maintained dependencies.

### Operational Hardening

- Have a clear process for responding to security incidents or vulnerabilities.
- Consider bug bounty programs or responsible disclosure channels for critical applications.
- Keep security contact information up to date.

---

## Quality Bar

AAA-tier security practices in Px means:
- Security is treated as a first-class concern throughout development
- Code in sensitive areas receives appropriate review
- Applications follow defense-in-depth principles
- Users can reasonably trust that their assets and data are protected
- Security decisions are documented and intentional

---

## How This Connects to Other Standards

- [Secure Local Vault Patterns](../recommended-secure-vault-patterns.md) — Specific patterns for key and secret management.
- [Error Handling Patterns](../recommended-error-handling-patterns.md) — Secure error handling that doesn’t leak sensitive information.
- [Observability Standards](../observability-standards.md) — Security-relevant logging and monitoring practices.

---

*This document helps establish a security-conscious culture and process across Px development.*

**Px Standards — Security Review & Hardening Standards**