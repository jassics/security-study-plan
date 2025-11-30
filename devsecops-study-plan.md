# DevSecOps Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for the job roles which require good knowledge of DevSecOps.
Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be a DevSecOps Engineer / DevSecOps-focused security engineer.
DevSecOps is not just "adding security tools to CI/CD". It is about building security into how software is planned, built, tested, delivered, and operated – with as much automation and feedback as possible.

It is more towards:
- working closely with developers, SRE/DevOps, and AppSec,
- integrating security checks into pipelines and platforms,
- defining secure defaults and guardrails,
- enabling teams to ship fast **and** safely.

Usually it will take you 6-12 months to be good at the DevSecOps fundamentals to get a job at entry level or move laterally from AppSec/DevOps into a DevSecOps role.

## In short

1. DevSecOps is not a separate silo – it is how development, security, and operations work together.
2. Think more of a combination of developer, DevOps/SRE, and security engineer.
3. You should be comfortable with CI/CD systems, containers, and basic cloud concepts.
4. You should know enough Application Security to choose and tune the right checks.
5. Automation, feedback loops, and culture change are as important as tools.

## ToC

1. [DevSecOps Fundamentals](#devsecops-fundamentals) - 3-4 weeks
2. [CI/CD and Automation Basics](#cicd-and-automation-basics) - 3-4 weeks
3. [Security Testing in the Pipeline](#security-testing-in-the-pipeline) - 4-6 weeks
4. [Cloud, Containers and IaC Security](#cloud-containers-and-iac-security) - 4-6 weeks
5. [Platform Guardrails and Governance](#platform-guardrails-and-governance) - 3-4 weeks
6. [Metrics, Feedback and Culture](#metrics-feedback-and-culture) - 2-3 weeks
7. [Books](#books)
8. [Videos](#videos)
9. [Courses](#courses)
10. [Certifications](#certifications)
11. [Interview Questions](#interview-questions)

## DevSecOps Fundamentals

Goal here is to understand what DevSecOps is and what problems it tries to solve.

1. Understand the evolution:
   1. Dev → DevOps → DevSecOps.
   2. Why traditional "security at the end" does not work.
2. Read or refresh related study plans:
   1. [Application Security Study Plan](application-security-study-plan.md)
   2. [Security Development Lifecycle (SDL) Study Plan](secure-software-development-lifecycle-study-plan.md)
   3. Relevant cloud security study plan(s) (AWS/Azure/GCP) if you know your focus.
3. Understand the main DevSecOps goals:
   1. Shift security left (earlier in SDLC) and right (monitoring in production).
   2. Make security part of the delivery pipeline, not a blocking afterthought.
   3. Provide self-service security capabilities for product teams.
4. Know typical DevSecOps responsibilities:
   1. Designing and maintaining security checks in CI/CD.
   2. Working with platform/DevOps teams to define secure defaults.
   3. Helping AppSec/Product Security scale via automation.

## CI/CD and Automation Basics

You cannot do DevSecOps effectively without basic CI/CD understanding.

1. Learn one or two CI/CD platforms in depth (e.g., GitHub Actions, GitLab CI, Jenkins, Azure DevOps, CircleCI – depending on your environment).
2. Understand common pipeline stages:
   1. Build
   2. Unit/Integration tests
   3. Security tests
   4. Packaging and artifact management
   5. Deployment
3. Learn infrastructure around pipelines:
   1. Repositories and branching strategies.
   2. Environments (dev, test, stage, prod).
   3. Secrets management for pipelines.
4. Practice:
   1. Create a simple app and add a basic CI pipeline (build + tests).
   2. Then plan where security checks will be plugged in (SAST, SCA, etc.).

## Security Testing in the Pipeline

Here you focus on what kinds of security checks you can automate and where.

1. Static Application Security Testing (SAST)
   1. What it is good at and its limitations (false positives, language support).
   2. Where to run it in the pipeline (typically on pull request/merge).
   3. How to configure basic rules and quality gates.
2. Software Composition Analysis (SCA) / Dependency Scanning
   1. Why vulnerable dependencies are a big risk.
   2. License risks and SBOM basics.
   3. Automating dependency checks and upgrade workflows.
3. Secrets Detection
   1. Preventing API keys and passwords from being committed.
   2. Pre-commit hooks vs pipeline checks.
4. Dynamic Application Security Testing (DAST) and API testing
   1. Basic idea of black-box testing against running apps/APIs.
   2. Where in the delivery process to run it (e.g., pre-prod env).
5. Container and Image Scanning
   1. Base image vulnerabilities.
   2. Application packages inside containers.
   3. Integrating scanning into image build process.

You do not need to be an expert in every tool, but you should understand **which type of test** fits which risk and where in the pipeline it makes sense.

## Cloud, Containers and IaC Security

Most DevSecOps work today happens around cloud-native stacks.

1. Containers and orchestration:
   1. Basics of Docker (images, containers, Dockerfile).
   2. Basics of Kubernetes or your orchestration platform (pods, services, deployments, namespaces).
   3. Common container security risks (running as root, capabilities, image provenance).
2. Infrastructure as Code (IaC):
   1. Terraform, CloudFormation, ARM/Bicep, etc.
   2. Why IaC is powerful for repeatable, auditable infrastructure.
   3. Typical misconfigurations (open security groups, public buckets, missing encryption).
3. Cloud security baselines:
   1. Align with your cloud study plan(s) for core cloud security concepts.
   2. Understand provider-native security services (e.g., security center, config, guardrails).
4. DevSecOps role here:
   1. Integrate image and IaC scanning into pipelines.
   2. Enforce baseline policies via policy-as-code (e.g., OPA/Conftest, admission controllers).

## Platform Guardrails and Governance

DevSecOps is also about **secure platforms**, not only individual pipelines.

1. Understand platform engineering concepts:
   1. Internal developer platforms.
   2. Golden paths and templates.
2. Typical security guardrails:
   1. Standardized service templates with logging, monitoring, and security defaults.
   2. Centralized identity and access patterns.
   3. Network policies and ingress/egress controls.
3. Governance and approvals:
   1. When approval workflows are necessary.
   2. Automating checks so humans mainly handle exceptions.
4. Work with Product Security / AppSec / Cloud Security to define:
   1. Minimal controls all services must have.
   2. Exception handling and risk acceptance process.

## Metrics, Feedback and Culture

DevSecOps is as much about **people and feedback** as it is about tools.

1. Metrics you might track:
   1. Security findings per pipeline or service (and trends).
   2. MTTR for security issues.
   3. Adoption of security checks (percentage of services with SAST/SCA/etc.).
2. Feedback loops:
   1. Making scanner results visible and understandable to developers.
   2. Fast feedback on pull requests.
   3. Security office hours or help channels.
3. Culture and enablement:
   1. Security champions in teams.
   2. Training developers on interpreting and fixing findings.
   3. Keeping friction low – avoid turning tools into constant blockers.

## Books

1. Any solid DevOps/Continuous Delivery book to understand the base culture and practices.
2. Books on building Application Security programs (see Application Security plan) – useful for understanding what you are automating.
3. Books on cloud-native security and container security that include CI/CD viewpoints.

## Videos

1. Conference talks on DevSecOps (OWASP, DevOpsDays, KubeCon, etc.).
2. Videos showing real-world CI/CD security implementations.
3. Talks on security automation, policy-as-code, and platform engineering.

## Courses

1. DevSecOps-focused courses that cover CI/CD, automation, and security tooling.
2. Cloud-native security courses that include pipeline and platform topics.
3. Container and Kubernetes security courses that show how to integrate checks into pipelines.

## Certifications

1. Cloud security certifications related to your main cloud provider (AWS/Azure/GCP).
2. DevOps/Cloud-native certifications that cover CI/CD and containers.
3. Application Security or Secure SDLC certifications if you want to emphasize the security side.

## Interview Questions

You can reuse many questions from the [Application Security interview questions](https://github.com/jassics/security-interview-questions/blob/main/application-security-interview-questions.md) and from any cloud/security interviews, but focus on how you would **automate** and **integrate** security into pipelines and platforms.

Additional DevSecOps-focused questions could be:

1. How would you add security checks into an existing CI/CD pipeline without slowing teams down too much?
2. How do you decide which security tools to run on pull requests vs in nightly builds?
3. How would you integrate container and IaC scanning into the delivery process?
4. How would you measure the success of a DevSecOps initiative over 6–12 months?

