# GCP Security Study Plan
I am making the study plan irrespective of job role under GCP Security category. It can be Cloud Security Analyst, Cloud Security Researcher or Cloud Security Engineer or Cloud Security Operations Expert or Cloud Security Manager or Cloud Governance.

So, check how much you can cover and learn practically. The more you are good at these concepts, the better candidate you are for the job role.
Also, I assume you have already checked and comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

## GCP Security Skills Learning and Checklist
My only suggestion here is ask below 4 questions while learning each topic/concepts etc.
1. What is this? (For example: What is instance group, where it is used and why?)
2. Why am I learning this specific service or concept now? Will it help me for my job role and in future?
3. How can I implement this? (Practical aspects, hands-on knowledge always have an extra edge)
4. How it will make secure or how to make it secure depending upon the topic or concept?

### GCP Fundamentals (2-3 weeks)
I am listing only the topic name with few lines and possibly some examples. How much you learn and comfortable with the concept or topic is upon you. 
And I will share the minimal link to make you up to the mark and you are free to learn anything more than this for better candidacy and experience.

#### For any GCP Service(s), please follow this strategy:
1. What does this service do?
2. What problem it would solve for the business?
3. Security Best Practices guide for GCP services. Ex: GCS security best practices, VPC security best practices.
4. What permissions you should provide for each role or principal or service account to maintain the least privilege principle.
5. How it is being used, can there be some security misconfiguration if not configured properly. If so, what are the security guideline to configure it.
6. Is multi-tier, multi region required for this service?
7. How data at rest and data in transit can be achieved?
8. Is logging required? If so, how are you going to log and what data and till what period
9. Are we monitoring it? what's the reason for Yes or No?
10. Any specific security settings for that service like Bucket Permissions for specific GCS bucket

To understand and use GCP resources effectively from security standpoint, you must understand common resources which an organization would use. Below are some important resources which you need to understand as you are either the cloud solution engineer or cloud architect.

#### IAM (1 week): 
It's very important topic for any cloud role. Try to understand it practically as much as your job demands.
1. [Start with GCP IAM official doc](https://cloud.google.com/iam/docs/overview)
2. [Understand IAM roles and permissions is 2nd important thing to excel in IAM concepts](https://cloud.google.com/iam/docs/roles-overview)
3. User, Group, Roles and when to use when and don't forget to ask why this, why not that
4. Custom role vs Google Managed role
5. Cross-Account IAM policy to different roles, services, account
6. Understand the IAM policy from security mindset. Why this, why not this?
8. [Using IAM Securely](https://cloud.google.com/iam/docs/using-iam-securely)

#### GCS (Google Cloud Storage)
#### GKE
#### VPC (Virtual Private Cloud)
#### Firewall Rules and policies
#### Load Balancer
#### Cloud DNS
#### Cloud CDN
#### Google Cloud Armor
#### Google Cloud Logging
#### BigQuery
#### API Gateway
#### Certificate Manager
#### Secrets Manager
#### Cloud Run
#### Cloud Function

### GCP Native Security skills
What I mean to say here is:
1. GCP core services related to security
2. GCP Security services hands-on knowledge

**What are these?**

These are the core services:
1. IAM, super important
2. Compute Instances
3. GCS
4. VPC, I feel it as the toughest one so far apart from GKE
5. RDS
6. API Gateway
7. GKE
8. Cloud Run
9. Cloud Function
10. Cloud Composer
11. BigQuery
12. DataStore

Below are GCP Core Security services that you should know and try hands-on as much as possible

1. IAM Policy Analyzer
2. IAM Organization Policies

### GCP Security Whitepapers
GCP has awesome lists of whitepapers related to GCP Security. We are adding few important one here. You can anytime check more for updated or new security whitepapers [here](https://aws.amazon.com/security/security-learning/?whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc)

And don't forget to **bookmark GCP Security bulletin** for new vulnerabilities' news from [here](https://aws.amazon.com/security/security-bulletins/)

1. [GCP Overview](https://cloud.google.com/docs/overview) - One of the important whitepapers to understand an overview of GCP
2. [Introduction to GCP Security Whitepaper](https://cloud.google.com/static/docs/security/overview/resources/google_security_wp.pdf)
3. [Google Cloud Security Foundation Guide](https://services.google.com/fh/files/misc/google-cloud-security-foundations-guide.pdf)
4. [GCP Well-Architected Security Pillar](https://cloud.google.com/architecture/framework/security)
5. [Risk Governance of Digital Transformation](https://services.google.com/fh/files/misc/risk-governance-of-digital-transformation.pdf)
6. [GCP Security Checklist](https://medium.com/@hassene/google-cloud-platform-security-checklist-5f57fe8eb761)
7. [Google Infrastructure Security Design Overview](https://cloud.google.com/static/docs/security/infrastructure/design/resources/google_infrastructure_whitepaper_fa.pdf)
8. [NIST Cybersecurity Framework in the GCP cloud](https://services.google.com/fh/files/misc/gcp_nist_cybersecurity_framework.pdf)
9. [NIST 800-144 Security and Privacy in Public Cloud Computing](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-144.pdf)

### Check your GCP Pentesting Skills
1. A Damn Vulnerable GCP Infrastructure [GCPGoat](https://github.com/ine-labs/GCPGoat)
2. Try out the scenarios in [Cloud Goat](https://github.com/RhinoSecurityLabs/cloudgoat)
3. [GCP Pentest Labs](https://github.com/lacioffi/GCP-pentest-lab/)
4. [GCP Pentesting](https://cloud.hacktricks.xyz/pentesting-cloud/gcp-security)

### Check your Knowledge against common security benchmark and frameworks.
1. CIS Benchmark for Google Cloud. You can download pdf version from [here](https://www.cisecurity.org/benchmark/google_cloud_computing_platform)
2. [CSA Cloud Matrix and STAR Framework](https://cloudsecurityalliance.org/download/artifacts/cloud-controls-matrix-v4/)
3. [NIST CSF for GCP](https://services.google.com/fh/files/misc/gcp_nist_cybersecurity_framework.pdf)
4. [ISO 27017](https://www.amnafzar.net/files/1/ISO%2027000/ISO%20IEC%2027017-2015.pdf)

## GCP Security Videos and Courses
1. [GCP Cloud Security Features](https://www.youtube.com/watch?v=83IwaIaBRRU)
2. [GCP Full Course from Intellipat](https://www.youtube.com/watch?v=cwpbY4wJMBs)
3. [Google Cloud Security Fundamentals - Level 1](https://www.youtube.com/watch?v=9Bx_cqpJDpI)
4. [Managing Secuirty in Google Cloud](https://www.cloudskillsboost.google/course_templates/21)

## GCP Security Interview Questions
I have a _[separate repo for GCP Security interview questions](https://github.com/jassics/security-interview-questions/blob/main/gcp-security-interview-questions.md)._ I will keep it updated time to time. You can **star** it or **[fork it](https://github.com/jassics/security-interview-questions/fork).** 
