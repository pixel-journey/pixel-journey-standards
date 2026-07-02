# Recommended Secure Local Vault & Encryption Patterns

**Self-Custody and Sensitive Data Handling for PxWallet and Similar Tools**

*Part of the Pixel Journey Standards Codex*

---

## Why This Matters

PxWallet and similar tools handle highly sensitive data (private keys, seeds, master passwords, session secrets). Following strong self-custody and encryption patterns is non-negotiable for user trust and security.

This document captures recommended patterns that align with our client-side state and self-custody principles.

---

## Core Principles

1. **Never send sensitive data to any server** — Everything stays client-side.
2. **Use strong, modern encryption** — Web Crypto API (AES-GCM or similar) with proper key derivation.
3. **Master password / key derivation** — Use PBKDF2 or Argon2 (via Web Crypto or WASM) with good parameters.
4. **Minimize attack surface** — Clear sensitive data from memory when possible. Use secure storage where available.
5. **User control & transparency** — Make encryption and storage behavior clear to the user.

---

## Recommended Patterns

### 1. Master Password + Key Derivation

- Derive a strong encryption key from the user’s master password using a strong KDF (PBKDF2 with high iterations or Argon2id via WASM).
- Never store the master password or derived key in plain text.
- Use the derived key to encrypt/decrypt the actual vault contents.

### 2. Encrypted Vault Storage

- Store the encrypted vault in IndexedDB or localStorage (with appropriate protection).
- Include metadata such as salt, iterations, and algorithm version for future compatibility.
- Support multiple accounts / sub-vaults when needed.

### 3. In-Memory Handling

- Keep decrypted sensitive data in memory for the shortest time possible.
- Clear sensitive variables after use when feasible.
- Avoid logging or exposing decrypted data.

### 4. Auto-Lock & Session Management

- Implement auto-lock after inactivity (configurable by user).
- Require master password re-entry after lock or on sensitive actions.
- Combine with WharfKit session management for signing operations.

### 5. Cross-Device / Backup Considerations (Future)

- For future multi-device support, consider secure export/import flows (encrypted backup files or seed phrase + password).
- Never rely on cloud sync for the raw vault without strong end-to-end encryption controlled by the user.

---

## Integration with WharfKit & State Management

- Use WharfKit for actual signing operations (never expose private keys to application code).
- Keep the encrypted vault in Zustand or a dedicated secure store.
- Use TanStack Query only for non-sensitive public data.

---

## Checklist

- [ ] All sensitive data stays client-side
- [ ] Strong key derivation (PBKDF2 / Argon2) is used
- [ ] Vault is encrypted at rest
- [ ] Auto-lock and re-authentication are implemented
- [ ] Sensitive operations require explicit user confirmation
- [ ] No sensitive data is logged or exposed unnecessarily

---

*These patterns help PxWallet and similar tools deliver true self-custody with strong security and good usability.*

**Px Standards — Secure Local Vault Patterns**