# Identity Sovereignty Protocol (v1.4)
**Status:** Active | **Type:** SSH-Ed25519 | **Context:** Technomoralist Node 01

## 1. The Mandate
Identity is anchored in hardware-bound cryptographic signatures, verified via a deterministic DNS pulse.

## 2. The Identity Anchor
* **Algorithm:** Ed25519
* **Fingerprint (SHA256):** EImwROjfIir5/+0y9BNw6+waGMdD3i5Xkp488UUQ2H0
* **DNS Anchor:** _identity.endlessvoid.space (TTL: 120s)

## 3. Canonical DNS Schema
The DNS record must follow this KVP format (semicolon delimited):
`v=1.4; epoch=[int]; status=[active|revoked]; alg=ssh-ed25519; fp=SHA256:[hash]; activated=[date]; prev=[hash]`

## 4. Deterministic Verification Rules
An identity claim is valid IF AND ONLY IF:
1. **DNS Persistence:** The `_identity` record is reachable.
2. **Rollback Protection:** The `epoch` is greater than or equal to the last verified state.
3. **Status Check:** `status` == `active`.
4. **Fingerprint Match:** DNS `fp` == Git Commit Signature `fp`.
5. **Cryptographic Validity:** The SSH-Ed25519 signature is valid.

## 5. Security Posture (Identity Only)
* **Registrar Risk:** Loss of domain control = Identity Death.
* **DNS SEC:** Not required for v1.4, but MitM resolver risks are acknowledged.
* **History:** Signatures made before a broadcast `revocation` are considered valid if they match the lineage recorded in the `IDENTITY.json` ledger.

> Infrastructure > Platform.
