# AWS Security Study Plan

I am making the study plan irrespective of job role under AWS Security category. It can be AWS Security Analyst, AWS Security Researcher or AWS Security Engineer or Cloud Security Operations Expert or Cloud Security Manager.

So, check how much you can cover and close the checkbox. The more you close, the better candidate you are for the job role.
Also, I assume you have already checked and comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

## ToC
1. [AWS Fundamentals](#aws-fundamentals) - 2-3 weeks
2. [AWS Native Security core skills](#aws-native-security-core-skills) - 4-6 weeks
3. [Current AWS Security Landscape (2025-2026)](#current-aws-security-landscape-2025-2026) - 1 week
4. [AWS Security Whitepapers](#aws-security-whitepapers) - 2 weeks
5. [Check your AWS Pentesting Skills](#check-your-aws-pentesting-skills) - 2-3 weeks
6. [Check your Knowledge against common security benchmark and frameworks](#check-your-knowledge-against-common-security-benchmark-and-frameworks)
7. [AWS Security Videos and Courses](#aws-security-videos-and-courses)
8. [AWS Security Interview Questions](#aws-security-interview-questions)
9. [People to follow on twitter](#people-to-follow-on-twitter)

## AWS Fundamentals
**Duration: 2-3 weeks**

I am listing only the topic name. How much you learn and comfortable with the concept or topic is upon you. 
And I will share the minimal link to make you up to the mark and you are free to learn anything more than this for better candidacy and experience.

### Week 1: IAM Deep Dive
One of the most important and must have skills for you. Try to understand IAM functionalities as much as possible.
1. [Understand IAM policy in 60 minutes: Youtube](https://www.youtube.com/watch?v=YQsK4MtsELU)
2. [Understand IAM permissions](https://aws.amazon.com/iam/features/manage-permissions/)
3. [Business Use Cases for IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UseCases.html)
4. [Security in IAM and STS](https://docs.aws.amazon.com/IAM/latest/UserGuide/security.html)
5. [IAM Access Analyzer](https://aws.amazon.com/iam/features/analyze-access/)
6. User, Group, Roles and when to use when and don't forget to ask why this, why not that
7. Custom policy vs AWS Managed Policy
8. Cross-Account IAM policy to different roles, services, account
9. Understand the IAM policy from security mindset. Why this, why not this? 
10. [Service Control Policy](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
11. [Security Best Practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

### Week 2-3: Core Services
**For any AWS Service(s), please follow this strategy:**
1. What does this service does & what problem it would solve for business
2. Security Best Practices guide for AWS service. Ex: S3 security best practices, VPC security best practices.
3. What permissions you should provide for each role to maintain the least privilege principle.
4. How it is being used, can there be some security misconfiguration if not configured properly.
5. Is multi-tier, multi region required for this service
6. How data at rest and data in transit can be achieved.
7. Is logging required? If so, how are you going to log and what data and till what period
8. Are we monitoring it? what's the reason for Yes or No
9. Any specific security settings for that service like Bucket Policy for S3 bucket

**Key Services to Cover:**
1. Amazon S3
2. KMS
3. VPC
4. Lambda
5. AWS EKS and ECS
6. AMAZON RDS

## AWS Native Security core skills
**Duration: 4-6 weeks**

What I mean to say here is:
1. AWS core services related security skills
2. AWS Security services hands-on knowledge

### Week 4-6: Core Services Security
**These are the core services:**
1. IAM, super important
2. EC2
3. S3
4. VPC, I feel it as the toughest one so far
5. RDS
6. API Gateway
7. Lambda
8. ECS and EKS

### Week 7-9: Security Services Hands-on
**Below are AWS Core Security services that you should know and try hands-on as much as possible:**
1. IAM Access Analyzer
2. S3 Bucket Policy
3. Security Group and NACL
4. CloudTrail
5. Config
6. GuardDuty
7. Inspector
8. Macie
9. Security Hub
10. WAF and Shield (Optional, but if your job needs it; learn it)
11. AWS KMS
12. Secrets Manager
13. Cognito
14. [IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html) (successor to AWS SSO) - workforce identity, permission sets and short-lived credentials instead of long-lived IAM users

## Current AWS Security Landscape (2025-2026)
**Duration: 1 week**

The AWS security service surface changed a lot in 2025. Don't study only the older service list - interviewers increasingly ask about these.

1. **Security Hub as a CNAPP-style layer:** [AWS Security Hub became generally available in December 2025](https://aws.amazon.com/about-aws/whats-new/2025/12/security-hub-near-real-time-risk-analytics/) with near real-time risk analytics. It aggregates and correlates findings from GuardDuty, Inspector, Macie and Security Hub CSPM, and organizes signals by threats, exposures, resources and coverage. Note the naming split: the older posture-management capability is now **Security Hub CSPM** (this is what runs your CIS/AWS FSBP standards), while **Security Hub** is the unified risk/correlation layer on top.
2. **GuardDuty Extended Threat Detection (ETD):** correlates multiple signals over time into a single multi-stage attack sequence finding instead of isolated alerts.
   - [Launched Dec 2024](https://aws.amazon.com/about-aws/whats-new/2024/12/amazon-guardduty-extended-threat-detection/) for IAM and S3.
   - [Amazon EKS support added June 2025](https://aws.amazon.com/about-aws/whats-new/2025/06/amazon-guardduty-threat-detection-eks/).
   - [Amazon EC2 and ECS support added Dec 2025](https://aws.amazon.com/about-aws/whats-new/2025/12/guardduty-extended-threat-detection-ec2-ecs/).
3. **[IAM Access Analyzer](https://aws.amazon.com/iam/access-analyzer/) - go beyond external access findings:**
   - **Custom policy checks** - automated-reasoning checks you can run in CI/CD to fail a build when a policy change is more permissive than the previous version, or when it grants public access. Start with [Introducing IAM Access Analyzer custom policy checks](https://aws.amazon.com/blogs/security/introducing-iam-access-analyzer-custom-policy-checks/).
   - **Internal access findings** - who *inside* your organization can reach an S3, DynamoDB or RDS resource, evaluated across identity policies, resource policies, SCPs and RCPs.
   - **Unused access findings** - unused roles, users, access keys and permissions.
4. **[EKS Pod Identity](https://docs.aws.amazon.com/eks/latest/userguide/pod-identity.html):** the current recommended way to give pods AWS permissions, replacing most IRSA (IAM Roles for Service Accounts) use. Know both, and be able to explain the trade-off: Pod Identity drops the per-cluster OIDC trust-policy sprawl and supports [cross-account access via `targetRoleArn`](https://aws.amazon.com/about-aws/whats-new/2025/06/amazon-eks-pod-identity-cross-account-access) - IRSA is still valid and is not deprecated.
5. **[IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html):** federated workforce access with permission sets across accounts. Practise mapping IdP groups to permission sets, and understand why this beats per-account IAM users with long-lived access keys.

## AWS Security Whitepapers
**Duration: 2 weeks**

AWS has awesome lists of whitepapers related to AWS Security. We are adding few important one here. You can anytime check more for updated or new security whitepapers [here](https://aws.amazon.com/security/security-learning/?whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc)

### Week 10-11: Reading & Analysis
1. [AWS Overview](https://d1.awsstatic.com/whitepapers/aws-overview.pdf) - One of the important whitepaper to understand an overview of AWS
2. [Introduction to AWS Security Whitepaper](https://docs.aws.amazon.com/whitepapers/latest/introduction-aws-security/introduction-aws-security.pdf)
3. [AWS Well-Architected Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/wellarchitected-security-pillar.pdf)
4. [Introduction to Security By Design](https://d1.awsstatic.com/whitepapers/compliance/Intro_to_Security_by_Design.pdf)
5. [AWS Well Architected Framework](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf)
6. [AWS Risk And Compliance Whitepaper](https://d0.awsstatic.com/whitepapers/compliance/AWS_Risk_and_Compliance_Whitepaper.pdf)
7. [AWS Security Checklist](https://d1.awsstatic.com/whitepapers/Security/AWS_Security_Checklist.pdf)
8. [AWS HIPAA Compliance Whitepaper](https://d0.awsstatic.com/whitepapers/compliance/AWS_HIPAA_Compliance_Whitepaper.pdf)
9. [AWS Cloud Adoption Framework](https://d1.awsstatic.com/whitepapers/aws_cloud_adoption_framework.pdf)
10. [AWS Auditing Security Checklist](https://d1.awsstatic.com/whitepapers/compliance/AWS_Auditing_Security_Checklist.pdf)
11. CIS AWS Foundations Benchmark - CIS published **v7.0.0** in April 2026; download it from [CIS](https://www.cisecurity.org/benchmark/amazon_web_services). Separately, know what your tooling can actually automate: [Security Hub CSPM](https://docs.aws.amazon.com/securityhub/latest/userguide/cis-aws-foundations-benchmark.html) supports **v5.0.0** (its newest supported version, [added October 2025](https://aws.amazon.com/about-aws/whats-new/2025/10/aws-security-hub-cspm-cis-foundations-benchmark-v5) with 40 automated controls) plus v3.0.0, v1.4.0 and v1.2.0, and AWS recommends v5.0.0 over the older ones. Also learn which CIS requirements are *manual only* (for example most of the CloudWatch metric-filter/alarm requirements from the older versions).
12. [AWS Security Incident Response](https://d1.awsstatic.com/whitepapers/aws_security_incident_response.pdf)
13. [Overview of AWS Lambda Security](https://d1.awsstatic.com/whitepapers/Overview-AWS-Lambda-Security.pdf)
14. [AWS KMS Best Practices](https://d1.awsstatic.com/whitepapers/aws-kms-best-practices.pdf)
15. [Encrypting File Data with Amazon Elastic File System](https://d1.awsstatic.com/whitepapers/Security/amazon-efs-encrypted-filesystems.pdf)
16. [Security of AWS CloudHSM backups](https://d1.awsstatic.com/whitepapers/Security/security-of-aws-cloudhsm-backups.pdf)
17. [Security overview of AWS Lambda](https://aws.amazon.com/lambda/security-overview-of-aws-lambda/)
18. [NIST Cybersecurity Framework in the AWS cloud](https://d0.awsstatic.com/whitepapers/compliance/NIST_Cybersecurity_Framework_CSF.pdf) - this whitepaper was updated in January 2025 and is aligned to **NIST CSF 2.0** (released February 2024), so it covers all six Core Functions including the new **Govern** function. If you are reading older CSF 1.1 material elsewhere, note that Govern did not exist there.
19. [NIST 800-144 Security and Privacy in Public Cloud Computing](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-144.pdf)
20. [Security at the Edge: Core Principles](https://d1.awsstatic.com/whitepapers/Security/security-at-the-edge.pdf)
21. [AWS KMS Best Practices](https://d0.awsstatic.com/whitepapers/aws-kms-best-practices.pdf)
22. [Security in Amazon ECS (including AWS Fargate)](https://docs.aws.amazon.com/AmazonECS/latest/bestpracticesguide/security.html) - the old *Security Overview of AWS Fargate* whitepaper PDF is no longer served, so use the maintained ECS Best Practices Guide security chapter instead. It covers the Fargate shared-responsibility split, task/container hardening, network security and FIPS-140 for Fargate.

## Check your AWS Pentesting Skills
**Duration: 2-3 weeks**

### Week 12-14: Practical Labs
1. Did you use [pacu](https://github.com/RhinoSecurityLabs/pacu)? if not, start using it
2. Try out the scenarios in [Cloud Goat](https://github.com/RhinoSecurityLabs/cloudgoat)
3. Try AWS CTF from [flaws.cloud](http://flaws.cloud/). Here is [solution on YouTube](https://www.youtube.com/playlist?list=PLRTsCutScZnzo3uV_79Dur73kqskfaTMS) as well
4. Next level is at [flaws2.cloud](http://flaws2.cloud/)
5. Try [Well Architected Framework: Security](https://www.wellarchitectedlabs.com/security/) Labs
6. [AWS Security Workshops](https://awssecworkshops.com/workshops/)
7. Check other good tools like Prowler and ScoutSuite as well.

## Check your Knowledge against common security benchmark and frameworks.
1. [CIS AWS Foundations Benchmark](https://www.cisecurity.org/benchmark/amazon_web_services) - current CIS release is v7.0.0 (April 2026); [Security Hub CSPM automates up to v5.0.0](https://docs.aws.amazon.com/securityhub/latest/userguide/cis-aws-foundations-benchmark.html)
2. CSA Cloud Matrix and STAR Framework
3. [NIST CSF 2.0 for AWS](https://d1.awsstatic.com/whitepapers/compliance/NIST_Cybersecurity_Framework_CSF.pdf) - CSF 2.0 was published February 2024; the AWS alignment whitepaper was refreshed for it in January 2025
4. [ISO/IEC 27017](https://www.iso.org/standard/82878.html) - cloud-specific controls built on ISO/IEC 27002 (the 2015 edition was revised, current edition is ISO/IEC 27017:2026)

## AWS Security Videos and Courses
Check [**Awesome AWS Security**](https://github.com/jassics/awesome-aws-security) repo for more details on book, videos, courses etc.

## AWS Security Interview Questions
I have a [separate repo for skills roadmap and interview questions](https://github.com/jassics/cybersecurity-interview-questions/blob/main/aws-security-interview-questions.md). I will keep it updated time to time. You can star it or [fork it](https://github.com/jassics/cybersecurity-skills-career-roadmap/fork). 

## People to follow on twitter
1. [Abhay Bhargav](https://twitter.com/abhaybhargav)
2. [Scott Piper](https://twitter.com/0xdabbad00)
3. [Anant Srivastava](https://twitter.com/anantshri)
4. [Aakash Mahajan](https://twitter.com/makash)
5. [Sanjeev Jaiswal](https://twitter.com/jassics)
