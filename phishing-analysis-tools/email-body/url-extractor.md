# Email Body Analysis – URL Extractor

## Overview

A URL Extractor is a tool employed during email body analysis to automatically identify and extract all URLs present in an email's content. These may include visible links, hidden links behind buttons or text, embedded HTML code, or obfuscated/encoded URLs.

## Application in Phishing Analysis

URL Extractors are utilized to:
- Quickly identify all links in suspicious emails
- Reveal hidden or misleading URLs
- Prevent accidental clicks by analysts
- Support further analysis with URL intelligence tools

## Types of URLs Extracted

- Plain-text URLs
- Hyperlinks embedded in anchor tags (`<a href="">`)
- Shortened URLs
- Obfuscated or encoded URLs

Potential Indicators of Phishing:
- Display text that does not match the actual link destination

## Common URL Extractor Tools

### 1. CyberChef
Extracts URLs from raw text or HTML, decodes obfuscated links, and supports bulk extraction.

### 2. URLScan.io (Pre-step)
Displays all URLs loaded by a webpage, aiding in the identification of hidden redirects and resources.

### 3. Online URL Extractors
Simple tools for listing URLs from email content, suitable for quick triage.

### 4. Manual Inspection
Involves viewing the email source and inspecting HTML anchor tags.

## Workflow for Analysts

1. Copy the email body (text or HTML).
2. Run it through a URL Extractor.
3. Collect all extracted URLs.
4. Identify:
   - Shortened URLs
   - Obfuscated links
   - Mismatched display versus destination URLs
5. Submit extracted URLs to:
   - URLScan.io
   - VirusTotal
   - Cisco Talos

## Indicators of Phishing

- Shortened or obfuscated URLs
- Multiple redirects
- Domains unrelated to the sender brand
- IP-based URLs
- Newly registered domains

## Conclusion

URL Extractors enable analysts to safely and accurately collect all URLs from an email prior to deeper investigation, serving as a critical initial step in email body analysis.

## Note

Always extract URLs before clicking anything. Avoid direct interaction with suspicious email links.
