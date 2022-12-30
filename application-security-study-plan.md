# Application Security Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for the job role.
Also, I assume you have already checked and comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be an Application Security Engineer. 
Application Security is different from Web Security or commonly people think it as offensive security or pentesting. Though it needs some concepts aligned with pentester but it's altogether a totally different skill sets.

It is more towards shift left security including Threat Modeling, Secure Code Review, Secure Code Design, of course OWASP Top 10 web and API security. I have another page specifically for ["API Security Study Plan"](api-security-study-plan.md) because that skill also needs good time to learn.

**In short:**

1. AppSec is not Pentesting or Web Security (people use it generically).
2. Think more of a combination of developer and attacker
3. Talking to developers, giving training to them or go through the code should not scare you.
4. Tougher than Pentesting (Topic of debate for another day)
5. Can write code for PoC, Exploit or demo with comfort
6. API security should be your areas of interest.

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
10. [Interview Quesitons](#interview-questions)
11. [Networking Matters](#networking-matters)
12. [Whom to follow on Twitter](#whom-to-follow-on-twitter)

## Web Application Concepts
This topic will have an overlap with the concepts required for Pentesting, but you have to now think more of a defender than offender.
Go with your pace, but make sure you understand the basic web security concepts very well like HTTP Security Response headers, Bruteforce, CSRF, Injection, JWT, Cryptography, Hashing, Encoding etc.

### Basics
1. Understanding of [various HTTP methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods), PUT vs POST, UPDATE vs PATCH, leverage OPTIONS method
2. Ability to [understand response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status).
   1. what if you got 200, when you tried something malicious
   2. what can we do if we get 403
   3. let's try to get 500 status code, and why so? What will it reveal.
   4. Try to understand each status code which as a pentester you would love to see.
3. Understand [HTTP headers very well](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers), specially response headers. You would need it more often while doing pentest.
4. TCP 3 way handshake
5. How SSL works
6. [Basics of security terminologies](https://github.com/jassics/cybersecurity-skills-career-roadmap/blob/master/cybersecurity-terminologies.md)
7. [Essentials Security Concepts](https://github.com/jassics/cybersecurity-skills-career-roadmap/blob/master/security-concepts.md)

### Security Concepts
You can find majority of the security concepts at [OWASP Cheatsheet](https://cheatsheetseries.owasp.org/index.html)

Understand the fundamental concepts on what it is, how it can be vulnerable and how you can eitehr epxloit it or mitigate it.
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

### Advance Level of application security skill sets
1. Very good at OWASP Top 10 for Web and API 
2. Go through OWASP Secure Code Review Guide, understand what to verify and how using this guide.
3. Very good at OWASP ASVS (Application Security Verification Standard), it's your job to make every developer aware about it and must use while development.
4. Go through OWASP Software Assurance maturity Model (OSAMM), if you aim for a security architect role.
5. Understand what causes BOLA and BFLA and try to be good at testing these vulnerabilities. 
6. Various weak cipher suites, how to test, how to make developers aware about it
7. [Authentication](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) and [Authorization](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html)
8. Advanced SQL Injection
9. [XML Injection](https://cheatsheetseries.owasp.org/cheatsheets/XML_Security_Cheat_Sheet.html), JSON Injection
10. Understand [SAML](https://cheatsheetseries.owasp.org/cheatsheets/SAML_Security_Cheat_Sheet.html) and LDAP Injection
11. NoSQL Injection
12. [GraphQL Injection](https://cheatsheetseries.owasp.org/cheatsheets/GraphQL_Cheat_Sheet.html)
13. [XXE Attacks](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html)
14. Template Injection
15. [Deserialization](https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet.html)
16. [CSP: Content Security Policy](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)

## Threat Modeling
Read [Threat Modeling Study Plan](threat-modeling-study-plan.md)

## Secure Code Review
Read [Secure Code Review](secure-code-review-study-plan.md)

## Cryptography
Read [Cryptography](cryptography-study-plan.md)

## Security Development Lifecycle (SDL)
Read [Security Development Lifecycle](security-development-lifecycle.md)

## Books
1. [Agile Application Security](https://www.amazon.in/Agile-Application-Security-Enabling-Continuous/dp/9352136292/)
2. [Application Security Program Handbook](https://www.manning.com/books/application-security-program-handbook)
3. [Writing Secure Code](https://www.amazon.in/Writing-Secure-Code-David-Leblanc/dp/0735617228/)
4. [The Tangled Web: A Guide to Securing Modern Web Applications](https://www.amazon.in/Tangled-Web-Securing-Modern-Applications/dp/1593273886)
5. [Alice and Bob Learn Application Security](https://www.amazon.in/Alice-Bob-Learn-Application-Security/dp/1119687357)  
6. [OWASP Code Review Guide](https://owasp.org/www-pdf-archive/OWASP_Code_Review_Guide_v2.pdf)

## Videos


## Courses
1. [Software Security on Coursera](https://www.coursera.org/learn/software-security)
2. [Cloud Application Security](https://www.coursera.org/learn/cloud-application-security)
3. [Application Security Guide - Udemy](https://www.udemy.com/course/application-security-the-complete-guide/)
4. [Sec522: Application Security: Securing Web Apps, APIs, and Microservices from SANS](https://www.sans.org/cyber-security-courses/application-security-securing-web-apps-api-microservices/) Really nice one but costly.

## Certifications
1. [CSSLP: Certified Secure Software Lifecycle Professional](https://www.isc2.org/Certifications/CSSLP) Recommended
2. [CASE: Certified Application Security Engineer](https://www.eccouncil.org/programs/application-security-training/) for Java and .NET professionals
3. [GWEB: GIAC Certified Web Application Defender](https://www.giac.org/certifications/certified-web-application-defender-gweb/)


## Interview Questions
[Possible Application Security interview questions](https://github.com/jassics/cybersecurity-skills-career-roadmap/blob/master/interview-questions/application-security-interview-questions.md) is shared at different github repo to keep it aligned with [career roadmap guide](https://github.com/jassics/cybersecurity-skills-career-roadmap).

## AppSec Tools
1. Checkmarx for SAST or HCL AppSCan (Previously it was IBM AppScan)
2. Snyk Code for SAST and Snyk Open Source for SCA
3. git-secrets or gitleaks or trufflehog to find out secrets
4. Inspec
5. OWASP Dependency Check is for SCA
6. Bandit for python code
7. Sonarqube for SAST with few plugins like findsecbugs
8. RetireJS for JS libraries
9. Contrast for IAST solution
10. Coverity from Snyopsys
11. You must not ignore **Burp Suite Pro**
12. Veracode
13. InSight from Rapid7

## Networking matters
Once you are on track and now understands the heat, it's time to:
1. Make some good LinkedIn contacts from application security domain
2. Find a mentor or follow someone who shares blogs, tutorials, talks on these topics.
3. Make connections through various security conference online/offline
4. Publish some good appsec articles, may be basic concepts, but you must publish. Choose medium.com or something of your choice.
5. Join webinars, conferences, newsletters.
6. Help someone who is still a beginner or struggling to understand appsec concepts. You will even learn better while guiding/helping others.

By the time you cover all these checklists, you will be already on a way to have a good start in web security job role. All the best!

## Whom to follow on twitter
Why twitter? Because you will see lots of security professionals very active here and sharing cool stuffs often.
1. [Jim Manico](https://twitter.com/manicode)
2. [Gyan Chawdhary](https://twitter.com/gunnu)
3. [Abhay Bhargav)](https://twitter.com/abhaybhargav)
4. [Inon Shkedy](https://twitter.com/InonShkedy)
5. [Chris Romeo](https://twitter.com/edgeroute)
6. [Tanya Janca](https://twitter.com/shehackspurple)
7. [Anant Shrivastava](https://twitter.com/anantshri)
8. [Defcon](https://twitter.com/defcon)
9. [Nullcon](https://twitter.com/nullcon)
10. [OWASP](https://twitter.com/owasp)

