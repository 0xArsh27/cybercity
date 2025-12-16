# Linux File System Commands 🗂️

Comprehensive guide to essential Linux file system commands for exploration, management, and analysis. These commands are particularly relevant for cybersecurity, Digital Forensics and Incident Response (DFIR), and privilege escalation scenarios.

---

## 📁 Directory Navigation

| **Command** | **Description** |
|-------------|-----------------|
| `pwd`       | Display the current working directory |
| `ls`        | List contents of a directory |
| `ls -l`     | List contents with detailed information (permissions, ownership) |
| `ls -a`     | Show hidden files in the directory |
| `ls -la`    | Detailed listing including hidden files |
| `tree`      | Visualize directory structure as a tree |

---

## 📄 File Creation & Modification

| **Command**         | **Description** |
|---------------------|-----------------|
| `touch file`        | Create an empty file or update its timestamp |
| `echo "text" > file` | Write text to a file (overwrite existing content) |
| `echo "text" >> file`| Append text to a file |
| `cat > file`        | Create a file and input content from stdin |

---

## 📂 File & Directory Management

| **Command**         | **Description** |
|---------------------|-----------------|
| `mkdir dir`         | Create a new directory |
| `mkdir -p a/b/c`    | Create nested directories |
| `rmdir dir`         | Remove an empty directory |
| `rm file`           | Delete a file |
| `rm -r dir`         | Recursively delete a directory |
| `rm -rf dir`        | Force delete a directory (⚠ Use with caution) |
| `cp src dst`        | Copy a file |
| `cp -r src dst`     | Recursively copy a directory |
| `mv src dst`        | Move or rename a file/directory |

---

## 👀 Viewing File Content

| **Command**         | **Description** |
|---------------------|-----------------|
| `cat file`          | Display the content of a file |
| `less file`         | View file content with pagination |
| `more file`         | Simple paginated file viewer |
| `head file`         | Display the first 10 lines of a file |
| `head -n 20 file`   | Display the first 20 lines of a file |
| `tail file`         | Display the last 10 lines of a file |
| `tail -f file.log`  | Monitor a file in real-time |

---

## 🔎 File Search & Discovery

| **Command**         | **Description** |
|---------------------|-----------------|
| `find / -name file` | Search for a file by name |
| `find / -iname file`| Case-insensitive file search |
| `find / -type f`    | Find regular files |
| `find / -type d`    | Find directories |
| `find / -perm -4000`| Locate SUID files (useful for privilege escalation) |
| `locate file`       | Quickly search for files using an indexed database |
| `updatedb`          | Update the locate command's database |

---

## 📊 File Information & Metadata

| **Command**         | **Description** |
|---------------------|-----------------|
| `file file`         | Identify the type of a file |
| `stat file`         | Display detailed file metadata |
| `lsblk`             | List information about block devices |
| `df -h`             | Show disk usage in human-readable format |
| `du -sh dir`        | Display the size of a directory |

---

## 🔗 Links & Inodes

| **Command**         | **Description** |
|---------------------|-----------------|
| `ln file link`      | Create a hard link |
| `ln -s file link`   | Create a symbolic link |
| `ls -i`             | Display inode numbers |

---

## 🗜️ Compression & Archives

| **Command**         | **Description** |
|---------------------|-----------------|
| `tar -cvf a.tar dir`| Create a tar archive |
| `tar -xvf a.tar`    | Extract a tar archive |
| `tar -czvf a.tar.gz dir` | Create a gzip-compressed tar archive |
| `tar -xzvf a.tar.gz`| Extract a gzip-compressed tar archive |
| `zip a.zip file`    | Compress a file into a zip archive |
| `unzip a.zip`       | Extract files from a zip archive |

---

## 📌 Mounting & File Systems

| **Command**         | **Description** |
|---------------------|-----------------|
| `mount`             | Display mounted file systems |
| `mount /dev/sdb /mnt` | Mount a device to a directory |
| `umount /mnt`       | Unmount a device |
| `df -T`             | Display file system types |

---

## 🔐 Cybersecurity Relevance

- **Hidden Files**: `.ssh`, `.bash_history` (potential sensitive information)
- **SUID Files**: Useful for privilege escalation attacks
- **Logs & Configs**: Critical for evidence analysis in DFIR
- **Large Files**: Indicators of potential data exfiltration

---


