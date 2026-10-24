# Crypto Data Structures

A visual guide to data structures that use cryptographic hashes to make data easier to verify.

These structures help answer questions such as “is this item in the committed dataset?” or “did this public log only grow?” They do not make data true by themselves: a verifier still needs a trusted root, signature, consensus rule, or other authenticated reference.

## Guides

- [Merkle trees](guides/merkle-trees.md) — compact commitments and inclusion proofs.
- [Append-only transparency logs](guides/transparency-logs.md) — inclusion and consistency proofs in Certificate Transparency.
- [Merkle Patricia tries](guides/merkle-patricia-tries.md) — authenticated key-value state as used by Ethereum.

## One-minute model

1. Hash the data at the leaves.
2. Hash child nodes together to build a root.
3. Publish or authenticate the root.
4. Provide a short proof that lets another party check a claim against that root.

The data structure organizes the data and proof. The hash function, signature scheme, protocol rules, and trust model determine what the proof means.

## Scope

This is a conceptual guide, not a blockchain implementation, cryptographic library, or endorsement of any system. The diagrams simplify details; refer to the cited specifications for exact encodings and verification rules.

Last reviewed: **2026-10-24**

See [SOURCES.md](SOURCES.md) for references.
