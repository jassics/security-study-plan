# Application Security Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for the job role.
Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be an Application Security Engineer.
Application Security is different from Web Security or commonly people think it as offensive security or pentesting. Though it needs some concepts aligned with pentester, it's altogether a totally different skill set.

It is more towards shift left security including Threat Modeling, Secure Code Review, Secure Code Design, Training Developers, taking care of overall SDL process, and of course OWASP Top 10 web and API security. I have another page specifically for ["API Security Study Plan"](api-security-study-plan.md) because that skill also needs good time to learn.

## In short:

1. AppSec is not Pentesting (Penetration Testing) or [Web Security](web-pentest-study-plan.md) (people use it generically).
2. Think more of a combination of developer and attacker
3. Talking to developers, giving training to them or going through the code should not scare you.
4. Tougher than Pentesting (Topic of debate for another day)
5. Can write code for PoC, Exploit or demo with comfort
6. [API security](api-security-study-plan.md) should be your area of interest.
7. Good understanding of [Identity and Access Management (IAM)](iam-security-study-plan.md) will help for auth-related design and reviews.

Usually it will take you 6-12 months to be good at the Application Security fundamentals to get a job at entry level.

## ToC:
1. [Web Application Concepts](#web-application-concepts) - 6 weeks
2. [Threat Modeling](#threat-modeling) - 2-3 weeks
3. [Secure Code Review](#secure-code-review) - 6-8 weeks
4. [Cryptography](#cryptography) - 3 weeks
5. [Security Development Lifecycle (SDL)](#security-development-lifecycle) - 4 weeks
6. [Books](#books)
7. [Videos](#videos)
8. [Courses](#courses) - Try to complete at least 1-2 courses (1-2 months)
9. [Certifications](#certifications) - on your bandwidth and wish
10. [Interview Questions](#interview-questions)
11. [Application Security Tools](#appsec-tools)
12. [Whom to follow on X (formerly Twitter)](#whom-to-follow-on-x-formerly-twitter)

## Web Application Concepts
**Duration: 6 weeks**

This topic will have an overlap with the concepts required for Pentesting, but you have to now think more of a defender than offender.
Go with your pace, but make sure you understand the basic web security concepts very well like HTTP Security Response headers, Bruteforce, CSRF, Injection, JWT, Cryptography, Hashing, Encoding etc.

### Week 1-2: Basics
1. Understanding of [various HTTP methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods), PUT vs POST, UPDATE vs PATCH, leverage OPTIONS method
2. Ability to [understand response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status).
  1. what if you got 200, when you tried something malicious
  2. what can we do if we get 403
  3. let's try to get 500 status code, and why so? What will it reveal?
  4. Try to understand each status code which as a pentester you would love to see.
3. Understand [HTTP headers very well](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers), especially response headers. You would need it more often while doing pentest.
4. TCP 3 way handshake
5. How SSL works
6. [Basics of security terminologies](https://github.com/jassics/cybersecurity-skills-career-roadmap/blob/master/cybersecurity-terminologies.md)
7. [Essentials Security Concepts](https://github.com/jassics/cybersecurity-skills-career-roadmap/blob/master/security-concepts.md)

### Week 3-4: Security Concepts
You can find the majority of the security concepts at [OWASP Cheatsheet](https://cheatsheetseries.owasp.org/index.html)

Understand the fundamental concepts on what it is, how it can be vulnerable and how you can either exploit it or mitigate it.
1. Understanding how proper implementation of AuthN and AuthZ contribute to robust security. What can an attacker do to exploit it and how to mitigate/defend it
2. How session and cookies work and how it can be vulnerable, bypassed or even exploited
3. Understand how [session management](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html) can be more secured
4. In-depth understanding of XSS from both perspective exploit and mitigation
5. REST concepts like CRUD.
6. Different types of injections specially SQLi, RFI,LFI, RCE
7. Mass Assignment
8. Concepts like rate limit, bruteforce, replay attack, MITM, session fixation, session hijack, credential stuffing
9. CORS concepts
10. How can you prevent SSRF attacks
11. JWT Tokens in depth
12. Basic of encoding, decoding, hashing
13. Good understand of Cryptography and its implementation in application
14. SAST vs SCA

### Week 5-6: Advance Level of application security skill sets
1. Very good at [OWASP Top 10:2025](https://owasp.org/Top10/2025/) (current edition, announced Nov 2025 at Global AppSec DC, final release Jan 2026) and [OWASP Top 10 for API 2023](https://owasp.org/API-Security/editions/2023/en/0x11-t10/) (latest API edition)
   1. What changed from 2021: two new categories — **A03:2025 Software Supply Chain Failures** (widened from "Vulnerable and Outdated Components" to cover dependencies, build systems and distribution) and **A10:2025 Mishandling of Exceptional Conditions**. Broken Access Control stays at A01 and now absorbs SSRF; Security Misconfiguration climbs to A02. See also [Software Supply Chain Security Study Plan](software-supply-chain-security-study-plan.md) for A03 depth.
   2. [OWASP Top 10 for Web 2021](https://owasp.org/Top10/2021/) — **historical**, but still worth reading: a lot of tooling, training material and interview questions are still written against the 2021 IDs, so you need to be able to translate between the two.
2. Go through [OWASP Secure Code Review Guide](https://owasp.org/www-pdf-archive/OWASP_Code_Review_Guide_v2.pdf), understand what to verify and how to use this guide.
3. Very good at [OWASP ASVS 5.0.0](https://github.com/OWASP/ASVS/releases/download/v5.0.0_release/OWASP_Application_Security_Verification_Standard_5.0.0_en.pdf) (Application Security Verification Standard, released 30 May 2025 — [project page](https://owasp.org/www-project-application-security-verification-standard/)), it's your job to make every developer aware about it and must use while development.
   1. What changed in 5.0: ~350 requirements across 17 chapters (down from 4.0's count, heavily deduplicated); the old V1 Architecture chapter was dissolved into the topic chapters; new chapters for Web Frontend Security, Self-Contained Tokens (JWT etc.), OAuth/OIDC and WebRTC; cryptography guidance updated with post-quantum considerations; password rules realigned to NIST SP 800-63; L1 streamlined for easier adoption.
4. Go through [OWASP Software Assurance maturity Model](https://owaspsamm.org/model/) (OSAMM), if you aim for a security architect role.
5. Understand what causes [BOLA](https://www.traceable.ai/blog-post/a-deep-dive-on-the-most-critical-api-vulnerability-bola-broken-object-level-authorization) and [BFLA](https://securityboulevard.com/2021/07/api-security-101-broken-function-level-authorization/) and try to be good at testing these vulnerabilities.
6. Various weak cipher suites, how to test, how to make developers aware about it
7. [Authentication](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) and [Authorization](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html)
8. Advanced SQL Injection
9. [XML Injection](https://cheatsheetseries.owasp.org/cheatsheets/XML_Security_Cheat_Sheet.html), JSON Injection
10. Understand [SAML](https://cheatsheetseries.owasp.org/cheatsheets/SAML_Security_Cheat_Sheet.html) and LDAP Injection
11. NoSQL Injection
12. [GraphQL Injection](https://cheatsheetseries.owasp.org/cheatsheets/GraphQL_Cheat_Sheet.html)
13. [XXE Attacks](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html)
14. [Server-side Template Injection](https://portswigger.net/web-security/server-side-template-injection)
15. [Deserialization](https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet.html)
16. [CSP: Content Security Policy](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)

## Threat Modeling
Read [Threat Modeling Study Plan](threat-modeling-study-plan.md)

## Secure Code Review
Read [Secure Code Review](secure-code-review-study-plan.md)

## Cryptography
Read [Cryptography](cryptography-study-plan.md)

## Security Development Lifecycle (SDL)
Read [Security Development Lifecycle](secure-software-development-lifecycle-study-plan.md)

## Mobile Application Security
If you work with mobile apps (Android/iOS), also check the [Mobile Application Security Study Plan](mobile-application-security-study-plan.md).

## AI-Assisted and "Vibe-Coded" Development
Most code you review from 2025 onwards is at least partly generated by an AI coding assistant, and that shifts the AppSec threat model in ways worth planning for:

1. **Volume and review pressure** — far more code lands per developer per sprint, so manual review does not scale; your leverage moves to guardrails in CI, secure defaults in frameworks/templates, and paved-road libraries rather than case-by-case review.
2. **Repeated, patterned defects** — assistants reproduce whatever pattern they were trained on, so a single insecure idiom (string-concatenated SQL, disabled TLS verification, hand-rolled auth checks, hardcoded secrets in examples) shows up across many files instead of once. Fix the pattern and the prompt/rule set, not just the instance.
3. **Missing security requirements** — a feature prompted into existence usually has no threat model and no non-functional security requirements behind it. Push security requirements into the prompt/PRD stage instead of finding them at review time.
4. **New trust boundaries in your own toolchain** — the assistant, its extensions/MCP servers and the packages it suggests are now part of your build path. Untrusted content the assistant reads (an issue, a doc, a dependency's README) can influence what it writes: treat that as an injection surface, and treat a hallucinated or attacker-registered package name as a supply chain risk (see [Software Supply Chain Security Study Plan](software-supply-chain-security-study-plan.md)).
5. **The application itself may be AI-backed** — if the app calls an LLM, does RAG, or runs agents/tools, the AppSec threat model has to extend to prompt injection, excessive agency and output handling.

Don't learn this from this page — go to the dedicated plans:
- [GenAI Security Study Plan](genai-security-study-plan.md) for LLM/agentic threats, OWASP Top 10 for LLM and Agentic Applications, and AI-assistant/toolchain security.
- [Secure Code Review Study Plan](secure-code-review-study-plan.md) for how to review AI-generated code and where to place automation.
- [Threat Modeling Study Plan](threat-modeling-study-plan.md) for shifting requirements earlier, before the code is generated.

## Books
1. [Agile Application Security](https://www.amazon.in/Agile-Application-Security-Enabling-Continuous/dp/9352136292/)
2. [Application Security Program Handbook](https://www.manning.com/books/application-security-program-handbook)
3. [Writing Secure Code](https://www.amazon.in/Writing-Secure-Code-David-Leblanc/dp/0735617228/)
4. [The Tangled Web: A Guide to Securing Modern Web Applications](https://www.amazon.in/Tangled-Web-Securing-Modern-Applications/dp/1593273886)
5. [Alice and Bob Learn Application Security](https://www.amazon.in/Alice-Bob-Learn-Application-Security/dp/1119687357) 
6. [OWASP Code Review Guide](https://owasp.org/www-pdf-archive/OWASP_Code_Review_Guide_v2.pdf)

## Videos
1. [Introduction to Application Security](https://www.youtube.com/watch?v=4shFba3eRAc)
2. [Scaling your AppSec Program with semgrep](https://www.youtube.com/watch?v=rAwxFw25x3E)
3. [Building an AppSec Program from the ground up by Snyk](https://www.youtube.com/watch?v=hYcMynC0f_M)
4. [Application Security - Understanding, Exploiting and Defending against Top Web Vulnerabilities by Cerner](https://www.youtube.com/watch?v=sY7pUJU8a7U)
5. [Securing Web Application](https://www.youtube.com/watch?v=WlmKwIe9z1Q)
6. [Web Application Security: 10 things developers need to know](https://www.youtube.com/watch?v=qjrkV4RjgIU)
7. [Application Security from SANS Institute](https://www.youtube.com/watch?v=T_nyN24QjEY)

## Courses
1. [Software Security on Coursera](https://www.coursera.org/learn/software-security)
2. [Cloud Application Security](https://www.coursera.org/learn/cloud-application-security)
3. [Application Security Guide - Udemy](https://www.udemy.com/course/application-security-the-complete-guide/)
4. [Sec522: Application Security: Securing Web Apps, APIs, and Microservices from SANS](https://www.sans.org/cyber-security-courses/application-security-securing-web-apps-api-microservices/) Really nice one but costly.
5. [Free OWASP Top 10 practice from Kontra Security](https://application.security/free/owasp-top-10)

## Certifications
1. [CSSLP: Certified Secure Software Lifecycle Professional](https://www.isc2.org/Certifications/CSSLP) Recommended
2. [CASE: Certified Application Security Engineer](https://www.eccouncil.org/programs/application-security-training/) for Java and .NET professionals
3. [GWEB: GIAC Certified Web Application Defender](https://www.giac.org/certifications/certified-web-application-defender-gweb/)


## Interview Questions
[Possible Application Security interview questions](https://github.com/jassics/security-interview-questions/blob/main/application-security-interview-questions.md) is shared at different github repo to keep it aligned with [career roadmap guide](https://github.com/jassics/security-skills-career-roadmap).

## AppSec Tools
1. Checkmarx for SAST or HCL AppSCan (Previously it was IBM AppScan)
2. Snyk Code for SAST and Snyk Open Source for SCA
3. [git-secrets](https://git-secret.io/) or [gitleaks](https://github.com/zricethezav/gitleaks) or [trufflehog](https://github.com/trufflesecurity/trufflehog) to find out secrets
4. [Chef Inspec](https://docs.chef.io/inspec/)
5. [OWASP Dependency Check](https://github.com/jeremylong/DependencyCheck) is for SCA
6. [Bandit for python code](https://bandit.readthedocs.io/en/latest/)
7. [Sonarqube for SAST](https://www.sonarsource.com/products/sonarqube/) with few plugins like [findsecbugs](https://github.com/find-sec-bugs/find-sec-bugs)
8. [RetireJS for JS libraries](https://retirejs.github.io/retire.js/)
9. [Contrast for IAST solution](https://www.contrastsecurity.com/contrast-assess)
10. [Coverity from Snyopsys](https://scan.coverity.com/)
11. You must not ignore **[Burp Suite Pro](https://portswigger.net/burp/pro)**
12. [Veracode](https://www.veracode.com/)
13. [InSight from Rapid7](https://www.rapid7.com/products/insight-platform/)

## Whom to follow on X (formerly Twitter)
Why? Because you will see lots of security professionals active here and sharing cool stuff often. Note that since the 2023 rebrand to X, a good number of AppSec folks have moved most of their posting to LinkedIn, Bluesky or Mastodon — the handles below are the same names to look for on those platforms too, so follow them wherever they are actually posting.
1. [Jim Manico](https://x.com/manicode)
2. [Gyan Chawdhary](https://x.com/gunnu)
3. [Abhay Bhargav](https://x.com/abhaybhargav)
4. [Inon Shkedy](https://x.com/InonShkedy)
5. [Chris Romeo](https://x.com/edgeroute)
6. [Tanya Janca](https://x.com/shehackspurple)
7. [Anant Shrivastava](https://x.com/anantshri)
8. [Sanjeev Jaiswal](https://x.com/jassics)
9. [Defcon](https://x.com/defcon)
10. [Nullcon](https://x.com/nullcon)
11. [OWASP](https://x.com/owasp)
