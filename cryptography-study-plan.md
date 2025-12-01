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
5. [Resources](#resources)

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

**Resources:**
- [Hak5: SSH Inside and Out](https://www.youtube.com/playlist?list=PLW5y1tjAOzI3IjZWkI4Qh0GP2bPTTF83a)
- [Real-world Cryptography](https://www.manning.com/books/real-world-cryptography) (Book)

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

## Resources
### Platforms
- [pwn.guide](https://pwn.guide)
- [TryHackMe](https://tryhackme.com)
- [RootMe](https://root-me.org)

### Books
- *Serious Cryptography* by Jean-Philippe Aumasson
- *Real-World Cryptography* by David Wong
