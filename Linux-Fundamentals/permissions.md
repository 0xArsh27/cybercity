# Linux Permissions Commands 🔐

All essential Linux permission-related commands used in cybersecurity, SOC analysis, privilege escalation, and system hardening — consolidated in a single reference. This guide includes practical examples, advanced tips, and cybersecurity relevance for effective permission management.

---

## 📄 Viewing Permissions

| Command | Description | Example |
|--------|-------------|---------|
| `ls -l` | Display file permissions, owner, group | `ls -l /etc/passwd` |
| `ls -ld dir` | View permissions of a directory itself | `ls -ld /var/log` |
| `stat file` | Show detailed permission and metadata info | `stat /etc/shadow` |
| `getfacl file` | View ACL permissions | `getfacl /tmp/testfile` |

---

## 🔑 Permission Representation

| Mode | Meaning |
|-----|--------|
| `r` | Read |
| `w` | Write |
| `x` | Execute |
| `-` | No permission |

### Permission Breakdown:
- **Owner**: `rwx` (Permissions for the file owner)
- **Group**: `r-x` (Permissions for the group members)
- **Others**: `r--` (Permissions for everyone else)

---

## 🛠️ chmod (Change Permissions)

### Numeric Mode
| Command | Purpose | Example |
|-------|--------|---------|
| `chmod 777 file` | Full permissions to everyone | `chmod 777 script.sh` |
| `chmod 755 file` | Common executable permission | `chmod 755 /usr/local/bin/tool` |
| `chmod 644 file` | Common file permission | `chmod 644 /etc/hosts` |
| `chmod -R 755 dir` | Recursively change permissions | `chmod -R 755 /var/www` |

Numeric Meaning:
| Value | Permission |
|-----|-----------|
| 4 | Read |
| 2 | Write |
| 1 | Execute |

### Symbolic Mode
| Command | Purpose | Example |
|--------|--------|---------|
| `chmod u+x file` | Add execute to user | `chmod u+x script.sh` |
| `chmod g-w file` | Remove write from group | `chmod g-w config.cfg` |
| `chmod o+r file` | Add read to others | `chmod o+r public.txt` |
| `chmod a+x file` | Add execute to all | `chmod a+x deploy.sh` |

---

## 👤 chown (Change Ownership)

| Command | Purpose | Example |
|--------|--------|---------|
| `chown user file` | Change file owner | `chown alice document.txt` |
| `chown user:group file` | Change owner and group | `chown alice:developers project.zip` |
| `chown -R user dir` | Recursive ownership change | `chown -R root /var/log` |

---

## 👥 chgrp (Change Group)

| Command | Purpose | Example |
|--------|--------|---------|
| `chgrp group file` | Change file group | `chgrp admins report.pdf` |
| `chgrp -R group dir` | Recursive group change | `chgrp -R staff /home/shared` |

---

## 🚩 Special Permissions (CRITICAL)

### SUID (Set User ID)
| Command | Purpose | Example |
|--------|--------|---------|
| `chmod u+s file` | Enable SUID | `chmod u+s /usr/bin/passwd` |
| `find / -perm -4000 2>/dev/null` | Find SUID files | `find / -perm -4000 2>/dev/null` |

📌 Executes file as file owner (often root).

---

### SGID (Set Group ID)
| Command | Purpose | Example |
|--------|--------|---------|
| `chmod g+s dir` | Enable SGID | `chmod g+s /shared` |
| `find / -perm -2000 2>/dev/null` | Find SGID files | `find / -perm -2000 2>/dev/null` |

📌 Files inherit group ownership.

---

### Sticky Bit
| Command | Purpose | Example |
|--------|--------|---------|
| `chmod +t dir` | Enable sticky bit | `chmod +t /tmp` |
| `ls -ld /tmp` | Common sticky-bit directory | `ls -ld /tmp` |

📌 Only file owner can delete files.

---

## 🔍 ACL (Access Control Lists)

| Command | Purpose | Example |
|--------|--------|---------|
| `setfacl -m u:user:rwx file` | Grant ACL permission | `setfacl -m u:john:rwx data.txt` |
| `setfacl -x u:user file` | Remove ACL | `setfacl -x u:john data.txt` |
| `setfacl -b file` | Remove all ACLs | `setfacl -b data.txt` |

---

## 🔐 Permission-Based Security Checks

| Command | Use Case | Example |
|--------|---------|---------|
| `find / -writable -type d 2>/dev/null` | Find writable directories | `find / -writable -type d 2>/dev/null` |
| `find / -perm -2 2>/dev/null` | World-writable files | `find / -perm -2 2>/dev/null` |
| `find / -user root -perm -4000` | Root-owned SUID binaries | `find / -user root -perm -4000` |

---

## 🚨 Cybersecurity Relevance

- **Misconfigured Permissions**: Can lead to **Privilege Escalation**.
- **World-Writable Files**: Allow attackers to plant malicious files for **Persistence**.
- **SUID Binaries**: Provide potential paths to **Root Access**.
- **ACL Misuse**: Can create **Hidden Access** for unauthorized users.

---

## 📌 Common Attack Targets

- `/etc/passwd`: Stores user account information.
- `/etc/shadow`: Contains password hashes (root-only access).
- `/etc/sudoers`: Defines sudo privileges.
- `/tmp`: Temporary file storage (often world-writable).
- `/var/tmp`: Similar to `/tmp`, used for temporary files.
- `/usr/bin`: Common location for executables.

---

## ✅ Used In

- **SOC Investigations**: Analyze file permissions for anomalies.
- **DFIR Evidence Analysis**: Identify misconfigurations during forensic investigations.
- **CTF Challenges**: Exploit permission misconfigurations for privilege escalation.
- **Linux Server Hardening**: Secure permissions to reduce attack surface.
