# Linux Shell Operators 🧩

Comprehensive reference of Linux shell operators used to control command execution, input/output flow, condition handling, and automation. These operators are heavily used in **cybersecurity, DFIR, SOC operations, bash scripting, and privilege escalation scenarios**.

---

## 🔗 Command Chaining Operators

| Operator | Name | Description | Basic Example |
|--------|------|-------------|---------------|
| `;` | Command separator | Executes commands sequentially regardless of success | `ls; pwd` |
| `&&` | AND operator | Executes next command only if previous succeeds | `mkdir test && cd test` |
| `||` | OR operator | Executes next command only if previous fails | `cd test || echo "Failed"` |

---

## 🔁 Background & Job Control Operators

| Operator | Name | Description | Example |
|--------|------|-------------|---------|
| `&` | Background operator | Runs command in background | `sleep 30 &` |
| `jobs` | Job list | Shows background jobs | `jobs` |
| `fg` | Foreground | Bring job to foreground | `fg %1` |
| `bg` | Background | Resume stopped job in background | `bg %1` |

---

## 🔀 Input / Output Redirection Operators

### Output Redirection

| Operator | Description | Example |
|--------|-------------|---------|
| `>` | Redirect output (overwrite) | `ls > files.txt` |
| `>>` | Redirect output (append) | `ls >> files.txt` |
| `2>` | Redirect error output | `ls /root 2> error.txt` |
| `2>>` | Append error output | `cmd 2>> error.txt` |
| `&>` | Redirect stdout and stderr | `ls &> all.txt` |

---

### Input Redirection

| Operator | Description | Example |
|--------|-------------|---------|
| `<` | Redirect input from file | `cat < file.txt` |
| `<<` | Here document | `cat << EOF` |
| `<<<` | Here string | `grep root <<< "$USER"` |

---

## 🔄 Pipes

| Operator | Description | Example |
|--------|-------------|---------|
| `|` | Pass output of one command as input to another | `ps aux | grep root` |

🔐 **Cybersecurity Use**: Log filtering, process analysis, alert triage.

---

## 🧠 Logical Test Operators (Used in Scripts)

| Operator | Meaning | Example |
|--------|--------|---------|
| `-eq` | Equal | `[ $a -eq 10 ]` |
| `-ne` | Not equal | `[ $a -ne 10 ]` |
| `-gt` | Greater than | `[ $a -gt 5 ]` |
| `-lt` | Less than | `[ $a -lt 20 ]` |
| `-ge` | Greater or equal | `[ $a -ge 10 ]` |
| `-le` | Less or equal | `[ $a -le 10 ]` |

---

## 📁 File Test Operators

| Operator | Description | Example |
|--------|-------------|---------|
| `-f` | File exists and is regular | `[ -f file.txt ]` |
| `-d` | Directory exists | `[ -d /etc ]` |
| `-r` | File readable | `[ -r file.txt ]` |
| `-w` | File writable | `[ -w file.txt ]` |
| `-x` | File executable | `[ -x script.sh ]` |
| `-s` | File not empty | `[ -s log.txt ]` |

---

## 🔤 String Operators

| Operator | Description | Example |
|--------|-------------|---------|
| `=` | Strings equal | `[ "$a" = "$b" ]` |
| `!=` | Strings not equal | `[ "$a" != "$b" ]` |
| `-z` | String is empty | `[ -z "$var" ]` |
| `-n` | String is not empty | `[ -n "$var" ]` |

---

## 🧮 Arithmetic Operators

| Operator | Description | Example |
|--------|-------------|---------|
| `+` | Addition | `((a+b))` |
| `-` | Subtraction | `((a-b))` |
| `*` | Multiplication | `((a*b))` |
| `/` | Division | `((a/b))` |
| `%` | Modulus | `((a%2))` |

---

## 🔄 Command Substitution Operators

| Operator | Description | Example |
|--------|-------------|---------|
| `` `command` `` | Old-style substitution | ``echo `whoami` `` |
| `$(command)` | Modern substitution | `echo $(whoami)` |

✅ Preferred: `$(command)`

---

## 🧱 Grouping Operators

| Operator | Description | Example |
|--------|-------------|---------|
| `( )` | Run commands in subshell | `(cd /tmp && ls)` |
| `{ }` | Group commands in current shell | `{ ls; pwd; }` |

---

## 🔐 Cybersecurity Relevance

- Used in **payload chaining**
- Essential for **log parsing**
- Helps bypass **restricted shells**
- Critical in **automation & IR scripts**
- Common in **CTF privilege escalation**

---

## 📌 Best Practice Notes

- Always quote variables: `"$var"`
- Prefer `$(command)` over backticks
- Avoid dangerous redirections as root
- Use `set -e` in scripts for safety

---
