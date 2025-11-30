# Product Security Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for the job roles which require good knowledge of Product Security.
Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be a Product Security Engineer / Product Security Lead.
Product Security is different from a pure "pentesting" role. It is closer to Application Security, but more embedded with product teams, helping them ship secure features quickly while balancing risk, user experience, and business goals.

It is more towards:
- enabling and coaching product & engineering teams,
- building and improving security into the product lifecycle,
- driving secure design, threat modeling, and remediation,
- partnering with AppSec, Cloud, and GRC to make security a feature of the product.

Usually it will take you 6-12 months to be good at the Product Security fundamentals to get a job at entry level or move laterally from AppSec/engineering into a Product Security role.

## In short:

1. Product Security is not only bug hunting or pentesting.
2. Think more of a combination of application security engineer, product engineer, and security program owner.
3. You work very closely with PMs, tech leads, architects, and developers.
4. You should be comfortable talking about risk, trade‑offs, and timelines.
5. You should know enough AppSec, Cloud, and SDLC to help teams make good decisions.
6. You must be able to translate technical issues into business impact and priorities.

## ToC:
1. [Product Security Fundamentals](#product-security-fundamentals) - 3-4 weeks
2. [Working with Product and Engineering](#working-with-product-and-engineering) - 2-3 weeks
3. [Secure SDLC in Product Teams](#secure-sdlc-in-product-teams) - 4-6 weeks
4. [Threat Modeling and Risk-Based Prioritization](#threat-modeling-and-risk-based-prioritization) - 3-4 weeks
5. [Metrics, Backlog and Communication](#metrics-backlog-and-communication) - 2-3 weeks
6. [Integrations with AppSec, Cloud and GRC](#integrations-with-appsec-cloud-and-grc) - 2-3 weeks
7. [Books](#books)
8. [Videos](#videos)
9. [Courses](#courses)
10. [Certifications](#certifications)
11. [Interview Questions](#interview-questions)

## Product Security Fundamentals

Goal here is to understand what Product Security is and where it sits between AppSec, engineering, and the rest of the security org.

1. Understand the role and responsibilities of Product Security:
   1. How it differs from Application Security, Security Architecture, and Pentesting.
   2. Typical responsibilities: partnering with product teams, reviewing designs, helping with threat modeling, triaging findings, guiding remediation.
2. Read or refresh:
   1. [Application Security Study Plan](application-security-study-plan.md)
   2. [API Security Study Plan](api-security-study-plan.md)
   3. [Security Architecture Study Plan](security-architecture-study-plan.md)
3. Understand the typical lifecycle of a feature in a product team:
   1. Idea / requirements
   2. Design
   3. Implementation
   4. Testing
   5. Release and monitoring
4. Map where Product Security can add value in each step.

## Working with Product and Engineering

Product Security is a **people and process** heavy role.

1. Learn how product management works:
   1. Basic concepts: product roadmap, backlog, epics, user stories.
   2. How priorities are decided (OKRs, business goals, customer requests).
2. Learn how engineering teams work:
   1. Agile / Scrum / Kanban basics.
   2. Sprint planning, stand‑ups, demos, retros.
3. Understand how to integrate security into these workflows:
   1. Security requirements in user stories.
   2. "Definition of done" including security checks.
   3. Security champions model in teams.
4. Practice communication:
   1. Explaining an issue in business terms.
   2. Proposing mitigations that fit within team constraints.
   3. Writing clear tickets and documentation.

## Secure SDLC in Product Teams

Here you focus on making the Secure SDLC **practical** for product teams.

1. Read [Security Development Lifecycle (SDL) Study Plan](secure-software-development-lifecycle-study-plan.md).
2. Map SDL activities to real product workflows:
   1. When to do security design reviews.
   2. When to run SAST/SCA/DAST/IAST and what to do with results.
   3. How to handle security sign‑off for high‑risk features.
3. Tools and automation (examples, not endorsements):
   1. SAST (e.g., tools mentioned in AppSec plan).
   2. SCA/Dependency scanning.
   3. Secret scanning.
   4. Container and IaC scanning.
4. Learn to define and roll out simple, opinionated security guardrails:
   1. Minimum controls per type of feature (auth, logging, encryption, rate limiting, etc.).
   2. Checklists for new services/APIs.
   3. Baseline for SDLC security activities.

## Threat Modeling and Risk-Based Prioritization

Threat modeling is a key part of Product Security.

1. Read [Threat Modeling Study Plan](threat-modeling-study-plan.md).
2. Practice at least one structured method (e.g., STRIDE or similar).
3. Focus on **practical** threat modeling in product teams:
   1. Short, facilitated sessions with the team.
   2. Using architecture diagrams and data flows.
   3. Capturing a small, actionable list of mitigations.
4. Learn risk-based prioritization:
   1. Simple risk scoring (likelihood x impact).
   2. Aligning with internal risk rating (e.g., Critical/High/Medium/Low).
   3. When to accept risk vs when to push for fixes.

## Metrics, Backlog and Communication

You also need to help leadership understand where the product stands.

1. Learn basic security metrics for product security, such as:
   1. Number of open security issues by severity and age.
   2. Mean time to remediate (MTTR) for different severities.
   3. Coverage of critical controls (e.g., auth, logging, encryption) across services.
2. Understand how to manage a security backlog:
   1. Grouping issues by theme.
   2. Balancing tactical fixes vs strategic improvements.
3. Practice reporting:
   1. Writing short monthly/quarterly updates.
   2. Showing trends instead of isolated numbers.
   3. Highlighting wins (reduced risk, improved coverage, closed gaps).

## Integrations with AppSec, Cloud and GRC

Product Security sits in the middle of several other teams.

1. With Application Security:
   1. Share findings and patterns across products.
   2. Reuse AppSec guidelines and standards.
   3. Coordinate on SAST/DAST/SCA and code review approaches.
2. With Cloud / Infrastructure Security:
   1. Understand cloud security baselines.
   2. Ensure product teams follow secure cloud patterns.
   3. Work together on network, IAM, and data protection.
3. With GRC / Compliance:
   1. Map product controls to policies and frameworks (e.g., ISO, SOC 2, GDPR).
   2. Help prepare for audits and customer security reviews.
   3. Turn compliance requirements into concrete product controls.

## Books

There is no single canonical "Product Security" book, but these are very useful:

1. [Application Security Program Handbook](https://www.manning.com/books/application-security-program-handbook)
2. [Agile Application Security](https://www.amazon.in/Agile-Application-Security-Enabling-Continuous/dp/9352136292/)
3. [Alice and Bob Learn Application Security](https://www.amazon.in/Alice-Bob-Learn-Application-Security/dp/1119687357)
4. Any good book on product management or working with product teams (to understand their language and priorities).

## Videos

1. Talks on building or scaling Product Security / AppSec programs (search recent OWASP/BSides/Black Hat talks).
2. Videos on secure SDLC and DevSecOps that emphasize working with product/engineering teams.
3. Threat modeling and secure design talks (linked from the Threat Modeling and Application Security study plans).

## Courses

1. Courses on building Application Security or Product Security programs from well‑known training providers.
2. DevSecOps / Secure SDLC courses that include integration with CI/CD and product workflows.
3. Threat modeling and architecture courses that show how to work with cross‑functional teams.

## Certifications

1. [CSSLP: Certified Secure Software Lifecycle Professional](https://www.isc2.org/Certifications/CSSLP)
2. Cloud security certifications (AWS/Azure/GCP) if your products are cloud‑native.
3. Application Security or DevSecOps‑oriented certifications, depending on your focus.

## Interview Questions

You can reuse many questions from the [Application Security interview questions](https://github.com/jassics/security-interview-questions/blob/main/application-security-interview-questions.md) but think about them in terms of **how you would embed security into product teams**.

Additional Product Security‑focused questions could be:

1. How would you integrate security into a team that ships features every 1–2 weeks?
2. How do you decide which security issues must be fixed before release and which can go into backlog?
3. How would you introduce threat modeling into a product team that has never done it before?
4. How would you communicate a critical security issue to product and engineering leadership?
