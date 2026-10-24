# Merkle trees

A Merkle tree hashes data in layers. Each leaf represents an item; each parent commits to its child hashes; the root summarizes the ordered dataset.

```text
                 root
                /    \
             H01      H23
            /  \     /  \
          H0   H1   H2   H3
          |    |    |    |
          A    B    C    D
```

To prove that **C** is in the dataset, a prover can send C and the sibling hashes needed to recompute the root (here, H3 and H01). A verifier hashes upward and compares the result to a trusted root. The verifier need not download every other item.

For a balanced tree with *n* leaves, an inclusion proof uses roughly log₂(*n*) sibling hashes. Exact proof shape, leaf encoding, and hash rules depend on the protocol.

## What this proves

An inclusion proof shows that the item is included in the data committed by that root, assuming the hash function and tree construction are used as specified.

It does **not** tell you whether the item is truthful, safe, or authorized. It also does not help if the root itself came from an untrusted source.

## Where you may see it

- Certificate Transparency logs
- Content-addressed storage and software distribution systems
- Merkle-based ledgers and blockchains

## Source

- [RFC 9162, Section 2.1: Merkle Trees](https://www.rfc-editor.org/rfc/rfc9162.html#section-2.1)
