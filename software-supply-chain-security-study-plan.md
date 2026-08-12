# Software Supply Chain Security Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for the job roles which require good knowledge of software supply chain security.
Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be good at Software Supply Chain Security.
Software supply chain security is about securing all the components, tools, and services that go into building, packaging, and delivering software: source code, dependencies, build systems, CI/CD pipelines, artifacts, and runtime environments.

It is more towards:
- understanding how code and dependencies flow from dev laptops to production,
- securing dependencies and third-party components,
- hardening build and CI/CD systems,
- ensuring integrity of artifacts and deployments,
- and responding to supply chain incidents quickly.

Usually it will take you 8-16 weeks to be comfortable with software supply chain security fundamentals, depending on your background in AppSec, DevSecOps, and cloud.

## In short

1. Software supply chain security is not just dependency scanning.
2. Think more of end-to-end integrity: from source to production.
3. You should be comfortable with version control, CI/CD, and package managers.
4. You should know the basics of DevSecOps, Docker/Kubernetes, and cloud.
5. You must understand how real-world incidents happened to avoid repeating them.

## ToC

1. [Supply Chain Fundamentals](#supply-chain-fundamentals) - 2-3 weeks
2. [Dependencies and Package Ecosystems](#dependencies-and-package-ecosystems) - 2-3 weeks
3. [Build Systems and CI/CD Security](#build-systems-and-cicd-security) - 2-3 weeks
4. [Artifact Integrity, Signing and SBOM](#artifact-integrity-signing-and-sbom) - 2-3 weeks
5. [Historical Supply Chain Incidents](#historical-supply-chain-incidents) - 1-2 weeks
6. [Detection, Response and Governance](#detection-response-and-governance) - 2-3 weeks
7. [Books](#books)
8. [Videos](#videos)
9. [Courses](#courses)
10. [Certifications](#certifications)
11. [Interview Questions](#interview-questions)

## Supply Chain Fundamentals
**Duration: 2-3 weeks**

Goal here is to understand what “software supply chain” actually means.

### Week 1-3: The Chain
1. Understand the basic stages:
   1. Developer workstation and source control.
   2. Dependencies and package managers.
   3. Build systems and CI/CD pipelines.
   4. Artifact repositories and container registries.
   5. Deployment and runtime environments.
2. Read or refresh related study plans:
   1. [Application Security Study Plan](application-security-study-plan.md)
   2. [DevSecOps Study Plan](devsecops-study-plan.md)
   3. [Docker Security Study Plan](docker-security-study-plan.md)
   4. [Kubernetes Security Study Plan](kubernetes-security-study-plan.md)
3. Map risks at each stage:
   1. Source code tampering, credential theft.
   2. Malicious or vulnerable dependencies.
   3. Compromised build agents or pipelines.
   4. Poisoned images or artifacts.
   5. Misconfigurations in deployment.
4. Learn the frameworks that give this domain a common language:
   1. **[SLSA: Supply-chain Levels for Software Artifacts](https://slsa.dev/)** — the de facto standard for build provenance. Current spec is [SLSA v1.2](https://slsa.dev/spec/v1.2/) (Approved); v1.1 is still widely cited.
      1. The Build track and its levels ([Build track basics](https://slsa.dev/spec/v1.2/build-track-basics)):
         1. **L0** — no provenance, no guarantees. Where most projects start.
         2. **L1** — the build runs on a build platform that automatically generates provenance describing how the artifact was built, and that provenance is distributed to consumers.
         3. **L2** — the build platform itself generates *and signs* the provenance, so a tampered artifact can be detected without trusting the uploader.
         4. **L3** — hardened build platform: builds are isolated from each other, and the provenance signing key is not reachable from user-defined build steps. This is what defends against a SolarWinds- or tj-actions-style build compromise.
      2. Understand the terms *provenance*, *attestation*, *build platform*, *producer/consumer* and *verifier* — you will meet them again in in-toto and Sigstore.
      3. Practical framing: pick a target level per artifact tier, and know which controls move you from L1 to L3 rather than treating SLSA as a badge.
   2. [OWASP Top 10 CI/CD Security Risks](https://owasp.org/www-project-top-10-ci-cd-security-risks/) — the risk taxonomy for the build side of the chain.
   3. **A03:2025 Software Supply Chain Failures** in the [OWASP Top 10:2025](https://owasp.org/Top10/2025/) — supply chain is now a top-three web application risk category in its own right; useful when you need to justify this work to AppSec leadership. See [Application Security Study Plan](application-security-study-plan.md).

## Dependencies and Package Ecosystems
**Duration: 2-3 weeks**

Dependencies are one of the largest attack surfaces.

### Week 4-6: Dependencies
1. Understand different ecosystems:
   1. npm/yarn/pnpm for JavaScript/TypeScript.
   2. PyPI for Python, Maven/Gradle for Java, NuGet for .NET, etc.
2. Common risks:
   1. Dependency confusion and typosquatting.
   2. Malicious maintainers or compromised accounts.
   3. Abandoned or unmaintained packages.
3. Basic protections:
   1. Lockfiles and deterministic builds.
   2. Private registries or proxies.
   3. Using allowlists/blocklists for dependencies.
4. Dependency scanning:
   1. Understanding SCA (Software Composition Analysis).
   2. Severity, exploitability, and prioritization of dependency vulns.

## Build Systems and CI/CD Security
**Duration: 2-3 weeks**

Here you focus on securing the build and delivery machinery.

### Week 7-9: Pipeline Security
1. Understand key components:
   1. CI servers/agents.
   2. Build scripts and configuration.
   3. Secrets used in pipelines (cloud creds, signing keys, etc.).
2. Common risks:
   1. Attackers gaining access to CI agents or configuration.
   2. Insecure storage or handling of secrets.
   3. Unreviewed changes to build scripts.
3. Basic hardening:
   1. Least privilege for CI service accounts.
   2. Separate build agents for different trust levels.
   3. Code review and change control for build configs.
4. Cross-link with [DevSecOps Study Plan](devsecops-study-plan.md) for CI/CD details.

## Artifact Integrity, Signing and SBOM
**Duration: 2-3 weeks**

This is about making sure what you build is exactly what gets deployed.

### Week 10-12: Integrity
1. Artifact repositories and registries:
   1. Access control and separation of environments.
   2. Immutable artifacts where possible.
2. Signing and verification (high level):
   1. Code signing concepts.
   2. Image signing and verification.
3. Get hands-on with the current standard tooling — this is what "signing and SBOM" actually looks like in practice:
   1. **[Sigstore](https://www.sigstore.dev/)** — keyless signing for artifacts and container images using short-lived certificates tied to an OIDC identity (your CI workflow), with a public transparency log (Rekor) so signatures are auditable.
      1. **[cosign](https://github.com/sigstore/cosign)** — the tool you will use day to day: `cosign sign` / `cosign verify` for images and blobs, and attaching attestations and SBOMs to an image. Start with the [signing overview](https://docs.sigstore.dev/cosign/signing/overview/).
      2. Understand why keyless beats long-lived signing keys: nothing to steal, and the identity in the certificate tells you *which pipeline* built the artifact.
      3. Learn to enforce verification at admission time (e.g. a Kubernetes policy controller), not just to sign — an unverified signature buys you nothing. Cross-link with [Kubernetes Security Study Plan](kubernetes-security-study-plan.md).
   2. **[in-toto](https://in-toto.io/)** attestations — a signed, machine-readable statement about an artifact ("this image was built by this workflow from this source", "these tests passed", "this SBOM belongs to this digest").
      1. Learn the [in-toto attestation framework](https://github.com/in-toto/attestation) format: subject (artifact digest), predicate type, predicate. SLSA provenance is itself an in-toto attestation predicate.
      2. This is how provenance, SBOMs and scan results get bound to a specific artifact digest instead of floating around as loose files.
   3. **[OpenSSF Scorecard](https://scorecard.dev/)** — automated checks on the security posture of an open source repository (branch protection, code review, pinned dependencies, dangerous workflow patterns, signed releases, maintenance activity).
      1. Run it via the [scorecard CLI or GitHub Action](https://github.com/ossf/scorecard) on your own repos, and use published scores as one input when evaluating a new dependency.
      2. Know its limits: it measures *practices*, not the absence of vulnerabilities, and a high score is not a substitute for review.
4. SBOM (Software Bill of Materials):
   1. What an SBOM is and why it matters.
   2. How SBOMs help in incident response and compliance.
   3. Know the two formats you will actually be asked for:
      1. **[CycloneDX](https://cyclonedx.org/specification/overview/)** — OWASP-backed, security-focused; current spec is 1.7 (Oct 2025), backward compatible with 1.4-1.6, and it also carries VEX, attestations and cryptographic (CBOM) data.
      2. **[SPDX](https://spdx.dev/use/specifications/)** — ISO/IEC 5962 standardized, licensing/compliance heritage; 3.0 line is current (3.0.1), but a large share of real-world tooling still emits 2.3, so expect to handle both.
      3. Understand VEX (Vulnerability Exploitability eXchange) alongside SBOM: the SBOM says what is in there, VEX says whether a given CVE is actually exploitable in your product.
   4. Generation and consumption in a pipeline: generate the SBOM at build time (not by scanning the finished artifact later), attach it to the artifact digest as an attestation, and store it so you can answer "where do we use log4j / xz / this package" in minutes.
5. Simple practices:
   1. Track which artifact versions are deployed where.
   2. Ensure builds are reproducible and traceable.
   3. Pin dependencies and third-party CI actions by immutable digest/commit SHA, not by mutable tag.

## Historical Supply Chain Incidents
**Duration: 1-2 weeks**

You will learn a lot by understanding how major incidents happened.

### Week 13-14: Case Studies
1. **npm ecosystem attacks** (examples at a high level):
   1. Malicious packages published to npm to steal credentials, exfiltrate data, or run cryptominers.
   2. Typosquatting attacks where packages with names similar to popular libraries are published.
   3. Incidents where maintainers’ accounts were compromised and releases were backdoored.
2. **SHA-1 related attacks** (e.g., SHA-1 collision attacks):
   1. Collision attacks against SHA-1 showed that older hash algorithms may no longer be safe for integrity.
   2. Understand why moving away from weak hashes (like SHA-1) matters in signing and integrity checks.
3. **[xz-utils backdoor, CVE-2024-3094](https://openssf.org/blog/2024/03/30/xz-backdoor-cve-2024-3094/)** (discovered 29 March 2024 by Andres Freund) — the canonical *maintainer trust* case study, and the one to study first:
   1. What happened: a contributor ("Jia Tan"/JiaT75) spent roughly two years building credibility on the xz project until they were granted maintainer rights, then shipped a backdoor in xz 5.6.0/5.6.1 that patched liblzma at build time to hijack OpenSSH's authentication path — remote code execution for whoever held a specific Ed448 private key. CVSS 10.0.
   2. Why it is the better teaching example: the malicious payload was in the **release tarball, not the git repository**, and was activated only by the distro build process — so reading the upstream source would not have found it. It was caught by accident, via a performance anomaly in sshd.
   3. Controls it stresses: reproducible builds and build-from-source-of-truth (would have exposed the tarball/repo divergence), maintainer succession and social-engineering risk, single-maintainer critical dependencies, and the size of the transitive dependency graph that pulled liblzma into sshd at all.
   4. It landed in Fedora 40 beta/Rawhide, Debian unstable/testing, Kali and Arch — not in stable Ubuntu or Amazon Linux, largely by timing luck.
4. **[tj-actions/changed-files GitHub Action compromise, CVE-2025-30066](https://www.cisa.gov/news-events/alerts/2025/03/18/supply-chain-compromise-third-party-tj-actionschanged-files-cve-2025-30066-and-reviewdogaction)** (March 2025) — the canonical *CI/CD and mutable-reference* case study:
   1. What happened: an attacker used a compromised bot personal access token to retag versions v1 through v45.0.7 of a very widely used GitHub Action to point at a malicious commit. The injected code dumped the CI runner's memory and printed harvested secrets — cloud keys, GitHub PATs, npm tokens, private keys — into the workflow logs, which are public for public repos. Around 23,000 repositories used the action; patched in v46.0.1. Read it together with the related [reviewdog/action-setup compromise, CVE-2025-30154](https://www.cisa.gov/news-events/alerts/2025/03/18/supply-chain-compromise-third-party-tj-actionschanged-files-cve-2025-30066-and-reviewdogaction), which is believed to be how the tj-actions bot token was obtained in the first place — a two-hop compromise through the Action ecosystem. Good technical write-up: [Wiz](https://www.wiz.io/blog/github-action-tj-actions-changed-files-supply-chain-attack-cve-2025-30066).
   2. Controls it stresses: pinning third-party actions by **full commit SHA instead of a mutable tag**, least-privilege `GITHUB_TOKEN` and workflow permissions, short-lived OIDC credentials instead of long-lived secrets in CI, treating build logs as a secret sink, and monitoring for unexpected outbound network calls from runners.
   3. Response practice: work out how you would answer "did any of our workflows run this action in that window, and which secrets were exposed?" — then rotate.
5. **SolarWinds-style attacks** (2020, still the reference *build system compromise*):
   1. Attackers compromised the vendor’s build system.
   2. Malicious code was inserted into legitimate updates.
   3. Customers trusted signed updates, so the backdoor spread widely.
   4. Note that signing alone did not help here — the malicious build was legitimately signed. This is exactly the gap SLSA Build L3 (isolated builds, signing keys unreachable from build steps) and verifiable provenance are meant to close.
6. For each incident type, focus on:
   1. Where in the supply chain the attacker gained control.
   2. What controls were missing or weak.
   3. What changes were made after the incident (e.g., more signing, better monitoring, stricter access control).

## Detection, Response and Governance
**Duration: 2-3 weeks**

Finally, focus on how to detect and respond to supply chain issues and how to govern the program.

### Week 15-17: Operations
1. Detection:
   1. Monitoring dependency changes and vulnerability feeds.
   2. Alerting on unusual build or deployment behavior.
   3. Logging around CI/CD and registries.
2. Response:
   1. Having an inventory of where components are used.
   2. Rapid patching or rollback strategies.
   3. Communication with stakeholders and customers.
3. Governance:
   1. Policies for dependency management and updates.
   2. Standards for CI/CD and artifact handling.
   3. Regular reviews and tabletop exercises based on real incidents.

## Books

1. Any good book on software supply chain or modern software security that includes supply chain chapters.
2. Books on DevSecOps and cloud-native security that cover CI/CD and dependencies.

## Videos

1. Conference talks on software supply chain attacks and defenses.
2. Deep dives on major incidents (e.g., large vendor compromises, dependency attacks).
3. Talks on SBOMs, signing, and secure build pipelines.

## Courses

1. Courses specifically focused on software supply chain security, if available.
2. DevSecOps courses with strong coverage of CI/CD and dependency scanning.
3. Cloud-native security courses that include supply chain topics.

## Certifications

1. General cloud security and DevSecOps certifications that include supply chain security.
2. Any vendor-neutral or vendor-specific certifications that emphasize secure SDLC and CI/CD.

## Interview Questions

You can reuse questions from Application Security, DevSecOps, and cloud security, but add supply chain focus:

1. How would you reduce the risk of malicious dependencies in a large organization?
2. What controls would you put around CI/CD systems to protect against supply chain attacks?
3. How would you respond if a widely used third-party library in your product was suddenly found to be compromised?
4. How would you explain the importance of SBOMs and artifact signing to engineering leadership?

