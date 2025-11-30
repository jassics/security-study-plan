# Docker Security Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for the job roles which require good knowledge of Docker and container security.
Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be good at Docker/container security.
Docker Security is a focused subset of cloud-native security and DevSecOps. You need to understand how images and containers work, what can go wrong, and how to build and run them securely across the SDLC.

It is more towards:
- building minimal and secure container images,
- understanding runtime hardening and isolation,
- integrating image scanning into CI/CD,
- and working with DevSecOps / Platform teams on secure base images.

Usually it will take you 4-8 weeks to be comfortable with Docker Security fundamentals, assuming you already know basic Docker usage.

## In short

1. Docker Security is not just running a scanner on images.
2. Think more of image hygiene + least privilege + secure defaults.
3. You should be comfortable writing and reviewing Dockerfiles.
4. You must understand how containers differ from VMs and what isolation they provide (and don’t).
5. You should know where Docker Security fits into DevSecOps and cloud security.

## ToC

1. [Docker and Container Fundamentals](#docker-and-container-fundamentals) - 1-2 weeks
2. [Image Build and Supply Chain Security](#image-build-and-supply-chain-security) - 1-2 weeks
3. [Runtime Hardening and Host Security](#runtime-hardening-and-host-security) - 1-2 weeks
4. [Scanning, Policies and CI/CD Integration](#scanning-policies-and-cicd-integration) - 1-2 weeks
5. [Books](#books)
6. [Videos](#videos)
7. [Courses](#courses)
8. [Certifications](#certifications)
9. [Interview Questions](#interview-questions)

## Docker and Container Fundamentals

Goal here is to be very comfortable with how Docker works before going deep into security.

1. Revisit basic Docker concepts:
   1. Images, layers, containers.
   2. Dockerfile instructions (FROM, RUN, COPY, CMD, ENTRYPOINT, EXPOSE, USER, etc.).
   3. Volumes and networking basics.
2. Understand containers vs VMs:
   1. Namespaces and cgroups at high level.
   2. Shared kernel model and what isolation it gives.
3. Practice:
   1. Build simple images from base images (alpine, debian, etc.).
   2. Run containers, inspect them, and play with basic commands.

## Image Build and Supply Chain Security

Here you focus on building **secure images** and understanding supply chain risk.

1. Secure Dockerfile practices:
   1. Use minimal base images.
   2. Avoid unnecessary packages and tools.
   3. Do not run as root – use `USER` properly.
   4. Separate build and runtime stages (multi-stage builds).
   5. Keep secrets out of images.
2. Dependency and base image risk:
   1. Understand how vulnerabilities in base images affect you.
   2. Learn to track and update base images regularly.
3. Basic supply chain concepts:
   1. Image registries and access controls.
   2. Image signing and provenance (high level).
4. Practice:
   1. Take an existing Dockerfile and harden it step by step.
   2. Compare image sizes and contents before vs after.

## Runtime Hardening and Host Security

Even with secure images, runtime and host configuration matter a lot.

1. Container runtime security basics:
   1. Dropping capabilities.
   2. Read-only filesystems where possible.
   3. Limiting resources (CPU/memory) via cgroups.
2. Networking and exposure:
   1. Avoid unnecessary open ports.
   2. Use networks to separate services.
3. Host hardening:
   1. Keep Docker engine and OS patched.
   2. Limit who can run Docker (docker group is effectively root).
   3. Logging and monitoring of Docker daemon and containers.
4. Integration with orchestration:
   1. How these concepts later map into Kubernetes or other orchestrators (see [Kubernetes Security Study Plan](kubernetes-security-study-plan.md)).

## Scanning, Policies and CI/CD Integration

This is where Docker Security meets DevSecOps.

1. Image scanning:
   1. Understand what image scanners usually check (OS packages, app libs).
   2. Severity, fix availability, and risk-based triage.
   3. Where to scan: in CI, in registry, and/or in runtime.
2. Policies and baselines:
   1. Define basic rules (no latest tags, specific allowed registries, minimal base images, no root user by default).
   2. Enforce through CI checks and registry policies.
3. CI/CD integration:
   1. Cross-link with [DevSecOps Study Plan](devsecops-study-plan.md).
   2. Add image build and scan stages into pipelines.
   3. Decide when to block vs warn.

## Books

1. Any good Docker/Container fundamentals book – focus on sections about security and best practices.
2. Books on container security or cloud-native security that include Docker as a base.

## Videos

1. Docker security talks from major conferences (DockerCon, KubeCon, OWASP).
2. Short tutorials on writing secure Dockerfiles and hardening images.
3. Videos on container runtime hardening and host security.

## Courses

1. Docker/Container security courses that cover image hardening and runtime security.
2. DevSecOps courses that include container image scanning and CI/CD integration.

## Certifications

1. Container or cloud-native security certifications where Docker is a key part of the curriculum.
2. General cloud security certifications (AWS/Azure/GCP) if you deploy Docker workloads to cloud.

## Interview Questions

You can reuse some questions from Application Security and DevSecOps, but focus on containers:

1. How would you harden a Dockerfile for a typical web application?
2. What are common security risks in container images and how do you detect them?
3. How would you integrate image scanning into a CI/CD pipeline?
4. What are the implications of giving developers access to the `docker` group on a host?

