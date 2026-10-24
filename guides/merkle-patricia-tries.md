# Merkle Patricia tries

A trie organizes values by the prefixes of their keys. A Merkle Patricia trie combines this key-based structure with cryptographic hashes: nodes encode parts of the key path and refer to child nodes through hashes.

```text
                 state root
                     |
               hashed node
                /       \
          key prefix   hashed node
                           |
                       key/value
```

In Ethereum’s execution layer, Merkle Patricia tries are used to represent state and other key-value data. A root hash commits to a particular trie state. If data is changed, the affected path and root change.

The design supports authenticated data: a verifier can check that supplied nodes and values are consistent with a trusted root. Node encoding, key encoding, and hashing are part of the protocol; a diagram is not enough to implement a compatible trie.

## Key distinction

A Merkle tree is usually introduced as an ordered collection of leaves. A trie organizes data by keys. A Merkle Patricia trie adds hash-based commitments to a Patricia-style trie. Both can support proofs, but their layouts and proof rules differ.

## Source

- [Ethereum.org: Merkle Patricia Trie](https://ethereum.org/developers/docs/data-structures-and-encoding/patricia-merkle-trie/)
