# Security Development Lifecycle (SDL) Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for roles which require good understanding of secure SDLC / SDL.
Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be good at Security Development Lifecycle.
SDL is about building security into each phase of software delivery – from requirements and design to coding, testing, release, and maintenance – instead of treating security as a separate step at the end.

It is more towards:
- defining security activities and checkpoints in the SDLC,
- aligning developers, product, and security teams on expectations,
- integrating AppSec/DevSecOps/Product Security work into a repeatable process,
- and giving organizations a structured way to measure and improve security maturity.

Usually it will take you 6-12 weeks to be comfortable with SDL fundamentals and how to apply them in real projects.

## In short

1. SDL is not just a document – it is how security is embedded into the way software is built.
2. Think more of a framework that connects Application Security, DevSecOps, Product Security, and Architecture.
3. You should be comfortable talking about phases of SDLC and which security activities belong where.
4. You should know how to keep SDL practical for agile and cloud-native teams.
5. You must understand how to start small and evolve the SDL over time.

## ToC

1. [SDL Fundamentals](#sdl-fundamentals) - 1-2 weeks
2. [Security in Requirements and Design](#security-in-requirements-and-design) - 2-3 weeks
3. [Security in Implementation and Code Review](#security-in-implementation-and-code-review) - 2-3 weeks
4. [Security Testing and Verification](#security-testing-and-verification) - 2-3 weeks
5. [Release, Operations and Feedback](#release-operations-and-feedback) - 1-2 weeks
6. [Frameworks and Maturity Models](#frameworks-and-maturity-models) - 1-2 weeks
7. [Books](#books)
8. [Videos](#videos)
9. [Courses](#courses)
10. [Certifications](#certifications)
11. [Interview Questions](#interview-questions)

## SDL Fundamentals
**Duration: 1-2 weeks**

Goal here is to understand what SDL is trying to achieve.

### Week 1-2: The Big Picture
1. Review basic SDLC models:
   1. Waterfall vs iterative vs agile.
   2. How modern teams actually deliver (Scrum/Kanban, CI/CD).
2. Understand SDL goals:
   1. Reduce vulnerabilities introduced during development.
   2. Catch issues earlier when they are cheaper to fix.
   3. Provide traceability for security activities.
3. Read or refresh related plans:
   1. [Application Security Study Plan](application-security-study-plan.md)
   2. [DevSecOps Study Plan](devsecops-study-plan.md)
   3. [Product Security Study Plan](product-security-study-plan.md)
   4. [Security Architecture Study Plan](security-architecture-study-plan.md)

## Security in Requirements and Design
**Duration: 2-3 weeks**

Security must start before code is written.

### Week 3-5: Shift Left
1. Requirements phase:
   1. Define security and privacy requirements along with functional ones.
   2. Examples: authN/authZ, logging, encryption, data retention, compliance.
   3. Work with Product Security and GRC (if present) to capture constraints.
2. Design phase:
   1. Perform high-level architecture reviews.
   2. Do threat modeling for new features or major changes (see [Threat Modeling Study Plan](threat-modeling-study-plan.md)).
   3. Choose appropriate security patterns (e.g., gateway, zero trust, secure data flow).
3. Deliverables at this stage might include:
   1. Documented security requirements.
   2. Threat models and risk assessments.
   3. Architecture diagrams with security controls marked.

## Security in Implementation and Code Review
**Duration: 2-3 weeks**

Here you focus on day-to-day development activities.

### Week 6-8: Secure Build
1. Secure coding practices:
   1. Follow language-specific secure coding guidelines.
   2. Use frameworks and libraries securely.
2. Code review:
   1. Integrate basic security checks into regular code reviews.
   2. Use checklists for common security issues.
3. Automation:
   1. Introduce SAST and SCA as part of the build (see Application Security and DevSecOps plans).
   2. Ensure findings are triaged and assigned, not ignored.
4. Link to [Secure Code Review Study Plan](secure-code-review-study-plan.md) for deeper code review skills.

## Security Testing and Verification
**Duration: 2-3 weeks**

Testing must verify that controls are correctly implemented.

### Week 9-11: Verification
1. Unit and integration tests with security in mind where possible.
2. DAST / API testing for running apps and services.
3. Additional testing methods where relevant:
   1. IAST, fuzzing, penetration testing.
4. Non-functional aspects:
   1. Performance and reliability under attack conditions (e.g., rate limiting).
5. Ensure test results feed back into backlog and SDL metrics.

## Release, Operations and Feedback
**Duration: 1-2 weeks**

Security does not end at release.

### Week 12-13: Post-Release
1. Pre-release:
   1. Security sign-off criteria for high-risk features.
   2. Checklist to verify critical controls (auth, logging, encryption, etc.).
2. Operations:
   1. Secure configuration management.
   2. Monitoring and alerting for security-relevant events.
   3. Patch and vulnerability management (apps and infrastructure).
3. Feedback loop:
   1. Use incidents and pen test findings to improve earlier SDL phases.
   2. Regular retrospectives on security issues.

## Frameworks and Maturity Models
**Duration: 1-2 weeks**

Finally, understand how SDL ties into broader frameworks.

### Week 14-15: Maturity
1. OWASP SAMM (Software Assurance Maturity Model):
   1. High-level understanding of practice areas and maturity levels.
2. Microsoft SDL concepts (at a summary level).
3. How SDL relates to standards like ISO 27001, NIST, etc.
4. Use maturity models to:
   1. Assess current state.
   2. Plan incremental improvements.

## Books

1. Books on building Application Security or Product Security programs – for seeing how SDL is implemented in practice.
2. Any secure software development or secure coding books that tie into SDLC.

## Videos

1. [Developing Secure Software (LFD121)](https://training.linuxfoundation.org/training/developing-secure-software-lfd121/) by The Linux Foundation (free).
2. Conference talks on SDL / secure SDLC and how organizations implemented it in agile/DevOps environments.
3. Talks on OWASP SAMM and real-world program maturity journeys.

## Courses

1. Courses focused on secure software development or secure SDLC.
2. DevSecOps and Application Security courses that show how to integrate security into pipelines and processes.

## Certifications

1. [CSSLP: Certified Secure Software Lifecycle Professional](https://www.isc2.org/Certifications/CSSLP).
2. Other secure software development or AppSec/DevSecOps certifications depending on your focus.

## Interview Questions

You can reuse many questions from the Application Security and Product Security interview sets, but think of them through the SDL lens:

1. How would you introduce security into an existing agile SDLC with minimal disruption?
2. Which security activities would you recommend at each phase of the SDLC and why?
3. How would you measure whether your SDL is working and improving over time?

