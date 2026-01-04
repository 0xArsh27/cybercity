# Mail Header Analysis

## Overview

Mail header analysis involves examining raw email headers through manual inspection and automated tools to detect spoofing, identify sender infrastructure, verify authentication, and uncover routing anomalies. This process reveals the true origin of suspicious emails.

## Obtaining Mail Headers

Headers can be accessed via:
- Email client options:
  - Gmail: Show Original
  - Outlook: View Message Headers
- Security platforms:
  - SIEM systems
  - Email Security Gateways
  - SOAR platforms

## Common Mail Header Analysis Tools

### 1. Google Admin Toolbox – Messageheader
This tool parses raw headers into a readable format, highlights SPF, DKIM, and DMARC results, and displays sender IP and mail routing paths. It is particularly useful for quick validation of spoofed emails.

### 2. MXToolbox – Email Header Analyzer
This analyzer performs header parsing and reputation checks, identifies blacklisted IPs and domains, and clearly displays authentication results. It supports reputation and DNS-based evaluations.

### 3. Microsoft Message Header Analyzer
Designed for Outlook and Exchange environments, this tool shows hop-by-hop mail delivery and identifies Exchange-specific anomalies. It is ideal for enterprise Microsoft setups.

### 4. Manual Header Inspection
Analysts manually review fields such as Received, authentication headers, and sender details. This method is employed for advanced investigations and validating false positives.

## Key Header Fields

### Received
This field traces the mail server path, read from bottom to top. The first entry indicates the originating server.

Potential Indicators of Phishing:
- Routing through unknown or suspicious mail servers

### From
This displays the claimed sender address, which is easily spoofed.

Potential Indicators of Phishing:
- Use of look-alike or misspelled domains

### Reply-To
This specifies the address for replies.

Potential Indicators of Phishing:
- Mismatch with the From address

### SPF
This verifies sender authorization.

Potential Indicators of Phishing:
- SPF Fail or SoftFail

### DKIM
This ensures message integrity.

Potential Indicators of Phishing:
- DKIM Fail or absence

### DMARC
This enforces SPF and DKIM policies.

Potential Indicators of Phishing:
- DMARC Fail

## Indicators of Phishing in Mail Headers
- Authentication failures (SPF, DKIM, DMARC)
- Sender IP not associated with the domain owner
- Multiple suspicious Received entries
- Divergent From and Reply-To addresses
- Transmission via unknown hosting providers

## Conclusion
Mail header analysis determines whether an email is legitimate, spoofed, or part of a phishing or malware campaign. It is conducted prior to analyzing URLs or attachments.
