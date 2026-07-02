# Verifiable On-Chain Entropy Patterns (Current Era)

**Part of the Pixel Journey Standards Codex**  
*How we implement provably fair randomness and verifiable game mechanics in the current wave by composing public primitives — no custom contracts required.*

---

## Why This Matters for Px

Many of our most delightful retro-game experiences (Px Hot or Not voting arena, future mini-games, streak/reward systems, leaderboards with verifiable elements) require some form of randomness or verifiable pairing/selection.

In the current era we deliberately **avoid custom RNG or oracle contracts**. Instead, we extract high-quality entropy directly from the blockchain itself using only public, free primitives.

This approach is:
- **Zero cost** (no RAM, no oracle fees, no deployment)
- **Provably fair** — anyone can independently verify the result from the transaction hash and block data
- **Educational** — it teaches the ecosystem powerful patterns they can reuse
- **Aligned with our principles** — maximum leverage of existing infrastructure + client-side execution

---

## Core Pattern: TX Hash + Block Header Entropy

The fundamental technique we use (and recommend) is:

> Derive deterministic, verifiable randomness from the **hash of a specific on-chain transaction** (usually the user's action TX) combined with **recent block headers**.

This is the pattern powering the verifiable seed/pairing in Px Hot or Not (`pxhot.pxj` transfer memos).

### Why It Works So Well

1. Every transaction on WAX/Antelope has a cryptographically strong hash.
2. Block headers are public, immutable once finalized, and easily queryable via Hyperion.
3. Combining the TX hash (user action) + block header(s) gives excellent entropy without any trusted party.
4. The result can be reproduced by anyone with the TX ID — perfect for leaderboards, disputes, or post-game verification.

---

## Recommended Implementation Pattern (Client-Side)

```ts
// Example: Verifiable seed derivation for game mechanics
// (inspired by Px Hot or Not pairing logic)

import { getBlockHeader } from '@pxjourney/hyperion'; // or direct Hyperion query

import { sha256 } from 'js-sha256'; // or Web Crypto API

interface VerifiableSeedResult {
  seed: string;
  txId: string;
  blockNum: number;
  blockHash: string;
  timestamp: string;
}

export async function deriveVerifiableSeed(
  txId: string,
  blockNum: number
): Promise<VerifiableSeedResult> {
  // 1. Fetch the transaction details (via Hyperion or WharfKit receipt)
  const tx = await getTransaction(txId);
  
  // 2. Fetch recent block header(s) for additional entropy
  const block = await getBlockHeader(blockNum);
  
  // 3. Combine TX hash + block hash + action data
  const entropySource = [
    tx.transaction_id,
    block.block_hash,
    tx.block_num.toString(),
    tx.actions?.[0]?.data?.memo || '', // e.g. pxhot.pxj transfer memo
  ].join(':');

  const seed = sha256(entropySource);

  return {
    seed,
    txId: tx.transaction_id,
    blockNum: block.block_num,
    blockHash: block.block_hash,
    timestamp: block.timestamp,
  };
}

// Usage in game logic (e.g. Hot or Not pairing, reward drops, etc.)
const { seed, txId, blockNum } = await deriveVerifiableSeed(userActionTxId, recentBlockNum);

const randomValue = parseInt(seed.slice(0, 8), 16) % 100; // deterministic 0-99
```

**Key Properties**:
- Fully deterministic and reproducible
- No server or oracle involved
- Works offline after the TX is broadcast (great for PWA / mobile)
- Extremely cheap (just Hyperion queries)

---

## Px Hot or Not Specific Pattern (Reference Implementation)

In Px Hot or Not we use the `pxhot.pxj` token transfer TX as the entropy anchor:

- User sends a small `pxhot.pxj` amount with a specific memo
- The TX hash + the block in which it was included becomes the seed
- Pairing / matchup is derived client-side from this seed
- Leaderboard and results are fully verifiable by anyone

This creates a beautiful retro-game feel (“press start to roll the dice on-chain”) while remaining 100% trustless and free.

**Educational takeaway**: We turned a simple token transfer (existing primitive) into a powerful verifiable game mechanic without writing a single line of custom contract code.

---

## Best Practices & Edge Cases

- Always use **recent finalized blocks** (avoid very recent blocks that could theoretically be reorganized).
- Combine **multiple sources** when possible (TX hash + block hash + action memo + timestamp) for stronger entropy.
- Document the exact derivation formula in your README and in code comments so others can verify independently.
- For high-stakes mechanics, allow users to view the raw seed and verify the result themselves (transparency builds trust).
- Cache block headers locally (short TTL) to reduce Hyperion load.

**Anti-patterns to avoid**:
- Relying on a single block hash without TX context (weaker entropy)
- Using server-side RNG and claiming it is “on-chain”
- Hiding the derivation logic from users

---

## When This Pattern Is Not Enough (Future Signal)

This TX + block header approach is excellent for the current wave. We would only consider a custom contract for randomness if we needed:
- On-chain **commit-reveal** schemes with hidden commitments before reveal
- Extremely high-frequency or complex multi-party verifiable randomness that becomes awkward/expensive purely client-side
- Cryptographic primitives (e.g. VRF) that are not practical to implement client-side today

Even then, the bar remains high (see `existing-primitives-first.md`).

---

## Checklist for Any Verifiable Mechanic in Current Px Work

- [ ] Is the entropy derived from public TX data + block headers?
- [ ] Can any user independently reproduce and verify the result?
- [ ] Is the derivation logic clearly documented and educational?
- [ ] Did we avoid introducing custom contract or oracle dependencies?
- [ ] Does this feature also serve as a teaching example of powerful WAX patterns?

---

*This pattern is a core part of how we deliver delightful, trustless retro-game experiences in the current Px Portal wave while staying lightweight and maximally educational.*

**Px Standards — Verifiable On-Chain Entropy (Current Era)**
