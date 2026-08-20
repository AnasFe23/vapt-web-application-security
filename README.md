# 🎯 Web Application Vulnerability Assessment & Penetration Testing (VAPT)

[![Course](https://img.shields.io/badge/Course-Hacking%20Techniques%20%26%20Prevention-red.svg)](https://www.utem.edu.my/)
[![OWASP Top 10](https://img.shields.io/badge/Standard-OWASP%20Top%2010%20(2021)-blue.svg)](https://owasp.org/Top10/)
[![Findings](https://img.shields.io/badge/Verified%20Findings-17%20Documented-critical.svg)]()
[![Status](https://img.shields.io/badge/Audit-Completed%20(2025%2F2026)-success.svg)]()

> **Course Module:** BAXZ 3613 — Hacking Techniques and Prevention  
> **Faculty:** Faculty of Artificial Intelligence and Cyber Security, Universiti Teknikal Malaysia Melaka (UTeM)[cite: 2]  
> **Lead Tester:** Anas Faozi Abdullah Al-Abi [cite: 2]  
> **Team Members:** Maged Saeed Ahmed Blashram, Ibrahim Khaled Abdullah Omar[cite: 2]

---

## 📄 Full Penetration Testing Report
- 📥 **[Download / View Full VAPT Assessment Report (PDF)](./BAXZ3613_Project_Activity%20.pdf)**[cite: 2]

---

## 📌 Executive Summary
This repository documents a comprehensive **Vulnerability Assessment and Penetration Testing (VAPT)** engagement executed across four distinct vulnerable targets[cite: 2]: **Entry Gate Authentication Portal**, **OWASP Juice Shop**, **Damn Vulnerable Web Application (DVWA)**, and **WebGoat**[cite: 2].

A total of **17 security findings** were identified, manually verified, and remediated[cite: 2]. Findings span critical risk categories including **SQL Injection (SQLi)**[cite: 2], **OS Command Injection**[cite: 2], **Local File Inclusion (LFI)**[cite: 2], **Insecure Direct Object References (IDOR)**[cite: 2], **Cross-Site Scripting (Reflected & DOM XSS)**[cite: 2], and **Predictable Session Generation**[cite: 2].

---

## 🛠️ Security Toolset
- **Reconnaissance & Enumeration:** `Nmap`, `Nikto`, `Gobuster`, `Dirsearch`[cite: 2]
- **Web Proxy & Interception:** `Burp Suite Community Edition`, `OWASP ZAP`[cite: 2]
- **Exploitation & Automation:** `sqlmap`, `cURL`[cite: 2]
- **Cryptographic & Decoding Analysis:** `CyberChef`, `CrackStation` (MD5 rainbow table cracking), `Base64 Decoder`[cite: 2]
- **Environment:** `Kali Linux`[cite: 2]

---

## 🔍 Consolidated Findings Summary (17 Verified Vulnerabilities)

| Finding ID | Target Environment | Vulnerability Title | Severity | OWASP Mapping / CWE |
| :--- | :--- | :--- | :---: | :--- |
| **GATE-01** | Entry Gate Portal | Sensitive Credential Exposure via `/static/clue.js`[cite: 2] | **High**[cite: 2] | OWASP A07:2021 / CWE-312[cite: 2] |
| **GATE-02** | Entry Gate Portal | Authentication Bypass via SQL Injection (`' OR '1'='1'--`)[cite: 2] | **High**[cite: 2] | OWASP A03:2021 / CWE-89[cite: 2] |
| **JS-01** | OWASP Juice Shop | Admin Authentication Bypass via SQLi on Email Field[cite: 2] | **High**[cite: 2] | OWASP A03:2021 / CWE-89[cite: 2] |
| **JS-02** | OWASP Juice Shop | Automated SQLi via `sqlmap` (22 Database Tables Dumped)[cite: 2] | **High**[cite: 2] | OWASP A03:2021 / CWE-89[cite: 2] |
| **JS-03** | OWASP Juice Shop | Unsalted MD5 Password Hash Storage (Offline Hash Cracking)[cite: 2] | **High**[cite: 2] | OWASP A02:2021 / CWE-916[cite: 2] |
| **JS-04** | OWASP Juice Shop | Trivial / Weak Password Policy Enforcement[cite: 2] | **High**[cite: 2] | OWASP A07:2021 / CWE-521[cite: 2] |
| **JS-05** | OWASP Juice Shop | Vulnerable `@angular/core` Library (`CVE-2026-54267`)[cite: 2] | **High**[cite: 2] | OWASP A06:2021 / CWE-1395[cite: 2] |
| **DVWA-01** | DVWA | OS Command Injection via Ping Utility (`cat /etc/passwd`)[cite: 2] | **High**[cite: 2] | OWASP A03:2021 / CWE-78[cite: 2] |
| **DVWA-02** | DVWA | Local File Inclusion (LFI) via `page` GET Parameter[cite: 2] | **High**[cite: 2] | OWASP A01:2021 / CWE-22[cite: 2] |
| **DVWA-03** | DVWA | SQL Injection via User ID Field (`99' or 1=1#`)[cite: 2] | **High**[cite: 2] | OWASP A03:2021 / CWE-89[cite: 2] |
| **DVWA-04** | DVWA | DOM-Based Cross-Site Scripting (XSS) via `default` Parameter[cite: 2] | **Medium**[cite: 2] | OWASP A03:2021 / CWE-79[cite: 2] |
| **DVWA-05** | DVWA | Predictable Sequential Session Identifiers (`dvwaSession`)[cite: 2] | **Medium**[cite: 2] | OWASP A07:2021 / CWE-330[cite: 2] |
| **WG-01** | WebGoat | Numeric SQL Injection via `User_Id` / `Login_Count`[cite: 2] | **High**[cite: 2] | OWASP A03:2021 / CWE-89[cite: 2] |
| **WG-02** | WebGoat | Reflected Cross-Site Scripting in Shopping Cart[cite: 2] | **Medium**[cite: 2] | OWASP A03:2021 / CWE-79[cite: 2] |
| **WG-03** | WebGoat | DOM-Based XSS via Client Route (`start.mvc#test/`)[cite: 2] | **Medium**[cite: 2] | OWASP A03:2021 / CWE-79[cite: 2] |
| **WG-04** | WebGoat | Arbitrary File Upload / Path Traversal (`../test`)[cite: 2] | **High**[cite: 2] | OWASP A01:2021 / CWE-22[cite: 2] |
| **WG-05** | WebGoat | Insecure Direct Object Reference (IDOR) on Profile Endpoint[cite: 2] | **High**[cite: 2] | OWASP A01:2021 / CWE-639[cite: 2] |

---

## 🛡️ Remediation Strategies
- **Injection Flaws:** Migrate all dynamic SQL queries to parameterized prepared statements; enforce strict IP allowlist validation on OS execution wrappers[cite: 2].
- **Broken Access Control & IDOR:** Implement robust server-side session-bound authorization checks on every resource request; canonicalize and restrict file upload paths[cite: 2].
- **Cross-Site Scripting (XSS):** Implement context-aware output encoding (HTML, JavaScript, Attribute); deploy strict Content Security Policies (CSP)[cite: 2].
- **Cryptographic & Session Integrity:** Transition legacy MD5 password hashes to modern adaptive algorithms (Argon2id/bcrypt) with unique salts; generate session IDs using cryptographically secure PRNGs[cite: 2].

---

## ⚖️ Rules of Engagement
All testing was executed inside an isolated, authorized local virtual machine lab environment strictly conforming to academic ethics guidelines, with zero testing conducted against unauthorized networks or public systems[cite: 2].
