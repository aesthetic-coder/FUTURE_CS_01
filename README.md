# Vulnerability Assessment Report: Altoro Mutual Bank
Target Website: http://demo.testfire.net <br>
Date: January 2026

## Project Overview
Every modern business relies on its website, but many still remain vulnerable to very common cyber threats. This project involves a security audit of the Altoro Mutual banking portal. The goal was to identify security weaknesses from an auditor's perspective, focusing on risk and practical remediation rather than exploitation.

## Tools Used
For this assessment, the following analysis tools were used:<br>
1. SecurityHeaders.com: Used for analysis of HTTP response headers and security posture grading.<br>
2. Browser DevTools: Used for manual inspection of the technology stack and server fingerprinting.<br>
3. OWASP ZAP: Used to identify common vulnerabilities without disrupting site services.<br>
4. ViewDNS.info: Used for remote port scanning.<br>

## Scope & Methodology
This audit followed strict ethical guidelines:<br>
Passive Only: There were no active attacks, brute-forcing, or Denial-of-Service (DoS) performed.<br>
Read-Only: No data was modified or deleted during the process.<br>

##  Findings & Risk Classification<br>
ISSUE: Missing SSL/TLS<br>
RISK LEVEL: High<br>
DESCRIPTION: The website uses the insecure HTTP protocol. All data (passwords, account details) is transmitted in cleartext, making it visible to anyone on the same network.<br>
<br>
ISSUE: Verbose Error Messages<br>
RISK LEVEL: Medium<br>
DESCRIPTION: The system displays raw database syntax errors to the user. This reveals the internal structure of the database and helps attackers craft more precise attacks.<br>
<br>
ISSUE: Server Information Disclosure<br>
RISK LEVEL: Medium<br>
DESCRIPTION: HTTP response headers reveal specific software versions (e.g., Apache-Coyote). This allows attackers to search for specific exploits related to that version.<br>
<br>
ISSUE: Missing Content Security Policy (CSP)<br>
RISK LEVEL: Low/Medium<br>
DESCRIPTION: The site lacks a CSP header, which increases the risk of Clickjacking and Cross-Site Scripting (XSS) attacks by allowing unauthorized scripts to run.<br>

