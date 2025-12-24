# Mobile Application Security Study Plan

This study plan is based on milestones. So, check how much you can cover within the timeline. The more you cover the topics, the better candidate you are for job roles which require good knowledge of mobile (Android/iOS) application security.

Also, I assume you have already checked and are comfortable with [Common Security Skills study plan](common-skills-study-plan.md) and [Web Pentest study plan](web-pentest-study-plan.md).

It will cover what you need to learn to test and secure mobile apps, including client, API, and backend aspects.

**How this connects:** Use this plan together with the [Web Pentest](web-pentest-study-plan.md), [Application Security](application-security-study-plan.md), and [API Security](api-security-study-plan.md) study plans, since mobile apps almost always talk to web backends and APIs.

---

## In short

1. Mobile security is not just “web in a smaller screen” – there are **platform-specific risks**.  
2. You must understand Android and iOS app models and storage.  
3. You should be comfortable proxying traffic, analyzing APK/IPA, and using common tools.  
4. You should align with [OWASP MASVS/MSTG](https://mas.owasp.org/) for methodology.  
5. You must consider both the app and its backend APIs.

---

## ToC

1. [Mobile Fundamentals](#mobile-fundamentals) - 2 weeks  
2. [Android Security](#android-security) - 3-4 weeks  
3. [iOS Security](#ios-security) - 3-4 weeks  
4. [Mobile Testing Methodology (OWASP MASVS/MSTG)](#mobile-testing-methodology-owasp-masvsmstg) - 3-4 weeks  
5. [Tools & Labs](#tools--labs) - 3-4 weeks  
6. [Books](#books)  
7. [Videos](#videos)  
8. [Courses](#courses)  
9. [Certifications](#certifications)  
10. [Interview Questions](#interview-questions)

---

## Mobile Fundamentals

**Duration: 2 weeks**

Goal: understand how mobile apps are built and deployed.

### Week 1-2: Architecture

1. **Mobile App Models:** native, hybrid, cross-platform.  
2. **Typical Architecture:** client app ↔ API ↔ backend services.  
3. **Data Storage & Permissions:** local storage, keychain/keystore, runtime permissions.

---

## Android Security

**Duration: 3-4 weeks**

Goal: understand Android internals and common vulnerabilities.

### Week 3-6: Android Basics & Risks

1. **Android Architecture:** APK structure, components (activities, services, receivers).  
2. **Permissions & Manifest:** exported components, dangerous permissions.  
3. **Common Issues:** insecure storage, hardcoded secrets, insecure logging.  
4. **Reverse Engineering Basics:** decompiling APKs, basic static analysis.

---

## iOS Security

**Duration: 3-4 weeks**

Goal: understand iOS app model and security controls.

### Week 7-10: iOS Basics & Risks

1. **iOS Architecture:** IPA packages, app sandboxing.  
2. **Keychain & Secure Storage:** where secrets go and how they can leak.  
3. **Common Issues:** insecure local storage, weak jailbreak detection, insecure URL schemes.  
4. **High-Level Static & Dynamic Analysis:** understanding what’s possible.

---

## Mobile Testing Methodology (OWASP MASVS/MSTG)

**Duration: 3-4 weeks**

Goal: follow a structured approach for mobile security testing.

### Week 11-14: Methodology

1. **OWASP MASVS:** security requirements categories (architecture, storage, crypto, etc.).  
2. **OWASP MSTG:** test cases and practical guidance.  
3. **Testing Focus Areas:**  
   - Local data storage.  
   - Authentication and session management.  
   - Network communication and certificate pinning.  
   - Code tampering and reverse engineering resistance.

---

## Tools & Labs

**Duration: 3-4 weeks**

Goal: get hands-on experience.

### Week 15-18: Practice

1. **Proxying & Interception:** Burp/ZAP, cert installation, bypassing certificate pinning (at high level).  
2. **Emulators & Devices:** basic setup for Android and iOS testing.  
3. **Deliberately Vulnerable Apps:** practice on intentionally vulnerable mobile apps from reputable sources.  
4. **Backend APIs:** reuse techniques from [API Security Study Plan](api-security-study-plan.md) to test the APIs mobile apps use.

---

## Books

1. Any good book focused on **mobile application security** or testing.  
2. Web and API security books to complement backend testing knowledge.

---

## Videos

1. Conference talks on Android and iOS application security.  
2. Walkthroughs of mobile app security assessments.  
3. Official platform security overviews from Google/Apple.

---

## Courses

1. Mobile application security or mobile pentesting courses with hands-on labs.  
2. Android/iOS development basics (optional but helpful to understand code).  
3. General web/API security courses to strengthen backend testing.

---

## Certifications

1. Mobile security-focused certifications if they align with your goals.  
2. General offensive security certs (OSCP/eWPTX/etc.) if you want broader pentest credentials.

---

## Interview Questions

You can reuse questions from Web & API Security but add mobile specifics:

1. How would you test a mobile banking app for insecure storage?  
2. What is OWASP MASVS and how would you use it in an assessment?  
3. How would you approach bypassing certificate pinning (conceptually)?  
4. What are common pitfalls in mobile auth and session management?
