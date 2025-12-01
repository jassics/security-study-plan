# Secure Code Review Study Plan

This study plan is designed to help you master the art of Secure Code Review. It covers methodologies, common vulnerabilities, tools, and best practices for identifying security flaws in source code.

## ToC
1. [Code Review Fundamentals](#code-review-fundamentals) - 2 weeks
2. [Common Vulnerabilities in Code](#common-vulnerabilities-in-code) - 2 weeks
3. [Process and Checklists](#process-and-checklists) - 2 weeks
4. [Tools and Automation](#tools-and-automation) - 2 weeks
5. [Resources](#resources)

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

## Tools and Automation
**Duration: 2 weeks**

Enhancing manual review with tools.

### Week 7-8: SAST & IDE Plugins
1. **Static Application Security Testing (SAST):**
   - **SonarQube:** Setup and rule configuration.
   - **Semgrep:** Writing custom rules (highly recommended).
   - **CodeQL:** Querying code as data.
2. **IDE Plugins:**
   - Snyk, SonarLint.
3. **Limitations of Tools:**
   - Understanding false positives and false negatives.
   - Why manual review is still needed for logic bugs.

## Resources
### Guides
- [OWASP Secure Code Review Guide](https://owasp.org/www-project-secure-code-review-guide/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [CWE Top 25](https://cwe.mitre.org/top25/archive/2023/2023_cwe_top25.html)

### Tools
- [Semgrep](https://semgrep.dev/)
- [SonarQube](https://www.sonarqube.org/)
- [CodeQL](https://codeql.github.com/)

### Practice
- [Secure Code Warrior](https://www.securecodewarrior.com/) (Free trial/community)
- [SonarQube Rules Explorer](https://rules.sonarsource.com/) (Learn by seeing bad vs good code)
