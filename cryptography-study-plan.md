# Cryptography Study Plan

In this plan, let's assume that you **already** have some **computer science skills** (linux basics, common windows or mac os use, search on the internet, edit a file...). 
<br>
But first, **what** is **cryptography** ? cryptography is the **practice** and **study** of techniques for **secure communication** in the presence of **adversarial behavior**.

<br>

This plan has several objectives, in short :
- learn about cryptography theoric concepts
- become familiar with useful cryptography tools
- how to apply all this acknoledgment in the context of cybersecurity

## ToC
1. [Theoretical Concepts](#theoretical-concepts) - 2 weeks
2. [Applied Cryptography](#applied-cryptography) - 2 weeks
3. [Cryptography Tools](#cryptography-tools) - 2 weeks
4. [Cryptanalysis & Challenges](#cryptanalysis-and-challenges) - 2 weeks
5. [Post-Quantum Cryptography (PQC)](#post-quantum-cryptography-pqc) - 2 weeks
6. [Resources](#resources)

## Theoretical Concepts
**Duration: 2 weeks**

In this first part you will focus on learning the **basics concepts** of **cryptography** (algorithms, keys, PKI, hashing).

### Week 1-2: Core Concepts
1. **Symmetric vs Asymmetric Encryption**: DES, AES, RSA, ECC.
2. **Hashing Algorithms**: MD5, SHA-1, SHA-256, SHA-3.
3. **Public Key Infrastructure (PKI)**: Certificates, CAs, Chain of Trust.
4. **Digital Signatures**: How they work and why they are important.

**Resources:**
- [Basic Cryptography](https://www.youtube.com/playlist?list=PLSNNzog5eyduN6o4e6AKFHekbH5-37BdV) from [Sunny Classroom](https://www.youtube.com/@sunnyclassroom24)
- [Cryptography Module on TryHackMe](https://tryhackme.com/module/cryptography)

## Applied Cryptography
**Duration: 2 weeks**

How to apply this knowledge in the context of cybersecurity and secure communications.

### Week 3-4: Protocols & Implementation
1. **SSL/TLS**: Handshake process, versions, and security.
2. **SSH**: Secure remote access, key management.
3. **Email Security**: PGP, GPG, S/MIME.
4. **Data at Rest vs Data in Transit**.
5. **Quantum readiness of the protocols you already use** (do this while you learn the classical versions, not later):
    - **TLS 1.3 hybrid key exchange:** classical ECDHE combined with ML-KEM so the handshake is safe even if one primitive falls. Standardised as [RFC 10024 — Hybrid Key Exchange in TLS 1.3: X25519MLKEM768, SecP256r1MLKEM768, SecP384r1MLKEM1024](https://www.rfc-editor.org/rfc/rfc10024.html) (Proposed Standard, August 2026).
    - **OpenSSL:** [OpenSSL 3.5 (April 2025)](https://openssl-library.org/news/openssl-3.5-notes/) ships ML-KEM, ML-DSA and SLH-DSA in the default provider, and prefers the hybrid `X25519MLKEM768` group for TLS by default.
    - **OpenSSH:** `mlkem768x25519-sha256` became the **default** key exchange in [OpenSSH 10.0 (April 2025)](https://www.openssh.com/releasenotes.html); OpenSSH 10.1 (Oct 2025) additionally *warns* when a connection negotiates a non-post-quantum key agreement (`WarnWeakCrypto`, on by default).
    - Practical exercise: run `openssl s_client -connect example.com:443 -groups X25519MLKEM768` and `ssh -Q kex` on your own boxes and record which of your endpoints are already hybrid-capable.
    - Note the asymmetry: **key exchange is being migrated first** (harvest-now-decrypt-later applies to confidentiality), while certificates/signatures move slower because the whole PKI has to move with them.

**Resources:**
- [Hak5: SSH Inside and Out](https://www.youtube.com/playlist?list=PLW5y1tjAOzI3IjZWkI4Qh0GP2bPTTF83a)
- [Real-world Cryptography](https://www.manning.com/books/real-world-cryptography) (Book)
- [RFC 10024: Hybrid Key Exchange in TLS 1.3 (ML-KEM + ECDHE)](https://www.rfc-editor.org/rfc/rfc10024.html)

## Cryptography Tools
**Duration: 2 weeks**

Become familiar with useful cryptography tools for analysis and implementation.

### Week 5-6: Hands-on Tools
1. **OpenSSL**: Generating keys, CSRs, and testing connections.
2. **GPG**: Encrypting and signing files.
3. **John the Ripper / Hashcat**: Password cracking basics (understanding strength).
4. **CyberChef**: The "Swiss Army Knife" for encryption/decoding.

**Resources:**
- [TryHackMe Practice](https://tryhackme.com/r/hacktivities/practice)
- [CyberChef](https://gchq.github.io/CyberChef/)

## Cryptanalysis & Challenges
**Duration: 2 weeks**

Time to challenge yourself with CTFs and cryptanalysis puzzles.

### Week 7-8: Breaking Codes
1. **Classical Ciphers**: Caesar, Vigenère (for historical context).
2. **Modern Attacks**: Padding Oracle, POODLE, Heartbleed (understanding the flaws).
3. **CTF Challenges**: Solve crypto challenges on platforms.

**Resources:**
- [RootMe Cryptanalysis Challenges](https://www.root-me.org/en/Challenges/Cryptanalysis/)
- [Cryptopals Crypto Challenges](https://cryptopals.com/)

## Post-Quantum Cryptography (PQC)
**Duration: 2 weeks**

A sufficiently large quantum computer breaks RSA, DH and ECC (Shor's algorithm) and halves the effective strength of symmetric keys (Grover's). You do not need to believe a cryptographically relevant quantum computer exists today to care: encrypted traffic captured now can be decrypted later, which is why migration is already a compliance item. Gartner ranked "Postquantum Computing Moves into Action Plans" among its top cybersecurity trends for 2026.

### Week 9: The Standards
1. **Why classical public-key crypto breaks**: Shor's algorithm vs RSA/ECC/DH; Grover's algorithm vs symmetric crypto (use AES-256 and SHA-384/512 rather than panicking).
2. **Harvest-now-decrypt-later (HNDL)**: the threat model that makes long-lived confidential data urgent *today*.
3. **The three finalized NIST standards (all published 13 August 2024):**
    - [FIPS 203 — ML-KEM (Module-Lattice-Based Key-Encapsulation Mechanism)](https://csrc.nist.gov/pubs/fips/203/final), derived from CRYSTALS-Kyber. The primary standard for key establishment.
    - [FIPS 204 — ML-DSA (Module-Lattice-Based Digital Signature Algorithm)](https://csrc.nist.gov/pubs/fips/204/final), derived from CRYSTALS-Dilithium. The primary standard for signatures.
    - [FIPS 205 — SLH-DSA (Stateless Hash-Based Digital Signature Algorithm)](https://csrc.nist.gov/pubs/fips/205/final), derived from SPHINCS+. Hash-based backup signature scheme, relying only on hash security — larger and slower, but a hedge against a lattice break.
4. **What comes next**: NIST selected **HQC** in March 2025 as a code-based backup KEM to ML-KEM (draft standard expected around 2026); track the [NIST Post-Quantum Cryptography project](https://csrc.nist.gov/projects/post-quantum-cryptography).
5. **Sizes matter**: ML-KEM/ML-DSA keys and signatures are far larger than ECC equivalents (ML-DSA signatures ~2.4-4.6 KB, SLH-DSA ~7.8-50 KB) — this breaks packet-size assumptions, certificate chains and embedded devices before it breaks anything cryptographic.

### Week 10: Migration & Crypto-Agility
1. **[NIST IR 8547 — Transition to Post-Quantum Cryptography Standards](https://csrc.nist.gov/pubs/ir/8547/ipd)** ([PDF](https://nvlpubs.nist.gov/nistpubs/ir/2024/NIST.IR.8547.ipd.pdf)) — the transition guidance. Proposes deprecating 112-bit-classical algorithms (RSA-2048, ECDSA P-256 etc.) after **2030** and disallowing them after **2035**. Read it for the algorithm-by-algorithm transition table.
    - Status check before you cite it: as of August 2026 this is still the **initial public draft** (published Nov 2024, comments closed Jan 2025). Quote the timelines as *proposed*, not final.
2. **Cryptographic inventory (CBOM)**: you cannot migrate what you cannot find. Enumerate every use of RSA, ECDSA, ECDH, DSA and finite-field DH across code, TLS endpoints, PKI, code signing, VPNs, HSMs and vendor products.
3. **Crypto-agility**: designing systems so an algorithm can be swapped without re-architecting — abstraction over crypto primitives, negotiated algorithms, no hardcoded key sizes, planned certificate/key rotation.
4. **Hybrid deployment**: prefer hybrid (classical + PQC) modes during transition so a flaw in the new lattice schemes does not immediately cost you confidentiality. See the TLS/SSH notes in [Applied Cryptography](#applied-cryptography).
5. **Prioritisation**: data with a long confidentiality lifetime (health, legal, national security, PII, long-lived signing keys and roots of trust) migrates first.

**Resources:**
- [NIST Post-Quantum Cryptography project (news, FAQs, standards)](https://csrc.nist.gov/projects/post-quantum-cryptography)
- [FIPS 203](https://csrc.nist.gov/pubs/fips/203/final) / [FIPS 204](https://csrc.nist.gov/pubs/fips/204/final) / [FIPS 205](https://csrc.nist.gov/pubs/fips/205/final)
- [NIST IR 8547 (initial public draft): Transition to Post-Quantum Cryptography Standards](https://csrc.nist.gov/pubs/ir/8547/ipd)
- [RFC 10024: Hybrid Key Exchange in TLS 1.3](https://www.rfc-editor.org/rfc/rfc10024.html)
- [Open Quantum Safe project (liboqs, oqs-provider)](https://openquantumsafe.org/) — the easiest way to actually experiment with PQC locally

**Hands-on Practice:**
- Build a hybrid TLS 1.3 connection with OpenSSL 3.5+ and confirm the negotiated group is `X25519MLKEM768`.
- Generate an ML-DSA key pair and compare key/signature sizes against RSA-2048 and ECDSA P-256.
- Produce a small cryptographic inventory for one service you own and mark each item deprecate-by-2030 or not.

## Resources
### Platforms
- [pwn.guide](https://pwn.guide)
- [TryHackMe](https://tryhackme.com)
- [RootMe](https://root-me.org)

### Books
- *Serious Cryptography* by Jean-Philippe Aumasson
- *Real-World Cryptography* by David Wong
