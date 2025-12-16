# Linux Cron & Scheduled Tasks ⏱️

Comprehensive reference for **cron** in Linux, used to schedule recurring tasks.  
Highly relevant for **system administration, SOC monitoring, persistence mechanisms, and DFIR investigations**.

---

## 🧠 Cron Basics

| Component | Description |
|---------|-------------|
| `cron` | Background daemon that executes scheduled tasks |
| `crontab` | File that stores cron jobs for a user |
| `crond` | Cron service process |

---

## 📄 Crontab File Locations

| Path | Purpose |
|----|--------|
| `/etc/crontab` | System-wide cron jobs |
| `/etc/cron.hourly/` | Jobs run hourly |
| `/etc/cron.daily/` | Jobs run daily |
| `/etc/cron.weekly/` | Jobs run weekly |
| `/etc/cron.monthly/` | Jobs run monthly |
| `/var/spool/cron/` | User-specific crontabs |

---

## 🛠️ Crontab Commands

| Command | Description |
|-------|------------|
| `crontab -l` | List current user’s cron jobs |
| `crontab -e` | Edit current user’s cron jobs |
| `crontab -r` | Remove all cron jobs for user |
| `crontab -u user -l` | List another user’s cron jobs (requires root privileges) |
| `crontab -u user -e` | Edit another user’s cron jobs (requires root privileges) |

---

## ⏰ Cron Job Syntax

Cron jobs follow a specific syntax to define the schedule and the command to execute. The format consists of five fields followed by the command:

```
* * * * * command_to_execute
- - - - -
| | | | |
| | | | +---- Day of the week (0 - 7) [Both 0 and 7 represent Sunday]
| | | +------ Month (1 - 12)
| | +-------- Day of the month (1 - 31)
| +---------- Hour (0 - 23)
+------------ Minute (0 - 59)
```

### Examples:

| **Cron Job** | **Description** |
|--------------|-----------------|
| `0 5 * * * /path/to/script.sh` | Run script daily at 5:00 AM |
| `*/15 * * * * /path/to/script.sh` | Run script every 15 minutes |
| `0 0 1 * * /path/to/script.sh` | Run script at midnight on the 1st of every month |
| `0 8-18/2 * * * /path/to/script.sh` | Run script every 2 hours between 8:00 AM and 6:00 PM |
| `0 0 * * 0 /path/to/script.sh` | Run script every Sunday at midnight |

---

## 🔐 Cybersecurity Relevance

- **Persistence Mechanisms**: Attackers may use cron jobs to maintain access to compromised systems.
- **DFIR Investigations**: Analyzing cron jobs can reveal malicious scripts or unauthorized tasks.
- **Privilege Escalation**: Misconfigured cron jobs with improper permissions can be exploited to gain elevated privileges.
- **Indicators of Compromise (IoCs)**: Suspicious cron jobs or scripts in `/etc/cron.*` directories may indicate malicious activity.

---

## 📌 Tips for Secure Cron Usage

1. **Restrict Access**: Use `/etc/cron.allow` and `/etc/cron.deny` to control user access to cron.
2. **Audit Cron Jobs**: Regularly review cron jobs for unauthorized or suspicious entries.
3. **Use Absolute Paths**: Always specify absolute paths for commands and scripts in cron jobs.
4. **Log Outputs**: Redirect cron job outputs to log files for monitoring and debugging.
   - Example: `0 5 * * * /path/to/script.sh >> /var/log/script.log 2>&1`
5. **Monitor Changes**: Use file integrity monitoring tools to detect changes in cron files.

---

