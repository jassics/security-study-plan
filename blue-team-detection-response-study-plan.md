# Blue Team, Detection & Response Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for job roles focused on Blue Team, SOC, Detection Engineering, and Incident Response.

Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

It will cover what you need to learn to **monitor, detect, and respond** to attacks across endpoints, networks, applications, and cloud.

**How this connects:** Start with [Common Skills](common-skills-study-plan.md) and [Network Security](network-security-study-plan.md), then pair this plan with the cloud study plans ([AWS](aws-security-study-plan.md), [Azure](azure-security-study-plan.md), [GCP](gcp-security-study-plan.md)) and [Web Pentest](web-pentest-study-plan.md) / [Application Security](application-security-study-plan.md) so you can detect attacks you or others already know how to perform. Combine it with [Threat Modeling](threat-modeling-study-plan.md) to turn identified threats into concrete detections and playbooks.

---

## In short

1. Blue Team is not just “watching a SIEM” – it’s about **detecting and responding to real attacks**.  
2. You must understand how logs, telemetry, and alerts are generated and correlated.  
3. You should know the incident response lifecycle and how to build playbooks.  
4. You should be comfortable mapping activity to frameworks like MITRE ATT&CK.  
5. You should understand basics of cloud, endpoint, and network telemetry.

---

## ToC

1. [Blue Team & SOC Fundamentals](#blue-team--soc-fundamentals) - 2 weeks  
2. [Logging, Telemetry & SIEM](#logging-telemetry--siem) - 2-3 weeks  
3. [Detection Engineering & Threat Hunting](#detection-engineering--threat-hunting) - 3-4 weeks  
4. [Incident Response (IR) Fundamentals](#incident-response-ir-fundamentals) - 3-4 weeks  
5. [Digital Forensics Basics](#digital-forensics-basics) - 2-3 weeks  
6. [Cloud & Modern Environments](#cloud--modern-environments) - 2-3 weeks  
7. [Books](#books)  
8. [Videos](#videos)  
9. [Courses](#courses)  
10. [Certifications](#certifications)  
11. [Interview Questions](#interview-questions)

---

## Blue Team & SOC Fundamentals

**Duration: 2 weeks**

Goal: understand what the Blue Team does and how SOCs operate.

### Week 1-2: Core Concepts

1. **Roles & Functions:** Tier 1–3 analysts, incident handlers, detection engineers, IR lead.  
2. **SOC Operating Models:** in-house, MSSP, hybrid.  
3. **Core Activities:** triage, investigation, containment, eradication, recovery, reporting.  
4. **Frameworks:** NIST CSF (Identify–Protect–Detect–Respond–Recover), basic exposure to MITRE ATT&CK.

---

## Logging, Telemetry & SIEM

**Duration: 2-3 weeks**

Goal: understand what to log, how, and where it lands.

### Week 3-5: Data & Platforms

1. **Log Types:**  
   - OS logs (Windows Event Logs, Linux syslog).  
   - Network logs (firewall, proxies, IDS/IPS).  
   - Application & API logs.  
   - Cloud logs (CloudTrail, Azure Activity, GCP Audit, etc.).  
2. **Log Quality:** timestamps, normalization, context, correlation IDs.  
3. **SIEM Concepts:** ingestion, parsing, normalization, correlation, dashboards, alerts.  
4. **Hands-on (if possible):**  
   - Use a lab with an ELK stack, Splunk, or any SIEM-like tool to ingest and search logs.

---

## Detection Engineering & Threat Hunting

**Duration: 3-4 weeks**

Goal: learn how to create high-quality detections and proactively hunt.

### Week 6-9: Detections & Hunts

1. **Detection Engineering Basics:**  
   - Use cases, hypotheses, and detection rules.  
   - Balancing false positives and false negatives.  
2. **MITRE ATT&CK Mapping:**  
   - Tactics vs techniques.  
   - Mapping detections to techniques.  
3. **Query Languages:**  
   - SIEM query basics (KQL-like or SPL-like language if available).  
4. **Threat Hunting:**  
   - Hypothesis-driven hunts.  
   - Baselines and anomaly detection at a high level.  
   - Collect and document hunting notebooks.

---

## Incident Response (IR) Fundamentals

**Duration: 3-4 weeks**

Goal: understand how to handle incidents end-to-end.

### Week 10-13: IR Lifecycle

1. **IR Phases:** Preparation, Detection & Analysis, Containment, Eradication, Recovery, Lessons Learned.  
2. **Playbooks & Runbooks:**  
   - Phishing incident playbook.  
   - Ransomware or malware outbreak playbook.  
   - Cloud credential compromise playbook.  
3. **Communication:**  
   - Internal stakeholders, leadership, legal, PR.  
   - When to involve external parties (regulators, law enforcement).  
4. **Tabletop Exercises:** running simulated incidents to test readiness.

---

## Digital Forensics Basics

**Duration: 2-3 weeks**

Goal: learn fundamentals of collecting and analyzing evidence safely.

### Week 14-16: Forensics Overview

1. **Evidence Handling:** chain of custody, integrity, imaging vs live response.  
2. **Endpoint Forensics Basics:**  
   - Windows (registry artifacts, event logs).  
   - Linux (logs, processes, file timelines).  
3. **Memory & Disk Analysis (high level):** what’s possible and when it’s needed.  
4. **Cloud Forensics Basics:** using cloud logs and snapshots to reconstruct events.

---

## Cloud & Modern Environments

**Duration: 2-3 weeks**

Goal: understand detection & response in cloud, SaaS, and modern stacks.

### Week 17-19: Modern Blue Teaming

1. **Cloud Telemetry:** AWS, Azure, GCP basic security logs and where they are configured.  
2. **Containers & Kubernetes:** high-level understanding of pod/node logs and common attack traces.  
3. **SaaS & IdP Logs:** identity provider logs (SSO, MFA), email security logs, EDR logs.  
4. **Integration:** sending these logs into SIEM / XDR and writing detections around them.

---

## Books

1. Any strong Blue Team / SOC operations book.  
2. Books on incident response and digital forensics.  
3. Books that walk through case studies of real intrusions.

---

## Videos

1. Conference talks on detection engineering, Blue Teaming, and SOC operations.  
2. IR and DFIR case study talks (how real incidents were handled).  
3. Vendor-agnostic content on SIEM best practices and ATT&CK-based detections.

---

## Courses

1. Blue Team / SOC analyst fundamentals courses.  
2. IR/DFIR-focused training with hands-on labs.  
3. Threat hunting and detection engineering courses using common SIEM/XDR tools.

---

## Certifications

1. Entry-level SOC / Blue Team certs if available from reputable providers.  
2. IR/DFIR-oriented certifications if you want to specialize.  
3. General security certs (like Security+) to support foundational knowledge.

---

## Interview Questions

You can reuse questions from Network Security, Cloud Security, and GRC but focus on detection & response:

1. How would you design logging for a new web application or API?  
2. How do you triage an alert that might be a false positive?  
3. How would you investigate a suspected account compromise in a cloud environment?  
4. How do you measure the effectiveness of your detections and IR process?
