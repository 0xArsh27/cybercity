# Message Header Analysis

## Overview

Email message headers contain technical routing information that reveals the origin, path, and authenticity of an email. Analyzing these headers is a fundamental step in phishing investigations, enabling the detection of spoofed senders, verification of email authentication, and identification of malicious infrastructure.

## Importance of Message Header Analysis

Message header analysis is crucial for:
- Detecting spoofed email addresses
- Identifying the true originating IP address
- Verifying email authentication mechanisms
- Attributing emails to malicious actors
- Providing indicators for blocking and threat hunting

## Key Fields in Email Headers

### 1. From
This field displays the claimed sender email address. It is easily spoofed and must be cross-referenced with authentication results.

Potential Indicators of Phishing:
- Use of look-alike domains (e.g., `micros0ft.com`)

### 2. To / CC / BCC
These fields indicate the recipients of the email. The presence of BCC may suggest mass phishing campaigns.

Potential Indicators of Phishing:
- Multiple unrelated recipients
- Hidden recipients via BCC

### 3. Subject
The subject line often contains social engineering elements designed to elicit urgency or fear.

Common Phishing Subject Lines:
- Urgent action required
- Invoice attached
- Account suspended
- Payment update

### 4. Reply-To
This field specifies the address where replies are directed and may differ from the From address.

Potential Indicators of Phishing:
- Mismatch between From and Reply-To addresses

Example:
- From: `support@company.com`
- Reply-To: `support.help@gmail.com`

### 5. Received Headers
These headers trace the email's path through mail servers, listed in reverse chronological order. The first Received entry represents the originating mail server.

Analyst Actions:
- Extract the sender IP address
- Identify suspicious mail servers

### 6. Sender IP Address
This is the IP address of the server that transmitted the email, useful for reputation checks and geolocation analysis.

Potential Indicators of Phishing:
- IP addresses associated with unknown hosting providers
- IPs not linked to the claimed organization

### 7. Reverse DNS Lookup
This resolves the sender IP to a hostname or organization.

Potential Indicators of Phishing:
- Absence of reverse DNS records
- Association with random or generic VPS providers

### 8. SPF (Sender Policy Framework)
SPF verifies whether the sending server is authorized by the domain owner. Results include Pass, Fail, or SoftFail.

Potential Indicators of Phishing:
- SPF Fail

### 9. DKIM (DomainKeys Identified Mail)
DKIM ensures message integrity and domain authenticity through cryptographic signatures.

Potential Indicators of Phishing:
- DKIM Fail or absence

### 10. DMARC
DMARC combines SPF and DKIM results and specifies handling for authentication failures.

Potential Indicators of Phishing:
- DMARC Fail

## Common Phishing Indicators in Headers
- Authentication failures (SPF, DKIM, DMARC)
- Mismatches between sender domains and IPs
- Suspicious sender IP addresses
- Divergent Reply-To addresses
- Routing through unknown or compromised servers

## Conclusion
Message header analysis reveals the true origin of an email and is essential for identifying spoofing, phishing, and malicious campaigns. It serves as a foundation for further examination of the email body, links, and attachments.
