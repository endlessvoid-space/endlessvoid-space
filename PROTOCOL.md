# Identity Sovereignty Protocol (v1.3)
**Status:** Active | **Type:** SSH-Ed25519 | **Context:** Technomoralist Node 01

## 1. The Mandate
Identity persistence is anchored in cryptographic necessity. We use the domain as the primary source of truth to bypass platform-dependency.

## 2. The Identity Anchor
* **Algorithm:** Ed25519
* **Fingerprint (SHA256):** EImwROjfIir5/+0y9BNw6+waGMdD3i5Xkp488UUQ2H0
* **DNS Anchor:** _identity.endlessvoid.space

## 3. Verification Protocol
1. **Infrastructure:** Query TXT record at `_identity.endlessvoid.space`.
2. **Platform:** Match against "Verified" signature on GitHub.
3. **Local:** Verification of signed commits via `git log --show-signature`.

## 4. Continuity & Revocation
In the event of compromise, the `status` flag in the DNS TXT record will be set to `revoked` and a new key-node will be initialized.

> Infrastructure > Platform.
