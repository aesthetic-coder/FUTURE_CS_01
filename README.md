# Vulnerability Assessment Report: Altoro Mutual Bank
Target Website: http://demo.testfire.net
Date: January 2026

## Project Overview
Every modern business relies on its website, but many still remain vulnerable to very common cyber threats. This project involves a security audit of the Altoro Mutual banking portal. The goal was to identify security weaknesses from an auditor's perspective, focusing on risk and practical remediation rather than exploitation.

## Tools Used
For this assessment, the following analysis tools were used:
1. SecurityHeaders.com: Used for analysis of HTTP response headers and security posture grading.
2. Browser DevTools: Used for manual inspection of the technology stack and server fingerprinting.
3. OWASP ZAP: Used to identify common vulnerabilities without disrupting site services.
4. ViewDNS.info: Used for remote port scanning.

## Scope & Methodology
This audit followed strict ethical guidelines:
Passive Only: There were no active attacks, brute-forcing, or Denial-of-Service (DoS) performed.
Read-Only: No data was modified or deleted during the process.

##  Findings & Risk Classification
|        Issue          |  Risk Level |                              Description                          |
-----------------------------------------------------------------------------------------------------------
| **Missing SSL/TLS**   | **High**    | Site uses HTTP, meaning data is sent in cleartext.                |
| **Verbose Errors**    | **Medium**  | Database syntax errors are leaked to the public.                  |
| **Server Disclosure** | **Medium**  | Server headers reveal specific software versions (Apache-Coyote). |
| **Missing CSP**       | **Low/Med** | Lack of Content Security Policy increases Clickjacking risk.      |
