# Kubernetes Security Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for the job roles which require good knowledge of Kubernetes and container orchestration security.
Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

Just to make sure that everyone understands what you need to learn to be good at Kubernetes Security.
Kubernetes Security builds on Docker/container security and cloud security. You need to understand how Kubernetes works, how workloads are deployed and exposed, and what controls exist at cluster, namespace, and workload levels.

It is more towards:
- securing clusters and control plane access,
- defining secure defaults for workloads (namespaces, RBAC, network policies),
- integrating Kubernetes security checks into DevSecOps pipelines,
- and working with platform/SRE teams to keep clusters hardened.

Usually it will take you 6-10 weeks to be comfortable with Kubernetes Security fundamentals, assuming you already know basic Docker and some Kubernetes usage.

## In short

1. Kubernetes Security is not just enabling a few network policies.
2. Think more of multi-layer defense: cluster, namespace, workload, network, and supply chain.
3. You should be comfortable with basic Kubernetes concepts (pods, deployments, services, ingress, configmaps, secrets).
4. You should understand how containers and images are built and scanned (see [Docker Security Study Plan](docker-security-study-plan.md)).
5. You should know how Kubernetes fits into DevSecOps and cloud-native security.

## ToC

1. [Kubernetes Fundamentals for Security](#kubernetes-fundamentals-for-security) - 1-2 weeks
2. [Cluster and Control Plane Security](#cluster-and-control-plane-security) - 1-2 weeks
3. [Workload and Identity Security](#workload-and-identity-security) - 2-3 weeks
4. [Network, Policies and Multi-tenancy](#network-policies-and-multi-tenancy) - 1-2 weeks
5. [Supply Chain and Runtime Security](#supply-chain-and-runtime-security) - 1-2 weeks
6. [Benchmarks and Kubernetes Versions](#benchmarks-and-kubernetes-versions)
7. [Books](#books)
8. [Videos](#videos)
9. [Courses](#courses)
10. [Certifications](#certifications)
11. [Interview Questions](#interview-questions)

## Kubernetes Fundamentals for Security
**Duration: 1-2 weeks**

Before securing it, you must understand how it works. Goal here is to be very comfortable with how Kubernetes works, specifically from a security point of view.

### Week 1-2: Core Concepts and Cluster Setup
1. **Architecture:** Control Plane (API Server, etcd, Scheduler, Controller Manager) vs Worker Nodes (Kubelet, Kube-proxy, Container Runtime).
2. **Objects:** Pods, Deployments, ReplicaSets, Services, Ingress, ConfigMaps, Secrets, Namespaces.
3. **Networking:** CNI basics, Pod-to-Pod communication, Service discovery.
4. Understand basic deployment flows:
   1. How manifests define workloads (YAML).
   2. How services expose pods.
   3. How ingress or load balancers expose services externally.
5. Map where **security decisions** are made:
   1. Who can talk to the API server (authentication and RBAC).
   2. Which nodes run which workloads.
   3. How traffic flows inside and outside the cluster.
6. **Practice:** Set up a cluster using `kind` or `minikube` and deploy a simple app.

## Cluster and Control Plane Security
**Duration: 1-2 weeks**

Securing the infrastructure itself.

### Week 3-4: Hardening the Cluster
1. **CIS Benchmarks:** Understand and apply the CIS Kubernetes Benchmark (see [Benchmarks and Kubernetes Versions](#benchmarks-and-kubernetes-versions) below for the current version), and run it with [kube-bench](https://github.com/aquasecurity/kube-bench).
2. **API Server Security:**
   - Disable anonymous access.
   - Enable audit logging.
   - Restrict access to etcd.
3. **RBAC (Role-Based Access Control):**
   - Roles vs ClusterRoles.
   - Bindings.
   - Principle of Least Privilege.
4. **Node Security:**
   - OS hardening.
   - Kubelet security configuration.

## Workload and Identity Security
**Duration: 2-3 weeks**

Securing what runs *inside* the cluster.

### Week 5-6: Securing Pods & Deployments
1. **Pod Security Standards (PSS):** Privileged, Baseline, Restricted profiles, and how Pod Security Admission enforces them per namespace.
2. **Workload identity:** ServiceAccounts and projected/bound ServiceAccount tokens, and how they map to cloud IAM on managed clusters (EKS Pod Identity or IRSA, GKE Workload Identity Federation, AKS Workload Identity). Never mount long-lived cloud credentials into a pod.
3. **Security Context:**
   - `runAsUser`, `runAsGroup`.
   - `readOnlyRootFilesystem`.
   - `allowPrivilegeEscalation: false`.
4. **Secrets Management:**
   - Kubernetes Secrets (encryption at rest).
   - External Secret Stores (Vault, AWS Secrets Manager).

## Network, Policies and Multi-tenancy
**Duration: 1-2 weeks**

Kubernetes networking is a big part of securing workloads.

1. Basic network model:
   1. Pod-to-pod and pod-to-service communication.
   2. Ingress controllers and load balancers.
2. Network Policies:
   1. Deny-by-default vs allow-by-default.
   2. Writing simple network policies to restrict traffic (ingress and egress).
   3. Note that plain `NetworkPolicy` is L3/L4 only - for L7 rules, identity-based policy or FQDN egress rules you need a CNI that extends it (Cilium, Calico).
3. Multi-tenancy considerations:
   1. Combining namespaces, network policies, and RBAC for isolation.
   2. Basic ideas of multi-tenant cluster vs dedicated clusters.
   3. Resource quotas and limit ranges as a denial-of-service control.

## Supply Chain and Runtime Security
**Duration: 1-2 weeks**

Ensuring integrity and monitoring behavior. Here you connect Kubernetes Security with Docker Security and DevSecOps.

### Week 7-8: Advanced Topics
1. **Admission control - this is where policy is actually enforced:**
   - Validating and Mutating admission webhooks (the classic approach).
   - Policy engines: [OPA Gatekeeper](https://open-policy-agent.github.io/gatekeeper/website/docs/) or [Kyverno](https://kyverno.io/docs/).
   - **[ValidatingAdmissionPolicy](https://kubernetes.io/docs/reference/access-authn-authz/validating-admission-policy/)** - Kubernetes' *native*, CEL-based admission policy, [stable/GA since Kubernetes 1.30](https://kubernetes.io/blog/2024/04/24/validating-admission-policy-ga/). Rules are evaluated in-process by the API server, so there is no webhook pod to run, no TLS certs to rotate and no fail-open/fail-closed webhook outage risk. A policy has two objects: the `ValidatingAdmissionPolicy` and a `ValidatingAdmissionPolicyBinding`, with `validationActions` of `Deny`, `Warn` or `Audit` (`Audit`/`Warn` is a great way to dry-run a policy before enforcing).
   - Know the trade-off, because this is a common interview question: use ValidatingAdmissionPolicy for simple, self-contained field checks with no external lookups; keep Gatekeeper/Kyverno for cross-object logic, mutation, image verification, policy reporting and generating resources. Gatekeeper can even [export its constraints to ValidatingAdmissionPolicy](https://open-policy-agent.github.io/gatekeeper/website/docs/validating-admission-policy/), so they are complementary rather than exclusive.
   - `MutatingAdmissionPolicy` is the CEL-based mutation counterpart and reached beta in Kubernetes 1.34 - worth knowing, but do not assume it in production yet.
2. **Supply Chain:**
   - Image registries and allowed/trusted registries.
   - Image scanning in CI/CD *and* before deployment (admission-time verification).
   - Image signing and verification (Cosign / Sigstore), SBOM generation, and provenance/attestations (SLSA).
   - Enforcing all of the above with an admission policy so an unsigned or unscanned image simply cannot be admitted.
3. **Runtime Security - eBPF is now the mainstream approach:**
   - Detecting anomalies with [Falco](https://falco.org/docs/). Learn its **eBPF evolution**: the legacy kernel module needed compiling per kernel version and would not load under Secure Boot, whereas the modern eBPF probe runs verified in a kernel sandbox and works on hardened/immutable OS images. Modern eBPF (`driver.kind=modern_ebpf`, kernel 5.8+) became Falco's default driver from the 0.40 release, so treat eBPF as the default and the kernel module as legacy.
   - [Cilium Tetragon](https://tetragon.io/) - eBPF security observability *and in-kernel runtime enforcement* via LSM hooks. The key distinction to be able to explain: Falco detects and alerts, Tetragon can synchronously block (kill a process, deny a syscall) in-kernel without a user-space round trip. Also look at [Tracee](https://github.com/aquasecurity/tracee) as a third option.
   - Sandboxed containers (gVisor, Kata Containers), if needed for hostile or multi-tenant workloads.
4. **AI and agentic workloads in the cluster** (increasingly asked about, treat as bonus):
   - LLM inference workloads: GPU node pools, model artifacts pulled at runtime from external registries (an unsigned-artifact supply-chain path that image signing does not cover), and why inference pods usually want their own node pool, namespace and egress policy.
   - **MCP servers running as pods:** they are network-reachable tool endpoints, often with credentials to internal systems. Apply the same rules as any other exposed service - least-privilege ServiceAccount, no cluster-admin, deny-by-default egress, authenticated ingress - and remember that a prompt-injected agent calling an over-privileged MCP pod is a lateral-movement path, not just an AI problem.
   - Do not let "it's an AI workload" bypass PSS, network policy or admission control.
5. Cross-link to other plans:
   1. [Docker Security Study Plan](docker-security-study-plan.md).
   2. [DevSecOps Study Plan](devsecops-study-plan.md).
   3. Relevant cloud security study plans if running managed Kubernetes.

## Benchmarks and Kubernetes Versions

Kubernetes moves fast and benchmarks trail it, so always check which Kubernetes version your hardening guide was written against.

1. **CIS Kubernetes Benchmark:** current version is **v2.0.1** (released June 2026), which targets clusters built on **Kubernetes v1.34 and v1.35**. Download it from [CIS](https://www.cisecurity.org/benchmark/kubernetes).
2. **The benchmark tracks specific Kubernetes version ranges.** As of August 2026 the latest stable Kubernetes is **v1.36** (released 22 April 2026), which is *newer* than what CIS v2.0.1 covers - so expect some checks to be stale or to not map cleanly on a 1.36 cluster. Kubernetes supports only the three most recent minor releases (currently 1.36, 1.35, 1.34), each with about a year of patch support, so "run a supported version" is itself a control.
3. **Use the right benchmark for your platform.** Managed control planes are not covered by the generic Kubernetes benchmark - CIS publishes separate benchmarks (all on the [same CIS Kubernetes page](https://www.cisecurity.org/benchmark/kubernetes)) for EKS v2.0.0 and EKS Auto Mode v1.0.0, GKE and GKE Autopilot v2.0.0, AKS v2.0.0, OKE v2.0.0, and OpenShift v2.0.0.
4. **Automate it:** run [kube-bench](https://github.com/aquasecurity/kube-bench) for CIS checks and [kubescape](https://github.com/kubescape/kubescape) or [Trivy](https://github.com/aquasecurity/trivy) for broader misconfiguration and vulnerability scanning.
5. Also read the [NSA/CISA Kubernetes Hardening Guide](https://www.cisa.gov/news-events/alerts/2022/03/15/updated-kubernetes-hardening-guide) (the PDF is linked from that CISA alert; latest is v1.2, August 2022 - dated in places, but still the best single hardening narrative) and the [OWASP Kubernetes Top Ten](https://owasp.org/www-project-kubernetes-top-ten/) alongside the CIS benchmark - they are risk-oriented rather than config-checklist-oriented.

## Books

1. Kubernetes fundamentals books – focus on the chapters about security.
2. Dedicated Kubernetes security or cloud-native security books that cover RBAC, network policies, and admission control.

## Videos

1. Kubernetes security talks from KubeCon, CNCF events, and OWASP.
2. Tutorials on securing RBAC, network policies, and pod security.
3. Videos on managed Kubernetes security (EKS, AKS, GKE) from cloud providers.

## Courses

1. Kubernetes security-focused courses (often part of cloud-native security tracks).
2. Hands-on labs for Kubernetes RBAC, network policies, and workload hardening.
3. DevSecOps courses which include Kubernetes integration.

## Certifications

1. Kubernetes-related certifications that cover security (CKA/CKS and similar) if they align with your goals.
2. Cloud security or cloud-native certifications where Kubernetes is a major component.

## Interview Questions

You can reuse questions from Docker Security, DevSecOps, and cloud security but focus on Kubernetes specifics:

1. How would you secure access to a Kubernetes cluster for multiple teams?
2. How would you restrict which services/pods can talk to each other?
3. What are the risks of running privileged containers and how do you prevent it?
4. How would you ensure only trusted images are deployed in a cluster?

