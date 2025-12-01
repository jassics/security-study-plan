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
6. [Books](#books)
7. [Videos](#videos)
8. [Courses](#courses)
9. [Certifications](#certifications)
10. [Interview Questions](#interview-questions)

## Kubernetes Fundamentals for Security

Goal here is to be very comfortable with how Kubernetes works, specifically from a security point of view.

1. Revisit basic Kubernetes concepts:
   1. Cluster components (api-server, controller-manager, scheduler, etcd, kubelet).
   2. Pods, deployments, replica sets.
   3. Services, ingress, configmaps, secrets.
2. Understand basic deployment flows:
   1. How manifests define workloads (YAML).
   2. How services expose pods.
   3. How ingress or load balancers expose services externally.
3. Map where **security decisions** are made:
   1. Who can talk to the API server (authentication and RBAC).
   2. Which nodes run which workloads.
   3. How traffic flows inside and outside the cluster.

## Kubernetes Fundamentals and Cluster Setup
**Duration: 1-2 weeks**

Before securing it, you must understand how it works.

### Week 1-2: Core Concepts
1. **Architecture:** Control Plane (API Server, etcd, Scheduler, Controller Manager) vs Worker Nodes (Kubelet, Kube-proxy, Container Runtime).
2. **Objects:** Pods, Deployments, Services, ConfigMaps, Secrets, Namespaces.
3. **Networking:** CNI basics, Pod-to-Pod communication, Service discovery.
4. **Practice:** Set up a cluster using `kind` or `minikube` and deploy a simple app.

## Cluster Hardening
**Duration: 1-2 weeks**

Securing the infrastructure itself.

### Week 3-4: Hardening the Cluster
1. **CIS Benchmarks:** Understand and apply CIS Kubernetes Benchmark.
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

## Workload Security
**Duration: 1-2 weeks**

Securing what runs *inside* the cluster.

### Week 5-6: Securing Pods & Deployments
1. **Pod Security Standards (PSS):** Privileged, Baseline, Restricted profiles.
2. **Security Context:**
   - `runAsUser`, `runAsGroup`.
   - `readOnlyRootFilesystem`.
   - `allowPrivilegeEscalation: false`.
3. **Network Policies:**
   - Default deny all.
   - Allow specific traffic (ingress/egress).
4. **Secrets Management:**
   - Kubernetes Secrets (encryption at rest).
   - External Secret Stores (Vault, AWS Secrets Manager).

## Supply Chain and Runtime Security
**Duration: 1-2 weeks**

Ensuring integrity and monitoring behavior.

### Week 7-8: Advanced Topics
1. **Admission Controllers:**
   - Validating and Mutating webhooks.
   - Policy engines: OPA Gatekeeper or Kyverno.
2. **Supply Chain:**
   - Image signing (Cosign).
   - Image scanning in CI/CD.
3. **Runtime Security:**
   - Detecting anomalies (Falco).
   - Sandboxed containers (gVisor, Kata Containers). if needed.

## Network, Policies and Multi-tenancy

Kubernetes networking is a big part of securing workloads.

1. Basic network model:
   1. Pod-to-pod and pod-to-service communication.
   2. Ingress controllers and load balancers.
2. Network Policies:
   1. Deny-by-default vs allow-by-default.
   2. Writing simple network policies to restrict traffic.
3. Multi-tenancy considerations:
   1. Combining namespaces, network policies, and RBAC for isolation.
   2. Basic ideas of multi-tenant cluster vs dedicated clusters.

## Supply Chain and Runtime Security

Here you connect Kubernetes Security with Docker Security and DevSecOps.

1. Supply chain:
   1. Image registries and allowed registries.
   2. Image scanning before deployment.
   3. Admission controllers or policy engines (at a high level) to enforce constraints.
2. Runtime security:
   1. Monitoring workloads for suspicious behavior.
   2. Basic idea of using runtime security tools to detect attacks.
3. Cross-link to other plans:
   1. [Docker Security Study Plan](docker-security-study-plan.md).
   2. [DevSecOps Study Plan](devsecops-study-plan.md).
   3. Relevant cloud security study plans if running managed Kubernetes.

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

