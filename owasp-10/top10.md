# OWASP Top 10 – Web Application Security Risks

The **OWASP Top 10** is a standard awareness document for developers, testers, and security professionals that represents the **most critical web application security risks**. This document provides detailed descriptions of each risk category, common vulnerabilities, potential impacts, and mitigation strategies.

---

## A01: Broken Access Control
**Description:**  
Access control is not properly enforced, allowing users to access data or perform actions beyond their intended permissions.

**Common Issues:**
- IDOR (Insecure Direct Object Reference)
- Horizontal privilege escalation
- Vertical privilege escalation
- Missing authorization checks

**Impact:**  
Data breaches, unauthorized actions, account compromise

**Mitigation:**
- Implement proper access control mechanisms
- Use role-based access control (RBAC)
- Enforce authorization checks on every request
- Regularly review and test access controls

---

## A02: Cryptographic Failures
**Description:**  
Sensitive data is not properly protected due to weak or missing encryption.

**Common Issues:**
- Plaintext storage of passwords
- Weak encryption algorithms
- Missing HTTPS
- Improper key management

**Impact:**  
Data exposure, identity theft

**Mitigation:**
- Use strong, up-to-date encryption algorithms
- Implement HTTPS everywhere
- Properly manage cryptographic keys
- Avoid storing sensitive data unnecessarily

---

## A03: Injection
**Description:**  
Untrusted data is sent to an interpreter as part of a command or query.

**Common Issues:**
- SQL Injection
- NoSQL Injection
- OS Command Injection
- LDAP Injection

**Impact:**  
Data loss, remote code execution

**Mitigation:**
- Use parameterized queries or prepared statements
- Implement input validation and sanitization
- Employ web application firewalls (WAF)
- Escape special characters in user inputs

---

## A04: Insecure Design
**Description:**  
Security flaws caused by missing or weak security controls at the design level.

**Common Issues:**
- No threat modeling
- Missing rate limiting
- Poor business logic design

**Impact:**  
Systemic vulnerabilities difficult to fix later

**Mitigation:**
- Conduct threat modeling during design phase
- Implement secure design patterns
- Include security requirements in specifications
- Perform security reviews early in development

---

## A05: Security Misconfiguration
**Description:**  
Incorrect or insecure configuration of applications, servers, or frameworks.

**Common Issues:**
- Default credentials
- Exposed admin panels
- Debug mode enabled
- Unnecessary services running

**Impact:**  
Unauthorized access, system compromise

**Mitigation:**
- Implement secure configuration baselines
- Regularly audit configurations
- Disable unnecessary features and services
- Use automated configuration management tools

---

## A06: Vulnerable and Outdated Components
**Description:**  
Using components with known vulnerabilities.

**Common Issues:**
- Outdated libraries
- Unsupported software versions
- No patch management

**Impact:**  
Known exploits leading to compromise

**Mitigation:**
- Regularly update and patch components
- Use dependency scanning tools
- Monitor vulnerability databases
- Implement a software bill of materials (SBOM)

---

## A07: Identification and Authentication Failures
**Description:**  
Failures related to user identity verification and session management.

**Common Issues:**
- Weak password policies
- Broken authentication logic
- Session fixation
- No MFA

**Impact:**  
Account Takeover (ATO)

**Mitigation:**
- Implement multi-factor authentication (MFA)
- Enforce strong password policies
- Use secure session management
- Regularly test authentication mechanisms

---

## A08: Software and Data Integrity Failures
**Description:**  
Failures related to code and infrastructure integrity.

**Common Issues:**
- Insecure CI/CD pipelines
- Unsigned updates
- Deserialization vulnerabilities

**Impact:**  
Supply chain attacks, malicious code execution

**Mitigation:**
- Secure CI/CD pipelines
- Verify integrity of updates and dependencies
- Implement code signing
- Use secure deserialization practices

---

## A09: Security Logging and Monitoring Failures
**Description:**  
Insufficient logging and monitoring, allowing attacks to go undetected.

**Common Issues:**
- No alerting on suspicious activity
- Logs not reviewed
- Missing audit trails

**Impact:**  
Delayed incident response, long-term persistence

**Mitigation:**
- Implement comprehensive logging
- Set up real-time monitoring and alerting
- Regularly review logs
- Integrate with security information and event management (SIEM) systems

---

## A10: Server-Side Request Forgery (SSRF)
**Description:**  
The server is tricked into making unauthorized requests.

**Common Issues:**
- Access to internal services
- Cloud metadata exposure
- Lack of URL validation

**Impact:**  
Internal network compromise, data leakage

**Mitigation:**
- Validate and sanitize user-supplied URLs
- Implement network segmentation
- Use allowlists for permitted destinations
- Disable unnecessary protocols

---

## Key Considerations

- **High Priority for Bug Bounty Programs:** A01 (Broken Access Control), A03 (Injection), A07 (Identification and Authentication Failures), A10 (Server-Side Request Forgery)
- **Critical for Security Operations Centers (SOC) and Blue Teams:** A09 (Security Logging and Monitoring Failures), A06 (Vulnerable and Outdated Components), A05 (Security Misconfiguration)
- **Business Logic Vulnerabilities:** Often categorized under A01 (Broken Access Control) or A04 (Insecure Design)

## References

- [OWASP Top 10 Official Website](https://owasp.org/www-project-top-ten/)
- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
