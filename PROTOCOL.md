# Identity Sovereignty Protocol (v1.5)
**Status:** Frozen | **Type:** SSH-Ed25519 | **Context:** Technomoralist Node 01

## 1. The Mandate
Identity is anchored in hardware-bound cryptographic signatures, verified via a deterministic DNS pulse.

## 2. Canonical DNS Schema (Strict)
The `_identity` TXT record uses semicolon-delimited KVPs:
`v=1.5; epoch=[int]; status=[active|revoked]; alg=ssh-ed25519; fp=SHA256:[hash]; activated=[date]; prev=[hash]`
* **Order:** Unordered (Verifiers MUST parse to map).
* **Precedence:** DNS State > Repository State (IDENTITY.json).
* **Rollback:** Verifiers MUST persist and check that `new_epoch >= last_seen_epoch`.

## 3. Verification Rules
An identity claim is valid IF AND ONLY IF:
1. **DNS Status:** `status=active` (Failure to resolve = Invalid).
2. **Fingerprint:** DNS `fp` == Git Commit Signature `fp`.
3. **Cryptography:** Ed25519 signature is valid.

## 4. Dependencies
* **Registrar:** Physical trust dependency (Loss = Identity Death).
* **Time:** Git commit timestamps are advisory; DNS `activated` date is the logical root.

> Infrastructure > Platform.
