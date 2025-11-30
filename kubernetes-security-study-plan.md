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

## Cluster and Control Plane Security

Here you focus on securing the cluster itself.

1. Access to cluster:
   1. Authentication methods (certs, tokens, OIDC).
   2. RBAC roles and role bindings.
2. API server and etcd security basics:
   1. TLS configuration and encryption at rest.
   2. Securing etcd access (only via API server).
3. Node security:
   1. Hardening nodes (OS patching, limiting access).
   2. kubelet security configuration basics.
4. Managed vs self-managed Kubernetes:
   1. Understand what your cloud provider manages vs what you must secure.

## Workload and Identity Security

Now focus on how workloads are defined and what identities they use.

1. Pod security:
   1. SecurityContext basics (runAsUser, fsGroup, capabilities, readOnlyRootFilesystem).
   2. Avoiding privileged containers.
2. Namespaces and multi-tenancy basics:
   1. Isolating workloads by namespace.
   2. Using namespaces for scoping RBAC and network policies.
3. Service accounts and workload identity:
   1. How pods authenticate to the API server.
   2. Mapping Kubernetes service accounts to cloud IAM roles where applicable.
4. Secrets management:
   1. Basics of Kubernetes Secrets and their limitations.
   2. Using external secret managers if needed.

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

