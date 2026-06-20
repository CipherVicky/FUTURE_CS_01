# 🔐 Web Application Penetration Test — testfire.net

![Type](https://img.shields.io/badge/Type-Black--Box%20Pentest-red?style=flat-square)
![Scope](https://img.shields.io/badge/Scope-XSS%20%26%20SQL%20Injection-orange?style=flat-square)
![OWASP](https://img.shields.io/badge/OWASP-A03%3A2021-blue?style=flat-square)
![Date](https://img.shields.io/badge/Test%20Date-19%20June%202026-lightgrey?style=flat-square)

> ⚠️ **Authorised testing only.** `testfire.net` is IBM's intentionally vulnerable demo application designed for security research and education. Never reproduce these techniques on systems you do not own or have explicit written permission to test.

---

## 🌐 Website Tested

| Field | Details |
|---|---|
| **Target URL** | http://testfire.net |
| **Application** | AltoroMutual Online Banking Demo |
| **Hosted By** | IBM (intentionally vulnerable demo) |
| **Environment** | Internet-facing, authorised for security testing |
| **Test Date** | 19-20 June 2026 |
| **Tester** | Bura Sam vivek |

AltoroMutual is a fictional online banking application maintained by IBM as a safe, legal target for practising web application security testing techniques.

---

## 🎯 Scope

The assessment focused on **OWASP A03:2021 – Injection and OWASP A01:2021/A05:2021** related security weaknesses.

### In-Scope Endpoints

| Endpoint | Method | Parameter(s) | Attack Type |
|---|---|---|---|
| `/default.aspx` | GET | `URL Fragment (#fragment)` | DOM-Based XSS |
| `/sendFeedback` | POST | `comment`, `name` | Reflected Cross-Site Scripting (XSS) |
| `/doLogin` | POST | `uid`, `passw` | SQL Injection (SQLi) |
| `/sitemap.xml` | GET | `Response Header` | Missing CSP HeaderPARA |
| `/login.jsp` | GET | Login Form | Cross-Site Request Forgery (CSRF) |
| `/` | GET | `N/A` | Clickjacking |

### Findings Overview

| ID | Vulnerability | Severity | CVSS v3.1 |
|---|---|---|---|
| VA-001 | DOM-Based XSS — `/default.aspx` | 🟠 HIGH| 8.8 |
| VA-002 | Reflected Cross-Site Scripting (XSS) — `/sendFeedback` | 🟠 HIGH | 6.1 - 8.8 |
| VA-003 | SQL Injection — `/doLogin` | 🔴 CRITICAL | 9.8 |
| VA-004 | Missing CSP HeaderPARA — `/sitemap.xml` | 🟡 MEDIUM | 5.3 |
| VA-005 | Cross-Site Request Forgery (CSRF) — `/login.jsp` | 🟡 MEDIUM | 6.5 |
| VA-006 | Clickjacking — `/` | 🟡 MEDIUM | 6.5 |

**6 vulnerabilities confirmed — 3 Critical · 2 High · 1 Medium**

---

## 🛠️ Tools Used

| Tool | Version | Purpose |
|---|---|---|
| **Burp Suite Community** | 2023.x | HTTP proxy, request interception, manual payload delivery |
| **OWASP ZAP** | 2.14 | Automated scanning and spider crawl |
| **SQLMap** | 1.7.x | SQL injection detection and automated exploitation |
| **Nikto** | 2.1.6 | Web server misconfiguration and CVE scanning |
| **Firefox DevTools** | 125+ | DOM inspection, JavaScript debugging, cookie analysis |


## 📁 Repository Structure


├── README.md
├── VULNERABILITY_ASSESSMENT_REPORT.pdf
└── evidence/
    ├── VA-001_Reflected_XSS.jpg
    ├── VA-002_Stored_XSS.jpg
    ├── VA-003_DOM_XSS.jpg
    ├── VA-004_SQLi_ErrorBased.jpg
    ├── VA-005_SQLi_UNION.jpg
    └── VA-006_SQLi_BlindBoolean.jpg

*Prepared by Sam vivek · 20 June 2026 · CONFIDENTIAL — distribute only to authorised personnel*
