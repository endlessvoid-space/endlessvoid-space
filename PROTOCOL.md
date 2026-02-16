# Identity Sovereignty Protocol (v1.2)
**Status:** Active | **Type:** SSH-Ed25519 | **Context:** Technomoralist Node 01

## 1. The Mandate
We reject "Systemic Serfdom" in favor of **Logic Sovereignty**. Identity persistence is anchored in cryptographic necessity, not platform permission.

## 2. The Identity Anchor
* **Algorithm:** Ed25519 (Elliptic Curve)
* **Storage:** Hardware-bound local keystore (Private)
* **Public Ledger:** Repository Verification Keys
* **Fingerprint (SHA256):** EImwROjfIir5/+0y9BNw6+waGMdD3i5Xkp488UUQ2H0

## 3. Operational Logic
### A. Git Signing (Local)
All commits must be cryptographically signed by the local node.
(Configuration enforces strict SSH signing)

### B. Verification (Remote)
* **Git Remote:** Public key registered as "Authentication & Signing"
* **DNS:** security.txt located at /.well-known/security.txt
* **Handshake:** SSH-Ed25519

## 4. Continuity
If the primary node is compromised or retired:
1.  **Revoke:** Delete the compromised key from the Git host.
2.  **Rotate:** Generate a new Ed25519 pair on the new node.
3.  **Update:** Overwrite security.txt and index.html with the new fingerprint.
4.  **Broadcast:** Push the update to the repository.

> "Vitality > Metric." The goal is verification without friction.
