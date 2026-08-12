# Secure Code Review Study Plan

This study plan is designed to help you master the art of Secure Code Review. It covers methodologies, common vulnerabilities, tools, and best practices for identifying security flaws in source code.

## ToC
1. [Code Review Fundamentals](#code-review-fundamentals) - 2 weeks
2. [Common Vulnerabilities in Code](#common-vulnerabilities-in-code) - 2 weeks
3. [Process and Checklists](#process-and-checklists) - 2 weeks
4. [Reviewing AI-Generated Code](#reviewing-ai-generated-code) - 1-2 weeks
5. [Tools and Automation](#tools-and-automation) - 2 weeks
6. [Resources](#resources)

## Code Review Fundamentals
**Duration: 2 weeks**

Understand the basics of code review and why it's critical.

### Week 1-2: The Basics
1. **What is Secure Code Review?**
   - Difference between functional review and security review.
   - Manual vs Automated review.
2. **Code Review Strategies:**
   - **Top-down:** Start from high-level logic/entry points.
   - **Bottom-up:** Start from sensitive functions (sinks).
3. **Secure Coding Principles:**
   - Input Validation.
   - Output Encoding.
   - Least Privilege.
   - Defense in Depth.

## Common Vulnerabilities in Code
**Duration: 2 weeks**

Learn what to look for.

### Week 3-4: Spotting Bugs
1. **OWASP Top 10 (Code Perspective):**
   - **Injection:** SQLi, Command Injection (look for unparameterized queries, `eval()`, `exec()`).
   - **Broken Auth:** Hardcoded credentials, weak session management.
   - **XSS:** Lack of context-aware encoding.
   - **Insecure Deserialization:** Unsafe handling of serialized objects.
2. **Language-Specific Issues:**
   - **Java:** Deserialization, XXE.
   - **Python:** Pickle, `eval()`, Jinja2 SSTI.
   - **JavaScript/Node.js:** Prototype pollution, `eval()`.
3. **[CWE Top 25 – 2025 edition](https://cwe.mitre.org/top25/archive/2025/2025_cwe_top25.html)** (published Dec 2025, the current edition):
   - Top of the list: XSS (CWE-79) at #1, SQL injection (CWE-89) up to #2, CSRF (CWE-352) up to #3, Missing Authorization (CWE-862) up 5 places to #4, Out-of-bounds Write (CWE-787) down to #5.
   - New entries this edition: Buffer Copy without Checking Size of Input (CWE-120, #11), Stack-based Buffer Overflow (CWE-121, #14), Heap-based Buffer Overflow (CWE-122, #16) and Improper Access Control (CWE-284, #19) – memory-safety weaknesses are now listed at a finer granularity, and access control appears twice in different forms.
   - Use CWE IDs as your review vocabulary: they are what SAST rules, CVEs and remediation tickets are keyed on.

## Process and Checklists
**Duration: 2 weeks**

Structuring your review.

### Week 5-6: Systematic Review
1. **OWASP Secure Code Review Guide:**
   - Read the guide to understand the methodology.
2. **Checklists:**
   - Authentication & Authorization.
   - Data Validation.
   - Error Handling & Logging.
   - Cryptography (weak algos, hardcoded keys).
3. **Reviewing Business Logic:**
   - Race conditions.
   - Order of operations flaws.
   - Price manipulation.

## Reviewing AI-Generated Code
**Duration: 1-2 weeks**

Most code you review now had an assistant involved somewhere. The review skill is the same, but the *failure modes* are different, and the usual social shortcut ("a competent human wrote this and understood it") no longer holds.

### Week 7-8: The New Review Surface
1. **Why it needs the same or higher scrutiny than human code:**
   - AI-generated code is *fluent*: correct naming, clean structure, plausible comments – so it passes the eyeball test that reviewers actually use for triage.
   - The author often cannot explain it. If the submitter can't answer "why is this safe?", the review has to establish it from scratch.
   - Volume: assistants make it cheap to produce large diffs, so cap PR size and refuse to speed-read.
2. **Subtle logic bugs (the dominant class):**
   - Off-by-one and boundary handling, inverted or short-circuited conditionals, error paths that swallow failures and continue.
   - Authorization checks that are present but incomplete – e.g. authenticates the user, never checks object ownership (CWE-862 / CWE-284, both in the 2025 CWE Top 25).
   - Concurrency and state: assistants rarely reason about your app's actual locking or transaction model.
3. **Hallucinated APIs and packages (slopsquatting):**
   - Models invent import names. The USENIX Security 2025 study ["We Have a Package for You!"](https://www.usenix.org/conference/usenixsecurity25/presentation/spracklen) found ~19.7% of packages recommended across 576,000 samples from 16 LLMs did not exist (~5.2% for commercial models vs ~21.7% for open-source), yielding over 205,000 unique non-existent names – and 43% of hallucinated names recurred in all ten re-runs of the same prompt.
   - Repeatable hallucinations are the attack: an attacker registers the predicted name, and the next developer who accepts the suggestion installs it. This is *slopsquatting* – typosquatting where the model, not the typo, picks the target.
   - Review action: verify every newly added dependency exists, is the package you think it is, and is actually maintained – before you review a single line of the code that uses it. Pin and lock. Cross-check with the [Software Supply Chain Security](software-supply-chain-security-study-plan.md) plan.
   - Also check hallucinated *methods* on real libraries, and API usage that compiles but silently disables a security feature (e.g. a verify/validate flag invented or set wrong).
4. **Insecure defaults inherited from training data:**
   - Assistants reproduce the most common pattern on the internet and in your repo, not the most secure one: string-concatenated queries, disabled TLS verification, MD5/SHA-1 for passwords, permissive CORS, `debug=True`, secrets inline.
   - Sonar's *The State of Code, Vol. 2: Security* (July 2025) analysed 7.9B lines of code across 970,000 developers and 40,000 organisations and found ~1,200 security issues and ~170 confirmed vulnerabilities per million lines of code, with log injection the most common vulnerability and hardcoded credentials the most common hotspot (50% of discovered secrets were database passwords).
   - The useful framing from that report: "AI coding tools are excellent mimics" – your existing code quality becomes a supply-chain input to everything generated from it. Fixing your repo's most repeated bad pattern also reduces the AI-generated copies of it.
5. **Practical review habits:**
   - Ask the submitter to explain the security-relevant decisions; treat "the assistant wrote it" as a signal to review harder, not a reason to trust it.
   - Diff against the framework's documented safe idiom rather than against "does it look reasonable".
   - Keep the [GenAI Security Study Plan](genai-security-study-plan.md) in scope if you also review code that *calls* LLMs (prompt injection, tool-use authz) – a different problem from reviewing code an LLM wrote.

## Tools and Automation
**Duration: 2 weeks**

Enhancing manual review with tools.

### Week 9-10: SAST & IDE Plugins
1. **Static Application Security Testing (SAST):**
   - **SonarQube:** Setup and rule configuration.
   - **Semgrep:** Writing custom rules (highly recommended).
   - **CodeQL:** Querying code as data.
2. **IDE Plugins:**
   - Snyk, SonarLint.
3. **AI-assisted triage and review copilots (current tooling):**
   - LLM-backed triage layers sit on top of SAST to filter noise, explain a finding in the context of the surrounding code, and propose a fix: [Semgrep Assistant](https://semgrep.dev/docs/semgrep-assistant/overview), [GitHub Copilot Autofix for code scanning](https://docs.github.com/en/code-security/code-scanning/managing-code-scanning-alerts/responsible-use-autofix-code-scanning), [Snyk automatic fixes (DeepCode AI Fix)](https://docs.snyk.io/scan-with-snyk/snyk-code/manage-code-vulnerabilities/fix-code-vulnerabilities-automatically).
   - Use them to *prioritise*, not to decide. Treat a suggested fix as a patch from an unknown contributor: verify it removes the root cause rather than the symptom (e.g. escaping at the wrong layer, or adding a check the attacker can bypass).
   - Know the failure modes: confident-sounding wrong verdicts on business-logic and authorization findings, and dismissed true positives – the expensive kind of error.
4. **Limitations of Tools:**
   - Understanding false positives and false negatives.
   - Why manual review is still needed for logic bugs.

## Resources
### Guides
- [OWASP Code Review Guide](https://owasp.org/www-project-code-review-guide/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [CWE Top 25 – 2025 edition](https://cwe.mitre.org/top25/archive/2025/2025_cwe_top25.html) (current; [all editions](https://cwe.mitre.org/top25/))

### AI-Generated Code
- [We Have a Package for You! A Comprehensive Analysis of Package Hallucinations by Code Generating LLMs](https://www.usenix.org/conference/usenixsecurity25/presentation/spracklen) – USENIX Security 2025; the slopsquatting paper ([code and data](https://github.com/Spracks/PackageHallucination))
- [Sonar: The State of Code, Vol. 2: Security](https://www.sonarsource.com/resources/the-state-of-code-security-report/) (July 2025) – vulnerability data across 7.9B lines of code

### Tools
- [Semgrep](https://semgrep.dev/)
- [SonarQube](https://www.sonarqube.org/)
- [CodeQL](https://codeql.github.com/)
- [Semgrep Assistant](https://semgrep.dev/docs/semgrep-assistant/overview) / [Copilot Autofix](https://docs.github.com/en/code-security/code-scanning/managing-code-scanning-alerts/responsible-use-autofix-code-scanning) – AI-assisted finding triage and fix suggestions

### Practice
- [Secure Code Warrior](https://www.securecodewarrior.com/) (Free trial/community)
- [SonarQube Rules documentation](https://docs.sonarsource.com/sonarqube-server/quality-standards-administration/managing-rules/rules) (Learn by seeing bad vs good code – the old `rules.sonarsource.com` explorer has been retired; browse the rules catalog from a SonarQube Server/Cloud instance)
