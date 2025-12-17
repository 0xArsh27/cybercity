# DNS (Domain Name System) – Cybersecurity Focused Notes

## What is DNS
DNS (Domain Name System) translates human-readable domain names into IP addresses. Without DNS, users would need to remember IP addresses to access websites and services.

DNS operates at:
- Application Layer
- Uses UDP 53 by default
- Uses TCP 53 for zone transfers and large responses

---

## Why DNS is Critical in Cybersecurity
DNS controls:
- Where traffic is sent
- Which servers users reach
- How malware communicates

If DNS is compromised, attackers can:
- Redirect users to malicious sites
- Steal credentials
- Control infected systems
- Exfiltrate data silently

---

## DNS Resolution Process
1. User enters a domain name
2. Browser checks local DNS cache
3. Query sent to recursive DNS resolver
4. Resolver queries root servers
5. Root points to TLD servers (.com, .org)
6. TLD points to authoritative DNS server
7. Authoritative server returns IP
8. IP is cached and used for connection

This process is trust-based and targetable.

---

## DNS Record Types (Security Relevant)

- A → Domain to IPv4 address
- AAAA → Domain to IPv6 address
- CNAME → Alias to another domain
- MX → Mail server
- NS → Authoritative name servers
- TXT → Text records (SPF, DKIM, verification)
- PTR → Reverse DNS lookup

TXT records are frequently abused.

---

## DNS Caching
DNS responses are cached to improve speed.

Security risk:
- Cache poisoning persists malicious IPs
- Long TTL increases attack impact

---

## DNS Attacks (VERY IMPORTANT)

### DNS Spoofing / Poisoning
- Fake DNS responses sent to victim
- Redirects traffic to malicious IP
- Enables phishing and malware delivery

---

### DNS Cache Poisoning
- Corrupts resolver cache
- Affects multiple users
- Difficult to detect

---

### DNS Tunneling
- Encodes data inside DNS queries
- Bypasses firewalls
- Used for C2 and data exfiltration

Common in advanced malware.

---

### DNS Amplification (DDoS)
- Small query → large response
- Spoofed source IP
- Overwhelms victim

---

### Subdomain Enumeration
- Discover hidden services
- Expand attack surface

Used heavily in reconnaissance.

---

## DNS in Reconnaissance
Attackers use DNS to:
- Identify infrastructure
- Map subdomains
- Discover mail servers
- Find exposed services

Example tools:
```bash
dig
nslookup
dnsrecon
