# GCP Security Study Plan
I am making the study plan irrespective of job role under GCP Security category. It can be Cloud Security Analyst, Cloud Security Researcher or Cloud Security Engineer or Cloud Security Operations Expert or Cloud Security Manager or Cloud Governance.

So, check how much you can cover and learn practically. The more you are good at these concepts, the better candidate you are for the job role.
Also, I assume you have already checked and comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

## GCP Security Skills Learning and Checklist
My only suggestion here is ask below 4 questions while learning each topic/concepts etc.
1. What is this? (For example: What is instance group, where it is used and why?)
2. Why am I learning this specific service or concept now? Will it help me for my job role and in future?
3. How can I implement this? (Practical aspects, hands-on knowledge always have an extra edge)
4. How it will make secure or how to make it secure depending upon the topic or concept?

### GCP Fundamentals (2-3 weeks)
I am listing only the topic name with few lines and possibly some examples. How much you learn and comfortable with the concept or topic is upon you. 
And I will share the minimal link to make you up to the mark and you are free to learn anything more than this for better candidacy and experience.

### Week 1: IAM Deep Dive
It's very important topic for any cloud role. Try to understand it practically as much as your job demands.
1. [Start with GCP IAM official doc](https://cloud.google.com/iam/docs/overview)
2. [Understand IAM roles and permissions is 2nd important thing to excel in IAM concepts](https://cloud.google.com/iam/docs/roles-overview)
3. User, Group, Roles and when to use when and don't forget to ask why this, why not that
4. Custom role vs Google Managed role
5. Cross-Account IAM policy to different roles, services, account
6. Understand the IAM policy from security mindset. Why this, why not this?
7. [Using IAM Securely](https://cloud.google.com/iam/docs/using-iam-securely)

### Week 2-3: Core Services
**For any GCP Service(s), please follow this strategy:**
1. What does this service do?
2. What problem it would solve for the business?
3. Security Best Practices guide for GCP services. Ex: GCS security best practices, VPC security best practices.
4. What permissions you should provide for each role or principal or service account to maintain the least privilege principle.
5. How it is being used, can there be some security misconfiguration if not configured properly.
6. Is multi-tier, multi region required for this service?
7. How data at rest and data in transit can be achieved?
8. Is logging required? If so, how are you going to log and what data and till what period
9. Are we monitoring it? what's the reason for Yes or No?
10. Any specific security settings for that service like Bucket Permissions for specific GCS bucket

**Key Services to Cover:**
1. GCS (Google Cloud Storage)
2. GKE
3. VPC (Virtual Private Cloud)
4. Firewall Rules and policies
5. Load Balancer
6. Cloud DNS
7. Cloud CDN
8. Google Cloud Armor
9. Google Cloud Logging
10. BigQuery
11. API Gateway
12. Certificate Manager
13. Secrets Manager
14. Cloud Run
15. Cloud Function

## GCP Native Security skills
**Duration: 4-6 weeks**

What I mean to say here is:
1. GCP core services related to security
2. GCP Security services hands-on knowledge

### Week 4-6: Core Services Security
**These are the core services:**
1. IAM, super important
2. Compute Instances
3. GCS (Storage Object)
4. VPC, I feel it as the toughest one so far apart from GKE
5. CloudSQL (RDS)
6. Bigtable (NoSQL)
7. API Gateway
8. GKE
9. Cloud Run
10. Cloud Function
11. Cloud Composer
12. BigQuery
13. DataStore
14. DataProc
15. Secret manager
16. Cloud Key Management

### Week 7-9: Security Services Hands-on
**Below are GCP Core Security services that you should know and try hands-on as much as possible:**
1. IAM Policy Analyzer
2. IAM Organization Policies
3. [Security Command Center (SCC)](https://cloud.google.com/security/products/security-command-center) - Google Cloud's CSPM/CNAPP layer. Beyond basic misconfiguration findings, learn:
   - **Attack path simulation**, enabled by default in the Premium tier, which scores findings by how exploitable they actually are toward high-value resources instead of by raw severity.
   - **Gemini-assisted investigation** - natural-language summaries of findings and attack paths, so you can ask what a finding means and what to do next rather than reading raw JSON. See [Gemini in Google SecOps](https://docs.cloud.google.com/chronicle/docs/secops/gemini-chronicle).
   - **[AI Protection](https://docs.cloud.google.com/security-command-center/docs/ai-protection-overview)** - inventory and risk posture for AI workloads: models, data sources, endpoints, agents and **MCP servers**, plus detection of over-privileged agents. Very relevant if your org is shipping GenAI on Google Cloud.
   - Track new capabilities in the [SCC release notes](https://docs.cloud.google.com/security-command-center/docs/release-notes).
4. **[Google Security Operations (Google SecOps)](https://cloud.google.com/security/products/security-operations)** - this is the SIEM/SOAR/threat-intel platform **formerly called Chronicle**. Chronicle Security Operations was rebranded to Google Security Operations on 25 April 2024, so older blogs, courses and job descriptions still say "Chronicle" - know that they mean the same platform. Note that documentation URLs are still under `/chronicle/`.
   - Learn UDM (Unified Data Model), ingestion and parsers, YARA-L 2.0 detection rules, and retrohunts.
   - Learn the [Gemini integration in SecOps](https://docs.cloud.google.com/chronicle/docs/secops/gemini-chronicle): natural-language search over your telemetry, AI-generated case/investigation summaries, and assisted detection-rule authoring.
5. **[Google Cloud Armor](https://cloud.google.com/security/products/armor)** - the edge WAF and DDoS layer. Cover:
   - Preconfigured WAF rules (OWASP ModSecurity CRS-based), custom rules in **CEL**, and rule tuning/sensitivity levels.
   - **Adaptive Protection** - ML-based detection of L7 volumetric attacks with suggested rules.
   - Rate limiting and throttling, bot management with reCAPTCHA integration, and edge security policies for Cloud CDN/Cloud Storage.
   - Cloud Armor is now packaged as part of **Global Front End Enterprise** alongside global Cloud Load Balancing, Cloud CDN and Service Extensions - be aware of the packaging when reading current Google Cloud docs.
6. [Sensitive Data Protection](https://cloud.google.com/security/products/sensitive-data-protection) (formerly Cloud DLP) - another rebrand to be aware of.
7. [Assured Workloads](https://cloud.google.com/security/products/assured-workloads) and VPC Service Controls - data-boundary and exfiltration controls.

## GCP Security Whitepapers
**Duration: 2 weeks**

GCP has awesome lists of whitepapers related to GCP Security. We are adding few important one here. You can anytime check more for updated or new security whitepapers at the [Cloud Security Best Practices Center](https://cloud.google.com/security/best-practices)

### Week 10-11: Reading & Analysis
1. [GCP Overview](https://cloud.google.com/docs/overview) - One of the important whitepapers to understand an overview of GCP
2. [Introduction to GCP Security Whitepaper](https://cloud.google.com/static/docs/security/overview/resources/google_security_wp.pdf)
3. [Google Cloud Security Foundation Guide](https://services.google.com/fh/files/misc/google-cloud-security-foundations-guide.pdf)
4. [GCP Well-Architected Security Pillar](https://cloud.google.com/architecture/framework/security)
5. [Risk Governance of Digital Transformation](https://services.google.com/fh/files/misc/risk-governance-of-digital-transformation.pdf)
6. [Google Cloud recommended security checklist](https://cloud.google.com/blog/products/identity-security/introducing-the-google-cloud-recommended-security-checklist) - official tiered checklist of 60 controls across six domains (authentication/authorization, organization resource management, infrastructure resource management, data protection, network security, and monitoring/logging/alerting), grouped Basic / Intermediate / Advanced. Pair it with the [Google Cloud security best practices catalog](https://cloud.google.com/docs/security/security-best-practices-catalog) and the [Cloud Security Best Practices Center](https://cloud.google.com/security/best-practices)
7. [Google Infrastructure Security Design Overview](https://cloud.google.com/static/docs/security/infrastructure/design/resources/google_infrastructure_whitepaper_fa.pdf)
8. [NIST Cybersecurity Framework in the GCP cloud](https://services.google.com/fh/files/misc/gcp_nist_cybersecurity_framework.pdf)
9. [NIST 800-144 Security and Privacy in Public Cloud Computing](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-144.pdf)

## Check your GCP Pentesting Skills
**Duration: 2-3 weeks**

### Week 12-14: Practical Labs
1. A Damn Vulnerable GCP Infrastructure [GCPGoat](https://github.com/ine-labs/GCPGoat)
2. Try out the scenarios in [Cloud Goat](https://github.com/RhinoSecurityLabs/cloudgoat)
3. [GCP Pentest Labs](https://github.com/lacioffi/GCP-pentest-lab/)
4. [GCP Pentesting](https://cloud.hacktricks.xyz/pentesting-cloud/gcp-security)

## Check your Knowledge against common security benchmark and frameworks.
1. **CIS Google Cloud Platform Foundation Benchmark v5.0.0** (published May 2026). You can download the pdf version from [here](https://www.cisecurity.org/benchmark/google_cloud_computing_platform). Note that CIS also publishes separate **CIS GKE Benchmark v2.0.0** and **CIS GKE Autopilot Benchmark v2.0.0** - if you run GKE, the Foundation benchmark alone is not enough.
2. [CSA Cloud Matrix and STAR Framework](https://cloudsecurityalliance.org/download/artifacts/cloud-controls-matrix-v4/)
3. [NIST CSF for GCP](https://services.google.com/fh/files/misc/gcp_nist_cybersecurity_framework.pdf) - NIST CSF 2.0 (February 2024) is the current framework version, so cross-check anything in this mapping that predates it
4. [ISO/IEC 27017](https://www.iso.org/standard/82878.html) - cloud-specific controls built on ISO/IEC 27002, for both cloud customers and providers. Current edition is ISO/IEC 27017:2026 (revising the 2015 edition); it is a paid standard, so use the official ISO page rather than a random mirror

## GCP Security Videos and Courses
1. [GCP Cloud Security Features](https://www.youtube.com/watch?v=83IwaIaBRRU)
2. [GCP Full Course from Intellipat](https://www.youtube.com/watch?v=cwpbY4wJMBs)
3. [Google Cloud Security Fundamentals - Level 1](https://www.youtube.com/watch?v=9Bx_cqpJDpI)
4. [Managing Secuirty in Google Cloud](https://www.cloudskillsboost.google/course_templates/21)

## GCP Security Interview Questions
I have a _[separate repo for GCP Security interview questions](https://github.com/jassics/security-interview-questions/blob/main/gcp-security-interview-questions.md)._ I will keep it updated time to time. You can **star** it or **[fork it](https://github.com/jassics/security-interview-questions/fork).** 
