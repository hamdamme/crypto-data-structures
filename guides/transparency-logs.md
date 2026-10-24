# Append-only transparency logs

A transparency log records entries in order and publishes a signed tree head: a statement containing the log’s current size and Merkle root, signed by the log.

This supports two useful proofs:

- **Inclusion proof:** shows that one entry appears in a particular tree.
- **Consistency proof:** shows that a newer tree preserves all entries from an earlier tree and only appends new ones.

```text
earlier tree:   [A, B, C]
                         \
newer tree:     [A, B, C, D, E]
                 same prefix + appended entries
```

Certificate Transparency uses this model so clients and monitors can check that certificates appear in public logs and that a log’s published history is append-only.

## Trust and limits

A signed tree head authenticates what the log claims; it does not prove that the log showed the same view to every client. Clients and monitors may need to compare tree heads and verify consistency proofs to detect conflicting views. Transparency logs also do not decide whether a logged certificate or other entry is legitimate.

## Source

- [RFC 9162: Certificate Transparency Version 2.0](https://www.rfc-editor.org/rfc/rfc9162.html)
