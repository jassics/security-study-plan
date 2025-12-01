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
3. SBOM (Software Bill of Materials):
   1. What an SBOM is and why it matters.
   2. How SBOMs help in incident response and compliance.
4. Simple practices:
   1. Track which artifact versions are deployed where.
   2. Ensure builds are reproducible and traceable.

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
3. **SolarWinds-style attacks**:
   1. Attackers compromised the vendor’s build system.
   2. Malicious code was inserted into legitimate updates.
   3. Customers trusted signed updates, so the backdoor spread widely.
4. For each incident type, focus on:
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

