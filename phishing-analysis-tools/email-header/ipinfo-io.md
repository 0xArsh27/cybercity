# IPinfo.io (IP Intelligence Tool)

## Overview

IPinfo.io is an IP intelligence and geolocation tool utilized by security analysts to gather contextual information about IP addresses encountered in email headers, URLs, logs, and network traffic. It aids in determining whether an IP address is legitimate or suspicious.

## Application in Phishing Analysis

IPinfo.io is employed to:
- Identify the geographical location of the sender IP
- Determine the associated organization, ISP, or hosting provider
- Detect cloud-hosted or VPS-based attacker infrastructure
- Support attribution and risk assessment

## Information Provided by IPinfo.io

### 1. IP Address
The queried public IP address serves as the primary indicator.

### 2. Geolocation
Includes country, region, city, and time zone.

Potential Indicators of Suspicious Activity:
- Location inconsistent with the claimed sender organization

### 3. Organization / ASN
Displays the network owner, including the Autonomous System Number (ASN).

Potential Indicators of Suspicious Activity:
- Association with VPS providers, cloud hosting, or unknown ISPs

### 4. ISP / Hosting Provider
Identifies whether the IP is residential, corporate, or hosted.

Potential Indicators of Suspicious Activity:
- Emails purporting to originate from established organizations (e.g., Microsoft, banks) but traced to inexpensive hosting providers

### 5. Privacy Indicators
Includes flags for VPN, proxy, Tor, or hosting usage.

Potential Indicators of Suspicious Activity:
- Use of VPN or proxy for communications claiming to be from business entities

## Workflow for Analysts

1. Extract the sender IP from the email header (Received field).
2. Query the IP using IPinfo.io.
3. Validate:
   - Consistency of country with sender claims
   - Legitimacy of the organization
   - Appropriateness of hosting versus corporate infrastructure
4. Correlate findings with SPF, DKIM, and DMARC results.

## Example Conclusion
If an email claims to originate from a trusted organization but the sender IP resolves to a cloud VPS, is located in an unexpected country, or utilizes VPN/proxy infrastructure, it is likely indicative of phishing or malicious activity.

## Note
IPinfo.io provides contextual information rather than definitive verdicts. Analysts should always correlate IP intelligence with header authentication results, URL analysis, and email body indicators.
