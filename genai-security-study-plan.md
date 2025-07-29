# GenAI Security Study Plan (GenAI/LLM)

This study plan covers all the topics, concepts, blogs, videos, books, videos, newsletters etc. by keeping GenAI security in mind.

![GenAI Security Study Plan](images/genai-security-study-plan.png)

It should take 6-9 months to be good at GenAI security so that you can do one or more of the below listed things:
1. LLM pentesting
2. GenAI security assessment
3. Design and implement secure GenAI/LLM architectures for organizations.
4. Understanding of GenAI from GRC perspective
5. Knowledge of different GenAI security frameworks
6. AI enabled Threat Modeling or Threat Modeling of AI systems
7. Good grip on LLM safety, LLM Guardrails, Responsible AI, AI ethic etc.

It would help you in your current work as well as finding a new work using GenAI security skills.

Note: I am not writing anything that would require core AI/ML skills. It's all are done after keeping security focus in mind.

> [!IMPORTANT]  
> This field is still evolving, so our repo would too! Stay tuned!

## Organizational Capabilities that you can be job ready after going through mentioned study plan

### Security Assessments & Audits
- Conduct comprehensive GenAI security assessments using [OWASP LLM Top 10 framework](https://genai.owasp.org/)
- Perform LLM application penetration testing and vulnerability assessments
- Audit RAG (Retrieval Augmented Generation) implementations for security risks
- Evaluate prompt injection and jailbreaking vulnerabilities
- Assess model security, including adversarial attacks and data poisoning risks
- Review AI/ML supply chain security (model provenance, dependencies, third-party APIs)

### Governance, Risk & Compliance (GRC)
- Develop GenAI security policies and procedures aligned with [NIST AI RMF](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf)
- Create AI governance frameworks and risk management strategies
- Implement compliance controls for AI regulations ([EU AI Act](https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX%3A32021R0215), etc.)
- Establish AI ethics and responsible AI practices
- Design AI security awareness training programs for employees
- Create incident response plans specifically for AI/ML security incidents

### Architecture & Implementation
- Design secure AI/ML pipelines and infrastructure
- Implement secure GenAI architectures (secure RAG, fine-tuning, inference)
- Deploy AI security tools (LLM Guard, model scanning, prompt filtering)
- Establish secure model deployment and MLOps practices
- Design data privacy controls for AI training and inference data
- Implement monitoring and logging for AI systems

### Risk Management & Threat Modeling
- Conduct [AI/ML specific threat modeling exercises](https://www.matillion.com/blog/ai-threat-modeling)
- Assess business risks associated with GenAI implementations
- Develop risk mitigation strategies for AI adoption
- Create AI security metrics and KPIs for organizational reporting
- Establish AI risk registers and continuous monitoring processes

### Security Engineering & DevSecOps
- Integrate AI security into CI/CD pipelines
- Implement security testing for AI/ML models and applications
- Design secure model training environments and data handling processes
- Establish model version control and security scanning practices
- Create automated security testing for prompt injection and other LLM vulnerabilities

### Incident Response & Forensics
- Investigate AI/ML security incidents and breaches
- Develop playbooks for AI-specific security incidents
- Perform forensic analysis on compromised AI systems
- Create incident classification systems for AI/ML security events

### Consulting & Advisory Services
- Provide GenAI security consulting to organizations
- Conduct security reviews of vendor AI solutions
- Advise on secure AI procurement and third-party risk management
- Lead AI security transformation initiatives
- Mentor and train internal security teams on AI security

> [!NOTE]  
> ToC will highlight GenAI based concepts and learning reqources as and when we come across some awesome learning materials. 

## Study Plan ToC:
1. [GenAI/LLM Fundamental Concepts](#genai-fundamental-concepts) - 4 weeks
2. [Prompt Engineering](#prompt-engineering) - 1 week
3. [RAG (Retrieval Augmented Generation)](#rag) - 1-2 weeks
4. [Fine Tuning](#fine-tuning) - 2 weeks
5. [AI Agents](#ai-agents) - 1 week
6. [Agentic AI](#agentic-ai) - 1 week
7. [MCP (Model Context Protocol)](#mcp) - 1 week
8. [Certifications](#certifications) - on your bandwidth and wish
9. [GenAI Interview Questions](#genai-interview-questions)
10. [GenAI Security Tools](#genai-security-tools)

---

## GenAI Fundamental Concepts
**Duration: 4 weeks**

### Week 1: AI/ML Foundations & LLM Basics
- [ ] **Understanding AI vs ML vs Deep Learning vs GenAI**
  - [What are Foundation Models](https://www.datacamp.com/blog/what-are-foundation-models)
  - [Introduction to Large Language Models](https://www.coursera.org/learn/generative-ai-with-llms)
  - [Transformer Architecture Explained](https://jalammar.github.io/illustrated-transformer/)

- [ ] **LLM Architecture & Components**
  - Attention mechanisms and self-attention
  - Encoder-decoder architecture
  - Pre-training vs fine-tuning concepts
  - Token embeddings and positional encoding

- [ ] **Popular LLM Models**
  - GPT family (GPT-3.5, GPT-4, GPT-4o)
  - Claude (Anthropic)
  - Llama 2/3 (Meta)
  - Gemini (Google)
  - Open-source vs proprietary models

### Week 2: LLM Security Fundamentals
- [ ] **OWASP LLM Top 10**
  - [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/assets/PDF/OWASP-Top-10-for-LLMs-2023-v1_1.pdf)
  - LLM01: Prompt Injection
  - LLM02: Insecure Output Handling
  - LLM03: Training Data Poisoning
  - LLM04: Model Denial of Service
  - LLM05: Supply Chain Vulnerabilities
  - LLM06: Sensitive Information Disclosure
  - LLM07: Insecure Plugin Design
  - LLM08: Excessive Agency
  - LLM09: Overreliance
  - LLM10: Model Theft

- [ ] **Common Attack Vectors**
  - [Prompt Injection and Jailbreaking](https://ogre51.medium.com/security-of-llm-apps-prompt-injection-jailbreaking-fb9fc5c883a8)
  - Data poisoning attacks
  - Model extraction and theft
  - Adversarial examples
  - Membership inference attacks

### Week 3: AI Governance & Compliance
- [ ] **Regulatory Frameworks**
  - [NIST AI Risk Management Framework](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf)
  - [EU AI Act](https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX%3A32021R0215)
  - [NIST AI RMF Playbook](https://airc.nist.gov/AI_RMF_Knowledge_Base/Playbook)
  - ISO/IEC 23053:2022 (AI risk management)

- [ ] **AI Ethics & Responsible AI**
  - Bias and fairness in AI systems
  - Transparency and explainability
  - Privacy and data protection
  - Accountability and human oversight

### Week 4: Threat Modeling & Risk Assessment
- [ ] **AI-Specific Threat Modeling**
  - [Microsoft's AI/ML Threat Modeling](https://learn.microsoft.com/en-us/security/engineering/threat-modeling-aiml)
  - [AI Threat Modeling by Matillion](https://www.matillion.com/blog/ai-threat-modeling)
  - [Quick AI Threat Model Check](https://plot4.ai/assessments/quick-check)

- [ ] **Risk Assessment Frameworks**
  - [Adversarial Machine Learning (NIST)](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2023.pdf)
  - [Failure Modes in Machine Learning](https://securityandtechnology.org/wp-content/uploads/2020/07/failure_modes_in_machine_learning.pdf)
  - Business impact assessment for AI systems

**Hands-on Practice:**
- [ ] Complete [Gandalf LLM Security Challenge](https://gandalf.lakera.ai/)
- [ ] Try [Prompt Airlines CTF](https://promptairlines.com/)
- [ ] Practice with [LLM Security Portal](https://llmsecurity.net/)

---

## Prompt Engineering
**Duration: 1 week**

### Understanding Prompt Engineering
- [ ] **Prompt Engineering Fundamentals**
  - What is prompt engineering and why it matters for security
  - Types of prompts: zero-shot, few-shot, chain-of-thought
  - Prompt structure and best practices
  - Context window limitations and management

- [ ] **Security-Focused Prompt Engineering**
  - Defensive prompt engineering techniques
  - Input validation through prompts
  - Output sanitization strategies
  - Prompt injection prevention techniques

### Advanced Prompt Techniques
- [ ] **Prompt Injection Attacks**
  - Direct prompt injection
  - Indirect prompt injection
  - Jailbreaking techniques
  - Prompt leaking attacks

- [ ] **Defensive Strategies**
  - Prompt templates and parameterization
  - Input filtering and validation
  - Output monitoring and filtering
  - Role-based prompt design

**Hands-on Practice:**
- [ ] Practice prompt injection techniques on safe platforms
- [ ] Design secure prompt templates
- [ ] Test prompt robustness against various attack vectors

---

## RAG (Retrieval Augmented Generation)
**Duration: 1-2 weeks**

### Week 1: RAG Fundamentals
- [ ] **Understanding RAG Architecture**
  - [RAG: The Essential Guide](https://www.nightfall.ai/ai-security-101/retrieval-augmented-generation-rag)
  - [Why RAG is Revolutionising GenAI](https://www.immuta.com/guides/data-security-101/retrieval-augmented-generation-rag/)
  - Components: Retrieval system, knowledge base, generation model
  - Vector databases and embeddings
  - Chunking strategies and document processing

- [ ] **RAG Implementation Patterns**
  - Simple RAG vs Advanced RAG
  - Multi-step reasoning with RAG
  - Hybrid search approaches
  - RAG with fine-tuned models

### Week 2: RAG Security (Optional - for deeper understanding)
- [ ] **RAG-Specific Security Risks**
  - [Riding the RAG Trail: Access, Permissions and Context](https://www.lasso.security/blog/riding-the-rag-trail-access-permissions-and-context)
  - [Security Risks with RAG Architectures](https://ironcorelabs.com/security-risks-rag/)
  - [Mitigating Security Risks in RAG Applications](https://cloudsecurityalliance.org/blog/2023/11/22/mitigating-security-risks-in-retrieval-augmented-generation-rag-llm-applications)

- [ ] **RAG Security Best Practices**
  - Access control for knowledge bases
  - Data privacy in retrieval systems
  - Context injection attacks
  - Information leakage through retrieval
  - Secure document processing pipelines

**Hands-on Practice:**
- [ ] Build a simple RAG system with security controls
- [ ] Test for information leakage vulnerabilities
- [ ] Implement access controls for knowledge bases

---

## Fine Tuning
**Duration: 2 weeks**

### Week 1: Fine-Tuning Fundamentals
- [ ] **Understanding Fine-Tuning**
  - Pre-training vs fine-tuning vs prompt engineering
  - Types of fine-tuning: full, parameter-efficient (LoRA, QLoRA)
  - When to use fine-tuning vs other approaches
  - Data requirements and preparation

- [ ] **Fine-Tuning Techniques**
  - Supervised fine-tuning (SFT)
  - Reinforcement Learning from Human Feedback (RLHF)
  - Constitutional AI approaches
  - Domain-specific fine-tuning

### Week 2: Fine-Tuning Security
- [ ] **Security Considerations in Fine-Tuning**
  - Training data security and privacy
  - Model poisoning through fine-tuning
  - Backdoor attacks in fine-tuned models
  - Model extraction risks

- [ ] **Secure Fine-Tuning Practices**
  - Data sanitization and validation
  - Secure training environments
  - Model versioning and provenance
  - Testing fine-tuned models for security

**Hands-on Practice:**
- [ ] Fine-tune a small model with security considerations
- [ ] Test for data leakage in fine-tuned models
- [ ] Implement secure fine-tuning pipelines

---

## AI Agents
**Duration: 1 week**

### Understanding AI Agents
- [ ] **AI Agent Fundamentals**
  - What are AI agents and how they differ from simple LLMs
  - Agent architectures: ReAct, Plan-and-Execute, Multi-agent systems
  - Tool use and function calling
  - Memory and state management in agents

- [ ] **Types of AI Agents**
  - Conversational agents
  - Task-specific agents
  - Autonomous agents
  - Multi-agent systems and collaboration

### AI Agent Security
- [ ] **Security Risks with AI Agents**
  - Excessive agency and unauthorized actions
  - Tool misuse and privilege escalation
  - Agent-to-agent communication security
  - Persistent memory security risks

- [ ] **Securing AI Agents**
  - Principle of least privilege for agents
  - Action validation and approval workflows
  - Monitoring agent behavior and decisions
  - Secure tool integration patterns

**Hands-on Practice:**
- [ ] Build a simple AI agent with security controls
- [ ] Test agent behavior under various scenarios
- [ ] Implement monitoring for agent actions

---

## Agentic AI
**Duration: 1 week**

### Advanced Agentic Systems
- [ ] **Agentic AI Concepts**
  - Autonomous decision-making systems
  - Goal-oriented AI behavior
  - Planning and reasoning in agentic systems
  - Human-AI collaboration patterns

- [ ] **Agentic AI Architectures**
  - Multi-agent orchestration
  - Hierarchical agent systems
  - Distributed agentic networks
  - Agent communication protocols

### Security in Agentic AI
- [ ] **Unique Security Challenges**
  - Emergent behaviors in agentic systems
  - Goal misalignment and specification gaming
  - Inter-agent security and trust
  - Scalability of security controls

- [ ] **Governance for Agentic AI**
  - Establishing boundaries and constraints
  - Monitoring and auditing agentic behavior
  - Human oversight and intervention mechanisms
  - Ethical considerations in autonomous systems

**Hands-on Practice:**
- [ ] Design security controls for agentic systems
- [ ] Analyze case studies of agentic AI failures
- [ ] Develop monitoring strategies for autonomous agents

---

## MCP (Model Context Protocol)
**Duration: 1 week**

### Understanding MCP
- [ ] **MCP Fundamentals**
  - What is Model Context Protocol
  - MCP architecture and components
  - Client-server communication patterns
  - Resource management and sharing

- [ ] **MCP Implementation**
  - Setting up MCP servers and clients
  - Resource discovery and access
  - Tool integration through MCP
  - Context sharing between applications

### MCP Security
- [ ] **Security Considerations**
  - Authentication and authorization in MCP
  - Resource access control
  - Data privacy in context sharing
  - Network security for MCP communications

- [ ] **Best Practices**
  - Secure MCP server deployment
  - Client-side security measures
  - Monitoring MCP interactions
  - Incident response for MCP systems

**Hands-on Practice:**
- [ ] Set up a secure MCP environment
- [ ] Implement access controls for MCP resources
- [ ] Test MCP security configurations

---

## Certifications
**Duration: Based on your bandwidth and goals**

### AI/ML Security Certifications
- [ ] **Certified AI/ML Pentester**
  - [SecOps Group Certification](https://secops.group/product/certified-ai-ml-pentester/)
  - Covers LLM penetration testing methodologies
  - Hands-on practical assessments

- [ ] **Cloud AI Security Certifications**
  - AWS Machine Learning Specialty
  - Google Cloud Professional ML Engineer
  - Azure AI Engineer Associate
  - Focus on security aspects of cloud AI services


### Vendor-Specific Certifications
- [ ] **OpenAI Safety and Alignment**
- [ ] **Anthropic Constitutional AI**
- [ ] **Microsoft Responsible AI**
- [ ] **Google AI Ethics**

**Preparation Resources:**
- [ ] [AttackIQ Foundation of AI Security](https://www.academy.attackiq.com/courses/foundations-of-ai-security)
- [ ] [Coursera AI for Cybersecurity Specialization](https://www.coursera.org/specializations/ai-for-cybersecurity)
- [ ] [IBM GenAI for Cybersecurity Professionals](https://www.coursera.org/specializations/generative-ai-for-cybersecurity-professionals)

---

## GenAI Interview Questions

### Technical Questions
- [ ] **LLM Fundamentals**
  - Explain the transformer architecture and its security implications
  - What are the key differences between GPT, BERT, and T5 models?
  - How do attention mechanisms work and what security risks do they pose?
  - Describe the training process of large language models

- [ ] **Security-Specific Questions**
  - Walk through the OWASP LLM Top 10 and provide examples
  - How would you test an LLM application for prompt injection vulnerabilities?
  - Explain the difference between direct and indirect prompt injection
  - What are the main security considerations when implementing RAG?
  - How would you secure a fine-tuning pipeline?

### Scenario-Based Questions
- [ ] **Risk Assessment Scenarios**
  - "A company wants to implement a customer service chatbot using GPT-4. What security risks would you identify?"
  - "How would you conduct a security assessment of an existing LLM application?"
  - "Design a secure architecture for a RAG-based document Q&A system"

- [ ] **Incident Response Scenarios**
  - "An LLM application is leaking sensitive customer data. How would you investigate?"
  - "Users report that the chatbot is providing inappropriate responses. What's your approach?"
  - "A competitor seems to have extracted your fine-tuned model. How do you respond?"

### Governance and Compliance
- [ ] **Regulatory Questions**
  - How does the EU AI Act impact LLM deployments?
  - What are the key components of NIST AI RMF?
  - How would you implement AI governance in an organization?
  - What metrics would you use to measure AI security posture?

### Hands-on Technical Challenges
- [ ] **Practical Exercises**
  - Demonstrate prompt injection techniques
  - Show how to implement LLM Guard or similar tools
  - Explain model scanning and vulnerability detection
  - Design monitoring and alerting for LLM applications

---

## GenAI Security Tools

### Open Source Security Tools
- [ ] **LLM Guard by ProtectAI**
  - [GitHub Repository](https://github.com/protectai/llm-guard)
  - [Playground](https://huggingface.co/spaces/protectai/llm-guard-playground)
  - Input/output filtering and sanitization
  - Prompt injection detection
  - Sensitive data detection and redaction

- [ ] **Model Scanning Tools**
  - [ModelScan by ProtectAI](https://github.com/protectai/modelscan)
  - Scans AI/ML models for security vulnerabilities
  - Detects malicious code in model files
  - Supports multiple model formats

- [ ] **AI/ML Exploit Tools**
  - [AI Exploits by ProtectAI](https://github.com/protectai/ai-exploits)
  - Collection of AI/ML security exploits
  - Educational and testing purposes
  - Demonstrates common attack vectors

### Commercial Security Platforms
- [ ] **Lakera Guard**
  - Real-time LLM security monitoring
  - Prompt injection detection
  - Content filtering and moderation
  - API-based integration

- [ ] **Robust Intelligence**
  - AI security and monitoring platform
  - Model validation and testing
  - Continuous monitoring for drift and attacks
  - Enterprise-grade security controls

- [ ] **WhyLabs**
  - ML monitoring and observability
  - Data drift detection
  - Model performance monitoring
  - Security-focused analytics

### Testing and Assessment Tools
- [ ] **Garak**
  - LLM vulnerability scanner
  - Automated testing for various attack types
  - Extensible framework for custom tests
  - Community-driven development

- [ ] **PromptFoo**
  - LLM evaluation and testing framework
  - Security-focused test cases
  - Automated red teaming capabilities
  - Integration with CI/CD pipelines

### Bug Bounty and Research Platforms
- [ ] **Huntr.com**
  - [World's first AI/ML bug bounty platform](https://huntr.com/)
  - Responsible disclosure for AI vulnerabilities
  - Community-driven security research
  - Rewards for finding AI security issues

### Monitoring and Observability
- [ ] **LangSmith**
  - LLM application monitoring
  - Trace analysis and debugging
  - Performance and security metrics
  - Integration with LangChain

- [ ] **Weights & Biases**
  - ML experiment tracking
  - Model monitoring and versioning
  - Security-focused metrics and alerts
  - Team collaboration features

### Cloud-Native Security Tools
- [ ] **AWS Bedrock Guardrails**
  - Content filtering and safety controls
  - Custom guardrail policies
  - Real-time monitoring and blocking
  - Integration with AWS services

- [ ] **Azure AI Content Safety**
  - Content moderation and filtering
  - Custom classification models
  - API-based integration
  - Multi-language support

- [ ] **Google Cloud AI Platform Security**
  - Model security scanning
  - Access controls and IAM
  - Audit logging and monitoring
  - Compliance reporting

### Implementation Checklist
- [ ] Evaluate tools based on your specific use case
- [ ] Set up monitoring and alerting for LLM applications
- [ ] Implement input/output filtering and validation
- [ ] Deploy model scanning in CI/CD pipelines
- [ ] Establish incident response procedures
- [ ] Regular security assessments and penetration testing
- [ ] Stay updated with latest tools and techniques

---

---
## Note: I will add the format and categories later. It's just a placeholder for now.

1. LLM CS-324 from Stanford University: https://stanford-cs324.github.io/winter2022/ 
2. COS 597G (Fall 2022): Understanding Large Language Models from Princeton University: https://www.cs.princeton.edu/courses/archive/fall22/cos597G/ 
3. Intro to LLM Security from WhyLabs (Youtube): https://www.youtube.com/watch?v=dj1H4g4YSlU
4. GenAI with LLM from Coursera: https://www.coursera.org/learn/generative-ai-with-llms#modules 
5. LLM Security: https://llmsecurity.net/
6. LLM AI Security and Governance Checklist from OWASP: https://owasp.org/www-project-top-10-for-large-language-model-applications/llm-top-10-governance-doc/LLM_AI_Security_and_Governance_Checklist.pdf
7. OWASP Top 10 for LLM Application: https://owasp.org/www-project-top-10-for-large-language-model-applications/assets/PDF/OWASP-Top-10-for-LLMs-2023-v1_1.pdf 
8. Web LLM attacks from portswigger: https://portswigger.net/web-security/llm-attacks 
9. LLM Pentesting exam: https://secops.group/product/certified-ai-ml-pentester/
10. Prompt injection jailbreaking: https://ogre51.medium.com/security-of-llm-apps-prompt-injection-jailbreaking-fb9fc5c883a8 
11. AI security challenges, CTF style: https://promptairlines.com/
12. Play another LLM security challenge with Gandalf: https://gandalf.lakera.ai/ 
13. Riding the RAG Trail: Access, Permissions and Context: https://www.lasso.security/blog/riding-the-rag-trail-access-permissions-and-context
14. Securing Risks with RAG Architectures: https://ironcorelabs.com/security-risks-rag/
15. Secure your RAG: https://ironcorelabs.com/security-risks-rag/ 
16. Mitigating Security Risks in Retrieval Augmented Generation (RAG) LLM Applications: https://cloudsecurityalliance.org/blog/2023/11/22/mitigating-security-risks-in-retrieval-augmented-generation-rag-llm-applications# 
17. RAG: The Essential Guide: https://www.nightfall.ai/ai-security-101/retrieval-augmented-generation-rag 
18. Why RAG is revolutionising GenAI: https://www.immuta.com/guides/data-security-101/retrieval-augmented-generation-rag/ 
19. PortSwigger LLM attacks: https://portswigger.net/web-security/llm-attacks
20. LLM Security portal: https://llmsecurity.net/
21. What are foundational models: https://www.datacamp.com/blog/what-are-foundation-models 
22. World’s first bug bounty platform for AI/ML: https://huntr.com/
23. Protect AI's OSS portfolio includes tools aimed at improving the security of AI/ML software: https://github.com/protectai
    1. LLM Guard: https://github.com/protectai/llm-guard 
    2. AI/ML exploits: https://github.com/protectai/ai-exploits 
    3. Model scan: https://github.com/protectai/modelscan 
    4. rebuff: https://github.com/protectai/rebuff 
    5. NB Defense: https://github.com/protectai/nbdefense 
24. Safeguarding LLm with llm-guard: https://medium.com/@dataenthusiast.io/language-models-at-risk-safeguarding-ai-with-llm-guard-11a3e7923af5
25. LLM Guard Playground: https://huggingface.co/spaces/protectai/llm-guard-playground
26. Courses:
    1. https://www.coursera.org/learn/generative-ai-with-llms (by DeepLearning and AWS)
    2. https://www.coursera.org/specializations/generative-ai-engineering-with-llms#courses
    3. https://www.coursera.org/specializations/generative-ai-for-cybersecurity-professionals (Specialization from IBM [3 courses])
    4. https://www.coursera.org/specializations/ai-for-cybersecurity (Specialisation from John Hopkins University)
27. NIST AI RMF Playbook: https://airc.nist.gov/AI_RMF_Knowledge_Base/Playbook
28. AI RMF: https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf
29. Adversarial Machine Learning: https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2023.pdf
30. Failure Models in Machine Learning:https://securityandtechnology.org/wp-content/uploads/2020/07/failure_modes_in_machine_learning.pdf 
31. A quick check on the AI Threat Model: https://plot4.ai/assessments/quick-check
32. Threat Modeling AI/ML by Microsoft: https://learn.microsoft.com/en-us/security/engineering/threat-modeling-aiml
33. Security Incident Response using LLM: https://engineering.mercari.com/en/blog/entry/20241206-streamlining-security-incident-response-with-automation-and-large-language-models/  
34. The foundation of AI Security by AttackIQ: https://www.academy.attackiq.com/courses/foundations-of-ai-security
