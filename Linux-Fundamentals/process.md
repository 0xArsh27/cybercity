# Linux Process Management 🧠⚙️

Comprehensive reference of Linux process-related commands used for system monitoring, troubleshooting, malware analysis, incident response, and privilege escalation scenarios in cybersecurity. This guide includes practical examples and advanced tips for effective process management.

---

## 🧩 Process Basics

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `ps` | Display current shell processes | `ps` |
| `ps aux` | List all running processes with detailed information | `ps aux` |
| `ps -ef` | Show all processes in full-format listing | `ps -ef` |
| `pidof process` | Get PID of a running process | `pidof sshd` |
| `pgrep process` | Search process by name | `pgrep apache2` |
| `watch ps aux` | Continuously monitor processes | `watch ps aux` |

---

## 📊 Real-Time Process Monitoring

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `top` | Real-time process monitoring | `top` |
| `htop` | Enhanced interactive process viewer | `htop` |
| `atop` | Advanced performance monitor | `atop` |
| `htop -u user` | Show processes of a specific user | `htop -u root` |

---

## 🆔 Process Identification

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `pidof sshd` | Show PID of sshd process | `pidof sshd` |
| `echo $$` | Show PID of current shell | `echo $$` |
| `pstree` | Display process hierarchy | `pstree` |
| `pstree -p` | Show process tree with PIDs | `pstree -p` |

---

## 🛑 Process Control & Termination

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `kill PID` | Terminate a process | `kill 1234` |
| `kill -9 PID` | Force kill a process | `kill -9 1234` |
| `pkill process` | Kill process by name | `pkill apache2` |
| `killall process` | Kill all instances of a process | `killall firefox` |

---

## 🎛️ Process Priority (Nice Values)

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `nice -n 10 command` | Start process with priority | `nice -n 10 ./script.sh` |
| `renice -5 PID` | Change priority of running process | `renice -5 1234` |
| `top` | View NI (nice) values | `top` |

---

## 🔄 Background & Foreground Jobs

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `command &` | Run process in background | `sleep 100 &` |
| `jobs` | List background jobs | `jobs` |
| `fg %1` | Bring job to foreground | `fg %1` |
| `bg %1` | Resume job in background | `bg %1` |
| `Ctrl + Z` | Suspend current process | Press `Ctrl + Z` during execution |

---

## 🧪 Process Files & Inspection

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `lsof` | List open files by processes | `lsof` |
| `lsof -i` | Show network connections | `lsof -i` |
| `strace command` | Trace system calls | `strace ls` |
| `cat /proc/PID/status` | Process status details | `cat /proc/1234/status` |
| `cat /proc/PID/cmdline` | Command used to start process | `cat /proc/1234/cmdline` |

---

## ⏱️ Scheduling & Automation

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `crontab -l` | List cron jobs | `crontab -l` |
| `crontab -e` | Edit cron jobs | `crontab -e` |
| `at time` | Schedule one-time job | `at 10:00` |
| `systemctl list-timers` | Show system timers | `systemctl list-timers` |

---

## ⚙️ Services & Daemons

| **Command** | **Description** | **Example** |
|------------|-----------------|-------------|
| `systemctl status service` | Check service status | `systemctl status apache2` |
| `systemctl start service` | Start a service | `systemctl start apache2` |
| `systemctl stop service` | Stop a service | `systemctl stop apache2` |
| `systemctl restart service` | Restart service | `systemctl restart apache2` |
| `systemctl enable service` | Enable service at boot | `systemctl enable apache2` |
| `systemctl list-units --type=service` | List running services | `systemctl list-units --type=service` |

---

## 🔐 Cybersecurity Relevance

- **Malware Persistence**: Malicious processes often run as background services, hiding in plain sight.
- **Privilege Escalation**: Misconfigured cron jobs and services can be exploited to gain higher privileges.
- **DFIR**: Process timelines reveal attacker activity, aiding in forensic investigations.
- **Lateral Movement**: Suspicious network-bound processes may indicate unauthorized access.
- **Persistence Mechanisms**: Attackers often use systemd, cron, or startup scripts to maintain access.

---

## 📌 Common Suspicious Indicators

- **Unknown Process Names**: Processes with unfamiliar or random names.
- **Processes Running as Root**: Unusual processes running with elevated privileges.
- **High CPU Usage**: Processes consuming excessive CPU without a clear purpose.
- **Unexpected Network Connections**: Processes establishing connections to suspicious IPs.
- **Hidden Processes**: Processes without corresponding binaries on disk.

---
