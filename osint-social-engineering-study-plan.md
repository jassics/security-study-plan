# OSINT & Social Engineering Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for roles that benefit from strong OSINT and social engineering awareness (red team, blue team, GRC, security awareness).

Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md).

This plan focuses on **ethical** OSINT and social engineering fundamentals.

**How this connects:** OSINT and social engineering skills complement [Web Pentest](web-pentest-study-plan.md) and red teaming, help [GRC](grc-study-plan.md) and [Blue Team, Detection & Response](blue-team-detection-response-study-plan.md) understand human-focused risks, and enrich [Threat Modeling](threat-modeling-study-plan.md) by adding people and process attack vectors.

---

## In short

1. OSINT is about collecting and correlating **public information** from many sources.  
2. Social engineering is about manipulating human behavior – use it *ethically* and within rules of engagement.  
3. Both attackers and defenders use OSINT and SE (offense and awareness/training).  
4. Legal and ethical boundaries are critical.  
5. Generative AI has made convincing phishing, cloned voices and deepfaked video meetings cheap - so "it looked and sounded like them" is no longer evidence of identity. Learn this alongside the classic vectors, not instead of them.

---

## ToC

1. [OSINT Fundamentals](#osint-fundamentals) - 2 weeks  
2. [People & Infrastructure OSINT](#people--infrastructure-osint) - 3-4 weeks  
3. [Social Engineering Fundamentals](#social-engineering-fundamentals) - 2-3 weeks  
4. [AI-Enabled Social Engineering: Deepfakes & Voice Cloning](#ai-enabled-social-engineering-deepfakes--voice-cloning) - 2-3 weeks  
5. [Offensive Use Cases (Ethical)](#offensive-use-cases-ethical) - 2-3 weeks  
6. [Defensive Use Cases & Awareness](#defensive-use-cases--awareness) - 2-3 weeks  
7. [Books](#books)  
8. [Videos](#videos)  
9. [Courses](#courses)  
10. [Interview Questions](#interview-questions)

---

## OSINT Fundamentals

**Duration: 2 weeks**

Goal: understand what OSINT is and is not.

### Week 1-2: Core Concepts

1. **Definition & Scope:** open sources, legality, ethics.  
2. **Data Types:** people, organizations, infrastructure, financial, technical.  
3. **OSINT Process:** define objective → collect → analyze → report.

---

## People & Infrastructure OSINT

**Duration: 3-4 weeks**

Goal: learn practical OSINT collection for people and infrastructure.

### Week 3-6: Practical OSINT

1. **People OSINT:** profiles, resumes, public posts, breached data (viewing only where legally allowed).  
2. **Company OSINT:** org charts, technologies used, job postings, press releases.  
3. **Infrastructure OSINT (high level):** public DNS records, certificate transparency logs, basic passive fingerprinting.

---

## Social Engineering Fundamentals

**Duration: 2-3 weeks**

Goal: understand social engineering tactics and psychology.

### Week 7-9: SE Basics

1. **Psychological Principles:** authority, scarcity, reciprocity, social proof, etc. These are unchanged by AI - synthetic media just makes the *delivery* more convincing.  
2. **Common Vectors:** phishing, vishing, smishing, pretexting, physical SE - and, alongside them, **AI-synthesized voice and video** used inside those same vectors (a vishing call with a cloned voice, a pretext backed by a deepfaked video meeting). AI adds a delivery channel; it does not replace the classic ones, and plain text phishing is still the highest-volume vector.  
3. **Real-World Examples:** review case studies (within legal/ethical material).  
4. **Framework mapping:** MITRE ATT&CK [T1656 Impersonation](https://attack.mitre.org/techniques/T1656/) is the technique to reference when documenting these attacks.

---

## AI-Enabled Social Engineering: Deepfakes & Voice Cloning

**Duration: 2-3 weeks**

Goal: understand how generative AI changed social engineering economics between 2023 and 2026 - not as a novelty, but as the dominant current trend in this domain. The core skill is still recognising a manipulation attempt; what changed is that "it looked and sounded like my CFO" is no longer proof of anything.

### Week 10-12: Synthetic Media as an SE Vector

1. **AI-generated phishing content.** KnowBe4's *2025 Phishing Threat Trends Report* found that **82.6%** of the phishing emails it analysed showed some sign of AI use, and that 76.4% of campaigns used polymorphic (AI-varied) content to evade filters ([KnowBe4 press release](https://www.knowbe4.com/press/new-knowbe4-report-reveals-a-spike-in-ransomware-payloads-and-ai-powered-polymorphic-phishing-campaigns)). Treat vendor telemetry as directional rather than a measured industry ground truth - the methodology is a single vendor's mail flow - but the direction is consistent across reporting: fluent, well-targeted phishing is now cheap, so "bad grammar" is a dead detection heuristic.
2. **Voice cloning / vishing.** A few seconds of public audio (a conference talk, a podcast, an earnings call, a voicemail greeting) is enough to clone a voice. The FBI issued a public service announcement on 15 May 2025 about an ongoing campaign using AI-generated voice and text messages to impersonate senior US officials and pivot to their contacts ([FBI IC3 PSA I-051525-PSA](https://www.ic3.gov/PSA/2025/PSA250515)).
3. **The OSINT-to-deepfake attack chain.** This is where the two halves of this study plan meet. Work through the chain end to end:
   1. **Collect** - OSINT identifies who has payment authority, who reports to whom, who is travelling or unreachable, plus public audio/video of the person to be impersonated (LinkedIn, YouTube, webinars, press interviews, earnings calls).
   2. **Model** - train/clone voice or face from that public media.
   3. **Pretext** - a plausible, urgent, confidentiality-flavoured scenario derived from real company context (an acquisition, a quarter-end payment, a "secret transaction").
   4. **Deliver** - email or chat first for the initial ask, then a live call or video meeting to defeat the target's scepticism.
   5. **Cash out** - multiple smaller transfers across several accounts to stay under review thresholds.
4. **Worked example - the Arup Hong Kong case.** In January 2024 a finance employee in the Hong Kong office of engineering firm Arup was targeted by a phishing email purporting to be from the UK-based CFO requesting a confidential transaction. The employee was initially suspicious. The attackers then put them on a video conference in which *every other participant, including the CFO and other familiar colleagues, was AI-generated* from publicly available footage of Arup executives. Convinced, the employee made 15 transfers totalling about **HK$200m (~US$25m)** to five Hong Kong bank accounts. Arup was only publicly identified in May 2024; its CIO stressed that no systems were breached and no data was taken - this was social engineering, technologically enhanced. Sources: [CNN, Feb 2024](https://www.cnn.com/2024/02/04/asia/deepfake-cfo-scam-hong-kong-intl-hnk), [CNN, May 2024 (Arup named)](https://www.cnn.com/2024/05/16/tech/arup-deepfake-scam-loss-hong-kong-intl-hnk). Map it back to step 1-5 above and ask which single control would have broken the chain.
5. **Detection is not the primary control.** Deepfake detection tooling exists but is an arms race and degrades on compressed, real-world video calls. Do not build a defence that depends on a human or a classifier spotting the fake.
6. **Read the baseline government guidance:** NSA/FBI/CISA, *Contextualizing Deepfake Threats to Organizations* (Cybersecurity Information Sheet, 12 September 2023) - [CISA announcement page with the PDF link](https://www.cisa.gov/news-events/alerts/2023/09/12/nsa-fbi-and-cisa-release-cybersecurity-information-sheet-deepfake-threats). It specifically calls out executive impersonation for BEC-style fraud.
7. **Ethics and law.** Cloning a real colleague's voice or face - even for an authorized awareness exercise - carries consent, privacy and (in some jurisdictions) biometric/likeness-law implications well beyond a normal phishing simulation. Get explicit written sign-off from legal and from the impersonated individual before any synthetic-media exercise, and never publish the artefacts.

---

## Offensive Use Cases (Ethical)

**Duration: 2-3 weeks**

Goal: understand how OSINT and SE are used in engagements with proper authorization.

### Week 13-15: Red Team View

1. **Pre-Engagement:** scoping, rules of engagement, legal sign-offs. If synthetic voice/video is in scope, it needs its own explicit authorization and named-individual consent (see the AI-Enabled section above).  
2. **Reconnaissance:** using OSINT to identify targets, email formats, tech stack (high level) - and, in a modern engagement, how much public audio/video of key executives exists, since that is itself an exposure finding worth reporting.  
3. **Campaign Design (Conceptual):** planning ethical phishing simulations and pretexts across channels - email, voice, SMS, chat platforms, and (only with sign-off) AI-synthesized voice/video pretexts.  
4. **Reporting the human path:** describe the full chain (OSINT input to final action) rather than just "N% clicked", so defenders can see which step was cheapest to break.

---

## Defensive Use Cases & Awareness

**Duration: 2-3 weeks**

Goal: use OSINT and SE knowledge to improve defenses.

### Week 16-18: Blue & GRC View

1. **Exposure Reduction:** minimizing unnecessary public data about staff and systems - now including public audio/video footprint of executives and finance staff.  
2. **Awareness Training:** explaining common SE patterns and red flags. Retire the outdated tells (bad grammar, odd formatting) and teach *situational* red flags instead: urgency, secrecy, an unusual payment path, and pressure to bypass a normal process.  
3. **Simulations & Metrics:** phishing simulations, reporting rates, improvement over time.  
4. **Process controls that survive a perfect deepfake.** Because detection is unreliable, the effective defences are procedural:
   1. **Out-of-band verification** on a separately-initiated channel (call back on the number in the corporate directory - never a number or link supplied in the request).
   2. **Pre-agreed verbal code phrases** for high-risk requests, agreed over a different channel. Recommended in the NSA/FBI/CISA deepfake guidance and the [FBI's May 2025 PSA](https://www.ic3.gov/PSA/2025/PSA250515).
   3. **Dual authorization and payment-change controls** for funds transfers and vendor bank-detail changes, with no exception path for "the CEO said it was urgent".
   4. **Explicit permission to slow down.** Publish that no executive will ever penalise an employee for pausing a payment to verify. The Arup case turned on an employee whose initial suspicion was overridden.
   5. **A named escalation route** and a rehearsed playbook for suspected impersonation, including how to recall/freeze a transfer fast.
5. **Media provenance (emerging):** [C2PA](https://c2pa.org/) content credentials and similar provenance signing are being adopted for verifying media origin - useful context, not yet a control you can rely on for a live video call.

---

## Books

1. Books on social engineering and human-based attacks from reputable authors.  
2. Books focused on OSINT techniques and case studies.

---

## Videos

1. Talks on social engineering from security conferences.  
2. OSINT practical walkthroughs (within ethical & legal boundaries).  
3. Corporate awareness-style videos explaining phishing and SE.

---

## Courses

1. Intro OSINT courses that emphasize legality and ethics.  
2. Social engineering awareness and simulation courses.  
3. Red team or phishing simulation courses if relevant to your job.

---

## Interview Questions

1. How would you use OSINT during a security assessment while staying within legal and ethical boundaries?  
2. How would you design an internal phishing awareness campaign?  
3. How can OSINT and SE knowledge help improve an organization's security posture?  
4. A finance employee receives a video call from someone who looks and sounds exactly like the CFO, authorising an urgent confidential transfer. Which controls would stop this, and why is deepfake-detection tooling not the primary answer?  
5. Walk me through an OSINT-to-deepfake attack chain and identify the cheapest step for a defender to break.  
6. AI-generated phishing removes the traditional "bad grammar" tell. How would you change your awareness programme and your detection logic in response?  
7. What legal and ethical constraints apply if you want to include cloned voice or video in an authorized red team engagement?
