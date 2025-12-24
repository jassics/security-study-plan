## Threat Modelling
> [!IMPORTANT]
> If you are into Product security or application security or security engineering, you would need this study plan more than any other security professionals. However, it is advised for every security professional to have a fair understanding of Threat Modeling fundamentals.

![Threat Modeling Study Plan](images/Threat-Modeling-Study-Plan.png)
> [!Note]
> It should take 1-2 months for good understanding of Threat Modeling with some hands-on experiences.

### What is Threat Modeling
Threat modelling is a structured approach for analysing the security of an application and enables to identify, quantify, and address the security risks associated with an application.
From details about threats and likely attacks against each application, the organization operates more effectively through better decisions about prioritization of initiatives for security. 
Additionally, decisions for risk acceptance are more informed, therefore better aligned to the business.

> [!TIP]
> You must go through [OWASP Threat Modeling Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html) for basic understanding.

In short,
- **Threat modeling is the process** of identifying, analyzing, and mitigating potential security threats to a system or organization. 
- It involves identifying the assets that need to be protected, analyzing the potential threats to those assets, and developing strategies to mitigate or eliminate those threats.
- The early you perform Threat Modeling the better result you would get.

### The objective to conduct threat modelling is to investigate following:
1. The trust boundaries to and within the application
2. The actors that interact within and outside of the trust boundaries
3. Information flows within and to and from the trust boundaries
4. Information persistence within and out of trust boundaries
5. Threats to transgression of trust boundaries by actors and for information flow and persistence
6. Vulnerabilities at trust boundaries as accessed by actors and for information flow and persistence
7. Threat agents that can exploit the vulnerabilities
8. Impact of exploitation of vulnerability by a threat agent
9. Decision tree to treat the risk

## ToC
1. [Threat Modeling Fundamentals](#threat-modeling-fundamentals) - 2 weeks
2. [Methodologies](#methodologies) - 2 weeks
3. [Process and Tools](#process-and-tools) - 2 weeks
4. [Advanced Topics and Practice](#advanced-topics-and-practice) - 2 weeks
5. [Resources](#resources)

## Threat Modeling Fundamentals
**Duration: 2 weeks**

Understand the "Why" and "What" of Threat Modeling.

### Week 1-2: Core Concepts
- **Definition:** Identifying, analyzing, and mitigating potential security threats.
- **Why it matters:** Proactive identification, cost efficiency, prioritization.
- **Key Elements:**
    - **Assets:** What are we protecting?
    - **Threats:** What can go wrong?
    - **Vulnerabilities:** Where are we weak?
    - **Mitigations:** What are we going to do about it?
- **The 4 Questions:**
    1. What are we building?
    2. What can go wrong?
    3. What are we going to do about it?
    4. Did we do a good job?

## Methodologies
**Duration: 2 weeks**

Learn the structured approaches to finding threats.

### Week 3-4: Frameworks
1. **STRIDE:** Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege. (Focus heavily on this).
2. **PASTA:** Process for Attack Simulation and Threat Analysis (Risk-centric).
3. **Attack Trees:** Visualizing attack paths.
4. **Other models:** CVSS (scoring), DREAD (scoring), LINDUNN (privacy).

## Process and Tools
**Duration: 2 weeks**

How to actually *do* it in a real project.

### Week 5-6: Execution
1. **Data Flow Diagrams (DFDs):**
    - Trust boundaries.
    - Processes, Data Stores, Data Flows, External Entities.
2. **The Process:**
    - Define Scope -> Decompose Application -> Identify Threats -> Mitigate -> Validate.
3. **Tools:**
    - **OWASP Threat Dragon:** Open source, web/desktop based.
    - **Microsoft Threat Modeling Tool:** The classic standard.
    - **Threagile:** Agile, code-driven threat modeling.

## Advanced Topics and Practice
**Duration: 2 weeks**

Scaling and integrating into SDLC.

### Week 7-8: Scaling & Integration
1. **Integration:** How to fit TM into Agile/DevOps (Rapid Threat Modeling).
2. **Validation:** Verifying mitigations through testing (pentesting, unit tests).
3. **Practice:**
    - Model a simple web app.
    - Model a cloud infrastructure (e.g., S3 bucket setup).
    - Model a CI/CD pipeline.

### Threat Modeling tools to explore
1. [OWASP Threat Dragon](https://www.threatdragon.com/#/)
2. [Microsoft Threat Modeling Tool](https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool)
3. [STRIDE GPT](https://stridegpt.streamlit.app/)
4. [Threagile - run agile threat modeling](https://run.threagile.io/)
5. [PyTM - a Pythonic Framework for Threat Modeling](https://github.com/izar/pytm)
6. [draw.io is also a good tool to draw threat model diagram](https://www.drawio.com/)

### Resources to learn and practice
1. https://owasp.org/www-project-threat-dragon/
2. https://owasp.org/www-community/Threat_Modeling
3. https://www.simplilearn.com/what-is-threat-modeling-article
4. https://www.synopsys.com/glossary/what-is-threat-modeling.html
5. https://www.eccouncil.org/threat-modeling/
6. https://komsr3ll.medium.com/threat-modelling-attack-vectors-4f4989336588
7. [Mindmap of a threat model used by Red Team](https://www.oreilly.com/library/view/hands-on-red-team/9781788995238/55d89c3e-e3f2-414a-872f-37620e9ab43f.xhtml)
8. [Cyber Threat Modeling by MITRE](https://www.mitre.org/sites/default/files/2021-11/prs-18-1174-ngci-cyber-threat-modeling.pdf)
9. https://redcanary.com/blog/threat-modeling/
10. https://www.jemurai.com/2020/11/10/risk-and-threat-modeling-with-mind-maps/
11. https://shellsharks.com/threat-modeling
12. [Clone this repo for more resources: Awesome Threat Modeling](https://github.com/hysnsec/awesome-threat-modelling) by [@secfigo](https://github.com/secfigo)
13. [Threat Modeling Podcast by Chris Romeo](https://open.spotify.com/show/4q9BxNrRb0NWnLBpSmNqoP)
14. [Threat Modeling learning resources: Linkedin Post](https://www.linkedin.com/feed/update/urn:li:activity:7209798162687873026/)
15. [Certified Threat Modeling Professional by Practical DevSecOps](https://www.practical-devsecops.com/certified-threat-modeling-professional/)
16. [Kubernetes Threat Modeling](https://www.trendmicro.com/vinfo/in/security/news/security-technology/a-deep-dive-into-kubernetes-threat-modeling)
17. [AWS S3 Threat Modeling - One you think you are ready for real time projects](https://controlcatalog.trustoncloud.com/dashboard/aws/s3)

### Video Resources :bulb:
1. https://youtu.be/h_BC6QMWDbA
2. https://youtu.be/GqmQg-cszw4
3. https://youtu.be/fggB70PxhmA
4. https://youtu.be/lnvYlg4HOX4
5. https://youtu.be/GuhIefIGeuA
6. https://youtu.be/CjzdC0Eerfw
7. [Paid Course on Udemy: Threat Modeling using STRIDE by Taimur](https://www.udemy.com/course/threat-modeling-using-stride-masterclass/?couponCode=IND21PM)

### Books :books:
1. [Threat Modeling: Design for Security by Adam Shostack](https://amzn.to/3zfKefb)
2. [Threat Modeling by Izar Tarandach](https://amzn.to/4gEgbif)

After learning Threat Modeling, you can connect it with monitoring and incident response by exploring the [Blue Team, Detection & Response Study Plan](blue-team-detection-response-study-plan.md).
