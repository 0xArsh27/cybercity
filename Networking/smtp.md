# SMTP (Simple Mail Transfer Protocol) – Cybersecurity Focused Notes

## What is SMTP
SMTP (Simple Mail Transfer Protocol) is an application-layer protocol used to send emails from a client to a mail server and between mail servers. SMTP is responsible only for **sending** emails, not receiving them.

Default ports:
- TCP 25  → SMTP (server-to-server)
- TCP 587 → SMTP with STARTTLS (submission)
- TCP 465 → SMTPS (SMTP over SSL/TLS)

---

## Why SMTP is Critical in Cybersecurity
SMTP is heavily abused for:
- Phishing attacks
- Email spoofing
- Malware delivery
- Spam campaigns
- Data exfiltration

Most real-world cyber attacks **start with email**.

---

## How SMTP Works (Basic Flow)
1. Client connects to SMTP server
2. Server responds with banner
3. Client introduces itself (HELO/EHLO)
4. Sender and recipient are specified
5. Email content is transmitted
6. Server queues and forwards the email

SMTP trusts headers by default, which creates security risks.

---

## SMTP Commands (Security Relevant)

```text
HELO / EHLO   → Identify client
MAIL FROM    → Specify sender
RCPT TO      → Specify recipient
DATA         → Send email content
RSET         → Reset session
VRFY         → Verify user (often disabled)
EXPN         → Expand mailing list
QUIT         → Close connection
