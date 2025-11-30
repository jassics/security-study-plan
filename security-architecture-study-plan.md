# Security Architecture Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for the job roles which require good knowledge of security architecture.
Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be a Security Architect / Security Architecture-focused engineer.
Security Architecture is different from just "doing AppSec" or "doing pentesting". You need to understand how to design secure systems end-to-end across applications, infrastructure, cloud, data, and identities.

It is more towards:
- defining guardrails and reference architectures,
- driving secure design decisions early,
- aligning with frameworks and standards,
- and working closely with AppSec, Cloud, Infrastructure and GRC teams.

Usually it will take you 6-12 months to be good at the Security Architecture fundamentals to get a job at entry level or move laterally into an architect-type role.

## In short:

1. Security Architecture is not only pentesting or only AppSec.
2. Think more of a combination of engineer, designer, and risk manager.
3. Talking to engineering leaders, architects, product owners, and GRC teams should not scare you.
4. You must be comfortable with diagrams, data flows, and threat modeling.
5. You should understand both on‑prem and cloud architectures (at least one major CSP).
6. You should be able to review designs and propose secure patterns with confidence.

## ToC:
1. [Security Architecture Fundamentals](#security-architecture-fundamentals) - 4-6 weeks
2. [Frameworks, Standards and Models](#frameworks-standards-and-models) - 3-4 weeks
3. [Designing Secure Architectures](#designing-secure-architectures) - 4-6 weeks
4. [Threat Modeling and Risk Management](#threat-modeling-and-risk-management) - 3-4 weeks
5. [Secure SDLC and Architecture Governance](#secure-sdlc-and-architecture-governance) - 3-4 weeks
6. [Reference Architectures and Patterns](#reference-architectures-and-patterns) - 3-4 weeks
7. [Books](#books)
8. [Videos](#videos)
9. [Courses](#courses)
10. [Certifications](#certifications)
11. [Interview Questions](#interview-questions)

## Security Architecture Fundamentals

Goal here is to understand what security architecture means and where it fits in the overall security program.

1. Understand the role of a Security Architect vs AppSec Engineer vs Cloud Security Engineer vs GRC.
2. Understand high-level components of modern systems:
   1. Applications / microservices
   2. APIs and integration layers
   3. Databases and data stores
   4. Identity and access management
   5. Network and perimeter controls
   6. Observability and logging
3. Learn to read and create architecture diagrams (C4 model basics, context/container/component diagrams).
4. Understand core security goals (CIA, authenticity, non-repudiation, privacy by design, least privilege, defense in depth).
5. Map typical attack surfaces on these diagrams.

You will use these fundamentals in almost every other section.

## Frameworks, Standards and Models

You don't need to memorize everything, but you should know **what exists**, **when to use it**, and **where to look**.

1. High-level security architecture frameworks
   1. SABSA (Sherwood Applied Business Security Architecture) – concept of business-driven security architecture
   2. TOGAF and how security fits into enterprise architecture
   3. NIST Cybersecurity Framework (CSF) at a high level
2. Technical standards and guidelines that influence architecture
   1. NIST 800-53 / NIST 800-171 basics
   2. ISO 27001 controls at a high level
   3. CIS Controls v8 (mapped to architecture capabilities)
3. Application- and cloud-focused standards
   1. [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/)
   2. [OWASP SAMM](https://owaspsamm.org/)
   3. CSP-specific well-architected frameworks (AWS, Azure, GCP)

Try to understand how these frameworks translate into **concrete architecture requirements** (e.g. logging, segmentation, encryption, IAM, backups, resilience).

## Designing Secure Architectures

Focus on how you design secure solutions from the start.

1. Network and segmentation concepts
   1. DMZs, zero trust network concepts, micro‑segmentation
   2. North-south vs east-west traffic
2. Identity and access architecture
   1. Central IdP, SSO, SAML/OIDC, MFA
   2. RBAC/ABAC, least privilege, just‑in‑time access
3. Data security architecture
   1. Data classification
   2. Encryption in transit and at rest, key management (KMS/HSM basics)
   3. Tokenization, masking, and pseudonymization
4. Application and API architecture
   1. High-level overview of secure web and API architectures
   2. (Deep API details are covered in [API Security Study Plan](api-security-study-plan.md))
5. Resilience and availability
   1. Redundancy, failover, backups and restore
   2. Designing for DDoS and capacity

Try to pick one or two small systems (side project, home lab, or existing app at work) and **draw** the "as‑is" and "to‑be" secure architecture.

## Threat Modeling and Risk Management

Here, you combine architecture diagrams with attacker thinking.

1. Read [Threat Modeling Study Plan](threat-modeling-study-plan.md).
2. Learn at least one methodology:
   1. STRIDE
   2. Attack trees or kill chain style
3. Learn how to:
   1. Identify assets, trust boundaries, and entry points
   2. Identify threats and abuses for each component
   3. Prioritize using simple risk scoring (likelihood x impact)
   4. Propose architectural mitigations and compensating controls

Repeat this for at least 3–4 different architectures:
- Simple 3‑tier web app
- Public APIs with mobile/SPA client
- Internal line-of-business application

## Secure SDLC and Architecture Governance

Security architecture is effective only if it is built into the way software is delivered.

1. Revisit [Security Development Lifecycle (SDL) Study Plan](secure-software-development-lifecycle-study-plan.md).
2. Understand where security architects engage in SDLC:
   1. Requirement and design reviews
   2. Architecture review boards / design review checklists
   3. Threat modeling as part of design
   4. Sign-off criteria and security non-functional requirements
3. Learn common architecture governance practices:
   1. Reference architectures and reusable patterns
   2. Exception management and technical debt tracking
   3. Security standards, baselines, and guardrails

## Reference Architectures and Patterns

Look for and collect **reference architectures** for typical environments:

1. On‑prem or hybrid architectures
   1. DMZ, VPN, identity, central logging, SIEM, bastion hosts
2. Cloud architectures
   1. Secure VPC/VNet design
   2. Internet‑facing vs private services
   3. Centralized logging, monitoring, and alerting
3. Common patterns
   1. Zero Trust style access to internal apps
   2. Secure API gateway pattern
   3. Secure data pipeline / analytics architecture

Try to map each reference diagram to:
- which controls are enforced where, and
- how attacks would flow through the system.

## Books

1. [Enterprise Security Architecture: A Business-Driven Approach](https://www.amazon.com/Enterprise-Security-Architecture-Business-Driven-Information/dp/1420091260)
2. [Agile Application Security](https://www.amazon.in/Agile-Application-Security-Enabling-Continuous/dp/9352136292/) – good for seeing how architecture and AppSec work together
3. [Security Engineering](https://www.cl.cam.ac.uk/~rja14/book.html) by Ross Anderson – classic reference on designing secure systems
4. [The Tangled Web: A Guide to Securing Modern Web Applications](https://www.amazon.in/Tangled-Web-Securing-Modern-Applications/dp/1593273886)

## Videos

1. Search for "Security Architecture" talks from OWASP, Black Hat, or RSA on YouTube.
2. Talks on threat modeling and secure design (many are linked from the [Threat Modeling Study Plan](threat-modeling-study-plan.md)).
3. Cloud provider "Well‑Architected" security deep‑dives (AWS, Azure, GCP official channels).

## Courses

1. Any good "Enterprise Security Architecture" or "Security Architecture and Design" course from trusted platforms.
2. Cloud security architecture courses from your preferred CSP (AWS, Azure, or GCP) – align with your cloud security plan.
3. Threat modeling and secure design courses (see Threat Modeling study plan for specific links).

## Certifications

1. [CSSLP: Certified Secure Software Lifecycle Professional](https://www.isc2.org/Certifications/CSSLP)
2. [CCSP: Certified Cloud Security Professional](https://www.isc2.org/Certifications/CCSP)
3. Vendor-specific cloud security or architecture certifications (AWS, Azure, GCP) depending on your focus.

## Interview Questions

You can use the [Application Security interview questions](https://github.com/jassics/security-interview-questions/blob/main/application-security-interview-questions.md) and think how you would answer them from an **architecture** perspective (design choices, trade‑offs, and patterns), and extend with:

1. How would you design a secure architecture for a public web application with APIs and mobile clients?
2. How would you design logging and monitoring for a critical payments system?
3. How would you approach threat modeling for a new microservices-based product?