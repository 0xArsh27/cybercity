# HTTP (Hypertext Transfer Protocol) – Cybersecurity Focused Notes

## Overview of HTTP
HTTP (Hypertext Transfer Protocol) is a foundational application-layer protocol enabling communication between clients (e.g., browsers) and servers. It operates on a stateless request–response model and is the backbone of web communication.

Default ports:
- **TCP 80** → HTTP (unencrypted)
- **TCP 443** → HTTPS (HTTP over TLS/SSL)

---

## Importance of HTTP in Cybersecurity
HTTP is a critical attack vector due to its ubiquity in web applications and APIs. Key reasons include:
- Exposure of business logic and sensitive data
- Processing of user input
- Authentication mechanisms
- API communication

Compromising HTTP often results in full application compromise, making its security paramount.

---

## HTTP Request–Response Model

### HTTP Request
Key components:
- **Method** (e.g., GET, POST)
- **URL/Path**
- **Headers**
- **Body** (optional)

### HTTP Response
Key components:
- **Status Code**
- **Headers**
- **Body** (content)

Understanding raw HTTP traffic is essential for identifying vulnerabilities and defending against attacks.

---

## HTTP Methods and Their Security Implications

- **GET** → Retrieves data; risks include sensitive data exposure in URLs.
- **POST** → Sends data; risks include injection attacks.
- **PUT** → Updates data; risks include unauthorized modifications.
- **DELETE** → Removes data; risks include data loss.
- **HEAD** → Retrieves headers only; useful for reconnaissance.
- **OPTIONS** → Reveals allowed methods; aids attackers in identifying misconfigurations.

Improperly configured methods can lead to significant vulnerabilities.

---

## HTTP Status Codes and Their Relevance

- **200** → OK (successful request)
- **301/302** → Redirect (can be abused for phishing)
- **401** → Unauthorized (indicates authentication required)
- **403** → Forbidden (access denied)
- **404** → Not Found (useful for enumeration)
- **500** → Server Error (may leak sensitive information)

Status codes provide valuable insights during reconnaissance and exploitation.

---

## HTTP Headers: Security Considerations

### Request Headers
- **Host** → Specifies the target domain.
- **User-Agent** → Identifies the client.
- **Cookie** → Stores session data.
- **Authorization** → Contains credentials or tokens.
- **Referer** → Indicates the source of the request.
- **Origin** → Used in CORS policies.

### Response Headers
- **Server** → Reveals server details (e.g., version).
- **Set-Cookie** → Manages session cookies.
- **Content-Type** → Specifies data format.
- **X-Frame-Options** → Mitigates clickjacking.
- **Content-Security-Policy** → Prevents XSS and data injection.

Misconfigured headers are a common source of vulnerabilities.

---

## HTTP Cookies and Session Security
- **Cookies** store session identifiers and maintain state in a stateless protocol.
- **Session Risks:**
  - Session hijacking
  - Insecure cookie flags (e.g., missing HttpOnly, Secure)
  - Predictable session IDs

Mitigation involves secure cookie attributes and session management practices.

---

## HTTP vs HTTPS: Security Implications

### HTTP
- Plaintext communication
- Vulnerable to eavesdropping and MITM attacks

### HTTPS
- Encrypted via TLS/SSL
- Ensures data integrity and confidentiality

**Note:** HTTPS does not mitigate application-layer vulnerabilities.

---

## Common HTTP Attacks

### SQL Injection
- Exploits user input to manipulate database queries.
- Results in data exfiltration or modification.

---

### Cross-Site Scripting (XSS)
- Injects malicious JavaScript into web pages.
- Executes in the victim’s browser, stealing data or performing actions.

---

### Cross-Site Request Forgery (CSRF)
- Tricks authenticated users into performing unintended actions.
- Exploits trust in the user’s browser.

---

### Insecure Direct Object Reference (IDOR)
- Bypasses authorization to access unauthorized resources.

---

### File Inclusion (LFI/RFI)
- Includes unintended files, leading to code execution.

---

## HTTP in Reconnaissance
Attackers analyze:
- **URLs** → Identify endpoints and parameters.
- **Parameters** → Test for injection points.
- **Headers** → Detect misconfigurations.
- **Cookies** → Analyze session management.
- **JavaScript Files** → Extract sensitive information.

### Common Tools
```bash
curl
burpsuite
wget
```

---

## Key Cybersecurity Takeaway
HTTP is a critical protocol for web communication and a primary target for attackers. Securing HTTP involves understanding its mechanisms, identifying misconfigurations, and mitigating common attack vectors.
