# Identity Sovereignty Protocol (v1.1)
**Status:** Active | **Type:** SSH-Ed25519 | **Context:** Technomoralist Node 01

## 1. The Mandate
We reject "Systemic Serfdom" (commercial plugin dependencies like GPGTools) in favor of **Logic Sovereignty** (hardware-bound SSH keys). Identity persistence is anchored in technical necessity, not platform permission.

## 2. The Identity Anchor
* **Algorithm:** Ed25519 (Elliptic Curve)
* **Key Location:** ~/.ssh/id_ed25519 (Private)
* **Public Ledger:** ~/.ssh/id_ed25519.pub
* **Fingerprint (SHA256):** EImwROjfIir5/+0y9BNw6+waGMdD3i5Xkp488UUQ2H0

## 3. Operational Logic
### A. Git Signing (Local)
All commits must be cryptographically signed by the hardware node.

    git config gpg.format ssh
    git config user.signingkey ~/.ssh/id_ed25519.pub
    git commit -S -m "Message"

### B. Verification (Remote)
* **GitHub:** Public key added as "Signing Key" (Badge: Verified)
* **DNS:** security.txt located at /.well-known/security.txt
* **Handshake:** ssh -T git@github.com (Auth) vs git push (Transport)

## 4. Continuity
If the physical node (Mac Studio) is compromised or retired:
1.  **Revoke:** Delete "Mac Studio (Auth)" and "Signing Key" from GitHub.
2.  **Rotate:** Generate new Ed25519 pair on new hardware.
3.  **Update:** Overwrite security.txt and index.html with new fingerprint.
4.  **Broadcast:** Push update to endlessvoid-space repository.

> "Vitality > Metric." The goal is not encryption for its own sake, but authorship verification without friction.
