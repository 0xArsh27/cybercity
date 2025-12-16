# Linux General Utilities Commands 🌐

Essential Linux general-purpose utilities commonly used in cybersecurity, penetration testing, file transfer, remote access, and quick service hosting. These commands are indispensable for both beginners and advanced users in managing Linux systems efficiently.

---

## 📥 wget

| **Command** | **Flag** | **Description** | **Basic Example** |
|-------------|----------|-----------------|-------------------|
| `wget URL` | — | Download file from a URL | `wget https://example.com/file.txt` |
| `wget -O file URL` | `-O` | Save output with custom filename | `wget -O test.txt https://example.com/a.txt` |
| `wget -c URL` | `-c` | Resume interrupted download | `wget -c https://example.com/file.iso` |
| `wget -r URL` | `-r` | Recursive download | `wget -r http://site.com/files/` |
| `wget --mirror URL` | `--mirror` | Mirror entire website | `wget --mirror http://site.com` |

---

## 🌐 curl

| **Command** | **Flag** | **Description** | **Basic Example** |
|-------------|----------|-----------------|-------------------|
| `curl URL` | — | Fetch content from URL | `curl https://example.com` |
| `curl -O URL` | `-O` | Download file with same name | `curl -O https://example.com/file.txt` |
| `curl -o file URL` | `-o` | Save output with custom name | `curl -o test.txt https://example.com` |
| `curl -I URL` | `-I` | Fetch HTTP headers only | `curl -I https://example.com` |
| `curl -X POST URL` | `-X` | Send custom HTTP request | `curl -X POST https://api.site.com` |

---

## 🔐 ssh

| **Command** | **Flag** | **Description** | **Basic Example** |
|-------------|----------|-----------------|-------------------|
| `ssh user@host` | — | Connect to remote system | `ssh user@192.168.1.10` |
| `ssh -p port user@host` | `-p` | Connect using custom port | `ssh -p 2222 user@host` |
| `ssh -i key user@host` | `-i` | Login using private key | `ssh -i id_rsa user@host` |
| `ssh -v user@host` | `-v` | Verbose debugging mode | `ssh -v user@host` |

---

## 📁 scp

| **Command** | **Flag** | **Description** | **Basic Example** |
|-------------|----------|-----------------|-------------------|
| `scp file user@host:/path` | — | Copy file to remote system | `scp test.txt user@host:/tmp` |
| `scp user@host:/file .` | — | Copy file from remote | `scp user@host:/tmp/a.txt .` |
| `scp -r dir user@host:/path` | `-r` | Copy directory recursively | `scp -r data/ user@host:/opt` |
| `scp -P port file user@host:/path` | `-P` | Use custom SSH port | `scp -P 2222 a.txt user@host:/tmp` |

---

## 🖥️ python3 -m http.server

| **Command** | **Flag** | **Description** | **Basic Example** |
|-------------|----------|-----------------|-------------------|
| `python3 -m http.server` | — | Start HTTP server on default port 8000 | `python3 -m http.server` |
| `python3 -m http.server 8080` | Port | Start server on custom port | `python3 -m http.server 8080` |
| `python3 -m http.server --bind IP` | `--bind` | Bind server to specific IP address | `python3 -m http.server --bind 0.0.0.0` |
| `python3 -m http.server --directory DIR` | `--directory` | Serve files from a specific directory | `python3 -m http.server --directory /path/to/dir` |

---

## 🔐 Cybersecurity Usage Notes

- **`wget` & `curl`**: Useful for downloading payloads, analyzing malware, and testing web application responses.
- **`ssh`**: Essential for secure remote access, lateral movement in penetration testing, and managing remote servers.
- **`scp`**: Securely transfer files between systems, often used for exfiltration or deploying tools.
- **`python3 -m http.server`**: Quick setup for temporary file hosting, commonly used in Capture The Flag (CTF) challenges or during penetration testing engagements.

---
