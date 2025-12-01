# AWS Security Study Plan

I am making the study plan irrespective of job role under AWS Security category. It can be AWS Security Analyst, AWS Security Researcher or AWS Security Engineer or Cloud Security Operations Expert or Cloud Security Manager.

So, check how much you can cover and close the checkbox. The more you close, the better candidate you are for the job role.
Also, I assume you have already checked and comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

## ToC
1. [AWS Fundamentals](#aws-fundamentals) - 2-3 weeks
2. [AWS Native Security core skills](#aws-native-security-core-skills) - 4-6 weeks
3. [AWS Security Whitepapers](#aws-security-whitepapers) - 2 weeks
4. [Check your AWS Pentesting Skills](#check-your-aws-pentesting-skills) - 2-3 weeks
5. [Check your Knowledge against common security benchmark and frameworks](#check-your-knowledge-against-common-security-benchmark-and-frameworks)
6. [AWS Security Videos and Courses](#aws-security-videos-and-courses)
7. [AWS Security Interview Questions](#aws-security-interview-questions)
8. [People to follow on twitter](#people-to-follow-on-twitter)

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
11. [AWS CIS Foundation benchmark](https://d1.awsstatic.com/whitepapers/compliance/AWS_CIS_Foundations_Benchmark.pdf)
12. [AWS Security Incident Response](https://d1.awsstatic.com/whitepapers/aws_security_incident_response.pdf)
13. [Overview of AWS Lambda Security](https://d1.awsstatic.com/whitepapers/Overview-AWS-Lambda-Security.pdf)
14. [AWS KMS Best Practices](https://d1.awsstatic.com/whitepapers/aws-kms-best-practices.pdf)
15. [Encrypting File Data with Amazon Elastic File System](https://d1.awsstatic.com/whitepapers/Security/amazon-efs-encrypted-filesystems.pdf)
16. [Security of AWS CloudHSM backups](https://d1.awsstatic.com/whitepapers/Security/security-of-aws-cloudhsm-backups.pdf)
17. [Security overview of AWS Lambda](https://aws.amazon.com/lambda/security-overview-of-aws-lambda/)
18. [NIST Cybersecurity Framework in the AWS cloud](https://d0.awsstatic.com/whitepapers/compliance/NIST_Cybersecurity_Framework_CSF.pdf)
19. [NIST 800-144 Security and Privacy in Public Cloud Computing](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-144.pdf)
20. [Security at the Edge: Core Principles](https://d1.awsstatic.com/whitepapers/Security/security-at-the-edge.pdf)
21. [AWS KMS Best Practices](https://d0.awsstatic.com/whitepapers/aws-kms-best-practices.pdf)
22. [Security Overview of AWS Fargate](https://d1.awsstatic.com/whitepapers/AWS_Fargate_Security_Overview_Whitepaper.pdf)

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
1. AWS CIS Benchmark
2. CSA Cloud Matrix and STAR Framework
3. [NIST CSF for AWS](https://d1.awsstatic.com/whitepapers/compliance/NIST_Cybersecurity_Framework_CSF.pdf)
4. ISO 27017

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
