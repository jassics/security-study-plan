# Identity and Access Management (IAM) Security Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for job roles which require strong Identity & Access Management skills (AppSec, Cloud Security, Product Security, GRC, Security Architecture, etc.).

Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

It will cover what you need to learn to excel at IAM from both **application** and **cloud** perspectives.

**How this connects:** Use this plan alongside the [AWS](aws-security-study-plan.md), [Azure](azure-security-study-plan.md), and [GCP](gcp-security-study-plan.md) security study plans for cloud-specific IAM, and with the [Application Security](application-security-study-plan.md), [Security Architecture](security-architecture-study-plan.md), and [Security Development Lifecycle](secure-software-development-lifecycle-study-plan.md) study plans when you are designing or reviewing secure systems. For AI agent identity, delegated authorization and MCP token scoping, pair it with the [GenAI Security Study Plan](genai-security-study-plan.md).

---

## In short

1. IAM is not just “creating users and groups” – it is access control for everything.
2. Think of IAM as the **new perimeter** across apps, APIs, cloud, and SaaS.
3. You must be comfortable with AuthN/AuthZ concepts and common protocols.
4. You should understand how IAM is implemented in AWS, Azure, and GCP at a high level.
5. You should recognize common IAM misconfigurations and how to avoid them.
6. Most identities in your estate are **not human** — service accounts, workloads and AI agents. Non-human identity is the fastest-growing part of IAM, and the least governed.

---

## ToC

1. [IAM Fundamentals](#iam-fundamentals) - 2 weeks  
2. [Authentication (AuthN) Deep Dive](#authentication-authn-deep-dive) - 2 weeks  
3. [Authorization (AuthZ) & Access Control](#authorization-authz--access-control) - 2 weeks  
4. [Cloud Provider IAM (AWS/Azure/GCP)](#cloud-provider-iam-awsazuregcp) - 3-4 weeks  
5. [Identity Lifecycle, Privileged Access & Federation](#identity-lifecycle-privileged-access--federation) - 2-3 weeks  
6. [Non-Human Identity (NHI), Workload & AI Agent Identity](#non-human-identity-nhi-workload--ai-agent-identity) - 2-3 weeks  
7. [Threats, Misconfigurations & Hardening](#threats-misconfigurations--hardening) - 2-3 weeks  
8. [Books](#books)  
9. [Videos](#videos)  
10. [Courses](#courses)  
11. [Certifications](#certifications)  
12. [Interview Questions](#interview-questions)

---

## IAM Fundamentals

**Duration: 2 weeks**

Goal: build a solid mental model of IAM, identities, and access control.

### Week 1-2: Core Concepts

1. **What is IAM?**  
   - Digital identities, principals, subjects.  
   - Resources, permissions, policies.
2. **Types of Identities:**  
   - Human identities (users, groups).  
   - Machine / non-human identities (NHIs): service accounts, workloads, applications, CI/CD pipelines, API keys, certificates, bots.  
   - **AI agent identities:** an agent is not a normal service account — it acts autonomously, picks its own action plan at runtime, can spawn sub-agents, and calls tools/APIs on a user's behalf. Its permissions are effectively decided at runtime, not at provisioning time.  
   - **Delegated / impersonated identities:** OAuth delegated authorization (act-on-behalf-of), service accounts with domain-wide delegation, token exchange and impersonation chains. Learn to answer "who is actually accountable for this call?" for each pattern.  
   - External identities (partners, customers, B2B/B2C).  
   - Non-human credential lifecycle: issuance → scoping → rotation → attestation → revocation → decommissioning. Most orgs run this manually (or not at all) — see the [NHI section](#non-human-identity-nhi-workload--ai-agent-identity).
3. **Access Models:**  
   - Discretionary Access Control (DAC).  
   - Mandatory Access Control (MAC).  
   - Role-Based Access Control (RBAC).  
   - Attribute-Based Access Control (ABAC).  
4. **Core Principles:**  
   - Least privilege.  
   - Separation of duties.  
   - Zero Trust (never trust, always verify).  
   - Just-In-Time (JIT) and Just-Enough-Access (JEA).

---

## Authentication (AuthN) Deep Dive

**Duration: 2 weeks**

Goal: understand how we prove *who* a user or service is.

### Week 3: Traditional AuthN

1. **Credentials:** passwords, password policies, password managers.  
2. **Multi-Factor Authentication (MFA):** SMS, TOTP apps, FIDO keys.  
3. **Sessions & Cookies:** session IDs, secure flags, timeouts.

### Week 4: Modern Protocols

1. **OAuth 2.0 (high level):** roles (resource owner, client, auth server), grant types.  
2. **OpenID Connect (OIDC):** ID token, userinfo endpoint, common flows.  
3. **SAML 2.0 basics:** assertions, IdP vs SP, SSO scenarios.  
4. **Modern web/mobile auth patterns:** SPA, mobile apps using OAuth/OIDC.

---

## Authorization (AuthZ) & Access Control

**Duration: 2 weeks**

Goal: understand how we decide *what* a user or service is allowed to do.

### Week 5-6: AuthZ Models & Implementation

1. **RBAC:** roles, role hierarchies, role explosion problem.  
2. **ABAC:** policies based on attributes (user, resource, environment).  
3. **Policy Languages & Engines (high level):**  
   - XACML, OPA/Rego, custom JSON/YAML-based policies.  
4. **Application-Level Authorization:**  
   - Route/method-level access control.  
   - Object-level (BOLA) and function-level (BFLA) authorization.  
   - Mapping business roles to technical permissions.

---

## Cloud Provider IAM (AWS/Azure/GCP)

**Duration: 3-4 weeks**

Goal: understand how major cloud providers implement IAM.

### Week 7-8: AWS IAM Basics

1. **Core Concepts:** principals, policies, actions, resources, conditions.  
2. **Identity Types:** IAM users, groups, roles, root account.  
3. **Policies:** identity-based vs resource-based policies, SCPs (Organizations).  
4. **Common Services:** IAM, AWS SSO/IAM Identity Center, STS, KMS.  
5. **Hands-on (if possible):** create roles, attach policies, test access.

### Week 9: Azure & GCP IAM Overview

1. **Azure:** Entra ID (formerly Azure AD), roles, role assignments, scopes (MG → Sub → RG → Resource).  
2. **GCP:** IAM policies, members, roles, service accounts, resource hierarchy.

3. **Compare Patterns:**  
   - How roles and scopes differ across AWS/Azure/GCP.  
   - Common misconfigurations (overly broad roles, wildcard permissions).

---

## Identity Lifecycle, Privileged Access & Federation

**Duration: 2-3 weeks**

Goal: understand how identities are managed over time and across systems.

### Week 10-11: Identity Lifecycle & PAM

1. **Lifecycle:** joiner/mover/leaver processes.  
2. **Provisioning & Deprovisioning:** HR systems, directories, SCIM basics.  
3. **Privileged Access Management (PAM):**  
   - Break-glass accounts.  
   - Session recording and approvals.  
   - JIT privileged access.

### Week 12: Federation & B2B/B2C

1. **Federation Concepts:** trusting external IdPs, SSO across organizations.  
2. **Common Scenarios:** SAML or OIDC from corporate IdP to SaaS/cloud.  
3. **Security Considerations:** trust boundaries, token lifetimes, revocation.

---

## Non-Human Identity (NHI), Workload & AI Agent Identity

**Duration: 2-3 weeks**

Goal: cover the fastest-growing part of IAM — identities that are not people.

> [!NOTE]
> Non-human identities now vastly outnumber human ones, and vendor surveys disagree on *how* vastly: Palo Alto Networks' [2026 Identity Security Landscape](https://www.paloaltonetworks.com/idira/identity-security-landscape-report) reports **109 machine identities per human** (up from 82:1 in 2025, with ~79 of the 109 being AI agents), while other 2026 reports range from roughly 17:1 to 144:1 depending on how they count. Do not quote a single number as gospel — the point is the order of magnitude and the growth rate, and that AI agents are the fastest-growing category.

### Week 13-14: NHI Fundamentals & Controls

1. **What counts as an NHI:** service accounts, workload identities, API keys, OAuth client credentials, certificates, SSH keys, CI/CD tokens, webhooks, bots, and AI agents.
2. **Discovery & inventory:** you cannot govern what you cannot list. Learn how NHIs get created outside IAM (in code, in CI, in SaaS integrations, by developers wiring up an agent) and how to inventory them.
3. **Ownership & lifecycle:** every NHI needs a human owner, an expiry, and an offboarding path. Joiner/mover/leaver has a machine equivalent, and most orgs skip the "leaver" half.
4. **[OWASP Non-Human Identities Top 10 (2025)](https://owasp.org/www-project-non-human-identities-top-10/):** the canonical risk list — NHI1 Improper Offboarding, NHI2 Secret Leakage, NHI3 Vulnerable Third-Party NHI, NHI4 Insecure Authentication, NHI5 Overprivileged NHI, NHI6 Insecure Cloud Deployment Configurations, NHI7 Long-Lived Secrets, NHI8 Environment Isolation, NHI9 NHI Reuse, NHI10 Human Use of NHI. Learn these the way you learned the OWASP Top 10.
5. **Governance gap reading:** [CSA — The Non-Human Identity Governance Vacuum (2026)](https://labs.cloudsecurityalliance.org/research/csa-whitepaper-nonhuman-identity-agentic-ai-governance-v1-cs/) and the [CSA Agent Identity Governance Framework](https://labs.cloudsecurityalliance.org/agentic/agentic-identity-governance-framework-v1/).

### Week 15: Tooling & Modern Patterns

1. **Secrets management / vaulting for machine identity:** centralized vaults (HashiCorp Vault, AWS Secrets Manager, Azure Key Vault, GCP Secret Manager, CyberArk Conjur), dynamic/short-lived secrets, automatic rotation, and secret-scanning to catch what leaked before the vault existed.
2. **Workload identity federation (the secretless goal):** exchange a platform-issued, short-lived token for a cloud credential instead of storing a static key — GitHub Actions OIDC → AWS/GCP/Azure, EKS/GKE/AKS workload identity, Kubernetes projected service-account tokens. Static long-lived keys should be the exception you have to justify.
3. **[SPIFFE / SPIRE](https://spiffe.io/):** the open standard for workload identity — SPIFFE IDs and SVIDs (X.509 or JWT) issued by a [SPIRE](https://spiffe.io/docs/latest/spire-about/) runtime based on attested workload properties, enabling mTLS between services and cross-trust-domain federation without shared secrets. Also implemented in parts by Istio and Consul.
4. **NHI security platforms (category awareness):** NHI discovery/posture tools, machine-identity/certificate lifecycle management, and CIEM for entitlement right-sizing.
5. **Agent identity & delegated authorization:** the live gap area. Bearer tokens were designed for deterministic clients, so they no longer prove *user intent* when the client is an LLM agent. Do not re-derive this here — read the **Agent Identity & Delegated Authorization** notes under AI Agents in the [GenAI Security Study Plan](genai-security-study-plan.md#ai-agents), which cover why OAuth 2.0 breaks down, intent-bound delegation proposals like Agentic JWT, and per-tool token scoping for MCP.

**Hands-on:**
- Replace one long-lived cloud access key in a personal project with OIDC-based workload identity federation.
- Inventory every NHI in one repo/pipeline you own (tokens, keys, service accounts) and assign each an owner and an expiry.

---

## Threats, Misconfigurations & Hardening

**Duration: 2-3 weeks**

Goal: connect IAM theory with real-world attacks and defenses.

### Week 16-18: Attacks & Defenses

1. **Common IAM-related Attacks:**  
   - Credential stuffing, password spraying.  
   - MFA fatigue / MFA bypass social engineering.  
   - OAuth misconfig (open redirect, overbroad scopes).  
   - IDOR/BOLA/BFLA due to missing authorization checks.  
   - Privilege escalation via misconfigured roles/policies.
2. **Cloud IAM Pitfalls:**  
   - `*:*` permissions, public buckets, overly broad service roles.  
   - Long-lived access keys and secrets.  
3. **Non-Human & AI Agent Identity Threats:**  
   - **AI-agent credential sprawl:** every agent, sub-agent, tool integration and MCP server tends to get its own token — often minted ad hoc by developers, unowned, unrotated and untracked. Orphaned agent credentials are the machine equivalent of a leaver who kept their badge.  
   - **Runtime permission escalation:** an agent's effective permissions are the union of every tool it can reach, so it accumulates privilege at runtime rather than at provisioning time. Watch for confused-deputy abuse (attacker-controlled content steering an agent that holds broad delegated authority) and sub-agents inheriting more than the parent needed.  
   - **Secrets in agent memory and context:** API keys, tokens and PII pulled into prompts, conversation history, vector stores, scratchpad files or logs — then re-emitted to a downstream tool, another agent, or the model provider. Treat the context window as an untrusted, exportable data store.  
   - **Shared/reused NHIs:** one credential across many agents or environments destroys attribution and widens blast radius (OWASP NHI9, NHI8).  
   - **Human use of machine identities:** engineers borrowing service-account or agent credentials to bypass their own access controls (OWASP NHI10).  
4. **Hardening Practices:**  
   - Enforce MFA for admins and remote access.  
   - Regular access reviews and certification.  
   - Least privilege role design and periodic cleanup.  
   - Conditional access / risk-based authentication (where available).  
   - Extend access reviews to NHIs and AI agents: named owner, expiry, scoped-per-tool tokens, short-lived/federated credentials instead of static keys, and logging that records *which agent, on whose behalf* performed each action.

---

## Books

1. Any solid book on **Identity & Access Management** in enterprise or cloud contexts.  
2. Books on **OAuth 2.0 / OpenID Connect** and modern authentication patterns.  
3. Cloud security books that include strong IAM chapters (AWS/Azure/GCP).

---

## Videos

1. Conference talks on IAM, SSO, OAuth/OIDC pitfalls, and cloud IAM misconfigurations.
2. Cloud provider official IAM deep-dive videos (AWS re:Invent, Azure, GCP).  
3. Talks on Zero Trust and modern identity-centric security.

---

## Courses

1. Cloud security fundamentals courses with strong IAM modules.  
2. Vendor-specific identity courses (e.g., AWS, Azure, GCP IAM).  
3. Courses focused on OAuth 2.0 / OIDC and modern auth patterns.

---

## Certifications

1. Cloud security certifications (AWS/Azure/GCP) where IAM is a major part of the exam.  
2. Identity-focused or access management certifications if they align with your goals.  
3. General security certs (CISSP, CCSP, etc.) for broader context around IAM.

---

## Interview Questions

You can reuse questions from Application Security, Cloud Security, and Security Architecture, but focus on Identity & Access:

1. How would you design authentication and authorization for a new web/mobile app?  
2. How would you migrate on-prem identities to a cloud IdP safely?  
3. How do you enforce least privilege across many AWS accounts or Azure subscriptions?  
4. How would you investigate and respond to a suspected IAM credential compromise?  
5. How would you inventory and govern non-human identities across cloud, CI/CD and SaaS?  
6. How would you issue, scope and revoke credentials for an AI agent that calls internal APIs on a user's behalf — and how would you prove which action was taken on whose authority?  
7. Why do bearer tokens stop being sufficient evidence of user intent once the client is an autonomous agent?
