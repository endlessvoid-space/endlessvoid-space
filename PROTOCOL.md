# Identity Sovereignty Protocol (v1.3.1)
**Status:** Active | **Type:** SSH-Ed25519 | **Context:** Technomoralist Node 01

## 1. The Mandate
Identity persistence is anchored in cryptographic necessity. We use the domain as the primary source of truth to bypass platform-dependency.

## 2. The Identity Anchor
* **Algorithm:** Ed25519
* **Fingerprint (SHA256):** EImwROjfIir5/+0y9BNw6+waGMdD3i5Xkp488UUQ2H0
* **DNS Anchor:** _identity.endlessvoid.space (TTL: 120s)

## 3. Verification Rules (Deterministic)
An identity is valid IF AND ONLY IF:
1. **DNS State:** `_identity` TXT record exists and returns `status=active`.
2. **Fingerprint Match:** DNS `fp` matches the Git commit signature fingerprint.
3. **Lineage:** `prev` hash matches the prior ledger entry (if rotated).
4. **Physicality:** Signature is cryptographically valid for the Ed25519 curve.

## 4. Dependencies & Risk
* **Registrar:** The domain registrar is a physical trust dependency. Loss of domain control constitutes Identity Death.
* **Hosting:** GitHub/Cloudflare are UI layers. Identity root resides in the local hardware + DNS anchor.

## 5. Continuity & Revocation
Revocation is broadcast via DNS. A status change to `revoked` invalidates all future claims of authorship, regardless of platform "Verified" badges.

> Infrastructure > Platform.
