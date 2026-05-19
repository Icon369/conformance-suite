<p align="center">
  <a href="https://verdict.systems"><img src="https://verdict.systems/brand/sigil.svg" alt="Verdict — sealed chain node" width="120" height="120" /></a>
</p>

<h1 align="center">conformance-suite</h1>

<p align="center">
  Test suite that defines what counts as a <em>conformant</em> Sealed Evidence Record implementation.<br/>
  The bridge between the open spec and the RAND-Z patent licensing commitment.
</p>

<p align="center">
  <a href="https://github.com/Icon369/ser-spec">SER v0.1 spec</a> ·
  <a href="https://verdict.systems/ip-policy">RAND-Z commitment</a> ·
  <a href="https://verdict.systems/api/mcp">Live reference endpoint</a>
</p>

---

## Why this matters

Verdict's IP Policy commits to a RAND-Z (Reasonable And Non-Discriminatory, Zero-royalty) license for **any conformant SER implementation**. This repository defines what "conformant" means in machine-checkable terms.

If your implementation passes this suite, the RAND-Z commitment applies to your use of the underlying Verdict patent portfolio.

## What gets tested

The suite is being built around these conformance dimensions (all aligned with SER v0.1):

- **Canonical hashing:** deterministic given identical inputs (`stableStringify` semantics; depth + cycle guards)
- **Merkle root construction:** RFC 6962-style
- **Server-attested `received_at`:** binding into the canonical hash, advisory `event_time` alongside
- **Chain of custody:** `signer`, `prior_root` linkage, `retention_class` semantics
- **Transparency anchor:** Sigstore Rekor `hashedrekord` v0.0.1 with valid signature verification
- **FRE 902(14) packet export:** correct field set, custodian disclosure, system description

## Current state

The reference implementation is the public MCP endpoint at `https://verdict.systems/api/mcp`. The conformance test runner ships alongside `verdict-bench` in the next sprint.

## License

Apache 2.0.
