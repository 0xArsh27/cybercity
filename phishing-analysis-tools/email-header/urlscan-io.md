# URLScan.io (URL and Website Analysis Tool)

## Overview

URLScan.io is a dynamic URL and website analysis tool employed by security analysts to safely inspect suspicious links without direct access. It captures website behavior, loaded resources, and communication patterns.

## Application in Phishing Analysis

URLScan.io is utilized to:
- Safely analyze suspicious or shortened URLs
- Identify phishing pages and fake login portals
- Capture webpage screenshots
- Extract network requests, redirects, and scripts
- Prevent direct exposure to malicious sites

## Information Provided by URLScan.io

### 1. Page Screenshot
A visual capture of the webpage, aiding in the identification of brand impersonation.

Potential Indicators of Phishing:
- Fake login pages mimicking legitimate services such as Microsoft, Google, or banks

### 2. Final Resolved URL
Displays the actual destination following any redirects.

Potential Indicators of Phishing:
- Multiple redirects
- Final domain unrelated to the claimed brand

### 3. Domain & IP Information
Includes hosting IP, ASN, ISP, and geolocation.

Potential Indicators of Phishing:
- Hosting via VPS or suspicious providers

### 4. Network Requests
Lists all external resources loaded, such as JavaScript, CSS, images, and APIs.

Potential Indicators of Phishing:
- Requests to suspicious or unknown domains

### 5. Redirect Chain
Details each redirection step.

Potential Indicators of Phishing:
- Chains involving URL shorteners leading to random domains and phishing pages

### 6. Technologies Used
Identifies frameworks, libraries, and content management systems.

Potential Indicators of Phishing:
- Use of newly created or uncommon technology stacks for purportedly official sites

## Workflow for Analysts

1. Extract the URL from the email body or attachment.
2. Submit the URL to URLScan.io.
3. Review:
   - Screenshot
   - Final URL
   - Redirects
   - Network activity
4. Compare branding with legitimate sources.
5. Correlate findings with email header analysis.

## Indicators of Phishing

- Brand impersonation
- Credential-harvesting pages
- Malicious redirects
- Suspicious third-party scripts
- Newly registered domains

## Conclusion

URLScan.io enables analysts to visually and technically validate whether a URL is legitimate, part of a phishing campaign, or associated with broader malicious activity.

## Note

Avoid visiting suspicious URLs directly. Always utilize URLScan.io or a sandboxed environment for initial analysis.
