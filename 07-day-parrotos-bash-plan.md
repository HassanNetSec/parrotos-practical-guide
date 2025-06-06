# 🗓️ 7-Day Practical Plan: Bash Scripting + Filesystem + Networking on Parrot OS (Cybersecurity Focus)

Welcome to this focused **7-day journey** into mastering **Bash scripting**, **Linux filesystem**, and **networking essentials** using **Parrot OS** – ideal for cybersecurity students and enthusiasts.

---

## 📅 Day 1: Linux & Bash Basics on Parrot OS

### 🔧 Topics:
- Navigate the filesystem: `ls`, `cd`, `pwd`
- Basic Bash scripting: creating `.sh` files and running them with `bash` or `./script.sh`
- Common commands: `echo`, `cat`, `head`, `tail`
- Understanding file paths: **relative vs absolute**

### 📝 Exercise:
```bash
#!/bin/bash
echo "Current Directory: $(pwd)"
echo "Files:"
ls -lah
```

---

## 📅 Day 2: File and Directory Management

### 🔧 Topics:
- Commands: `touch`, `mkdir`, `rm`, `cp`, `mv`, `find`
- Handling hidden files: `ls -a`
- Using wildcards: `*`, `?`

### 📝 Exercise:
```bash
#!/bin/bash
mkdir project
touch project/file{1..3}.txt
mv project/file1.txt project/file1_renamed.txt
ls -l project
```

---

## 📅 Day 3: File Permissions & Ownership

### 🔧 Topics:
- Understanding `rwx` (read, write, execute)
- Managing permissions: `chmod`, `chown`, `chgrp`
- Symbolic vs numeric permissions
- Special permissions: **SUID**, **SGID**, **Sticky Bit**

### 📝 Exercise:
```bash
#!/bin/bash
touch myfile.txt
chmod 640 myfile.txt
sudo chown $USER:$USER myfile.txt
ls -l myfile.txt >> permissions.log
```

---

## 📅 Day 4: Bash Variables, Conditionals & File Tests

### 🔧 Topics:
- Bash variables and environment variables: `$USER`, `$HOME`
- Conditional logic: `if`, `else`, `elif`
- File test operators: `-f`, `-d`, `-e`, `-r`, `-w`

### 📝 Exercise:
```bash
#!/bin/bash
BACKUP_DIR="$HOME/backup"

if [ ! -d "$BACKUP_DIR" ]; then
    mkdir "$BACKUP_DIR"
    echo "Backup directory created."
else
    echo "Backup directory already exists."
fi
```

---

## 📅 Day 5: Loops & User Input

### 🔧 Topics:
- Loop types: `for`, `while`, `until`
- Accepting user input using `read`
- Automating repetitive filesystem tasks

### 📝 Exercise:
```bash
#!/bin/bash
read -p "Enter directory: " DIR

for FILE in "$DIR"/*; do
    chmod 644 "$FILE"
    echo "Updated permissions for $FILE"
done
```

---

## 📅 Day 6: Networking Commands & Scripts

### 🔧 Topics:
- Key networking tools: `ip`, `ping`, `ss`, `nmap`, `tcpdump`, `curl`
- Scan IPs and save results to log files

### 📝 Exercise:
```bash
#!/bin/bash
IP_LIST=("8.8.8.8" "1.1.1.1")

for IP in "${IP_LIST[@]}"; do
    ping -c 2 "$IP" >> ping_log.txt
    echo "Pinged $IP"
done
```

---

## 📅 Day 7: Mini Project & Full Review

### 🎯 Project Goals:
- ✅ Check internet connectivity
- ✅ Perform a local network scan with `nmap`
- ✅ Log scan results to a file
- ✅ Set secure permissions on the log file

### 📝 Project Script Example:
```bash
#!/bin/bash

LOG="scan_report.txt"

echo "[*] Checking connectivity..."
ping -c 2 8.8.8.8 > /dev/null && echo "Internet: OK" || echo "No Internet"

echo "[*] Scanning local network..."
nmap -sn 192.168.1.0/24 > "$LOG"

chmod 600 "$LOG"
echo "[*] Scan complete. Results saved to $LOG"
```

---

## 🎁 Bonus Tips for Parrot OS

- 🔐 Use `sudo` only when necessary for system-level changes
- 📂 Explore system logs in `/var/log/`
- ⚙️ Combine commands using `|`, `>`, and `>>` for chaining and logging
- 💡 Test your scripts on non-critical files before running them on real data

---

## 📚 What’s Next?

After this week, you’ll be ready to:
- Start building **automation scripts** for security tasks
- Dive into **web security** and **tool-based testing** (e.g. Burp Suite, sqlmap)
- Explore **cron jobs**, **log monitoring**, and **network traffic analysis**

---

## 🌐 Contribute

Found a bug? Want to improve this guide? PRs are welcome!  
Let’s make Parrot OS easier to learn for everyone 💻🛡️

---

📘 **Repo:** [`ParrotOS Practical Guide`](https://github.com/HassanNetSec/ParrotOSPracticalGuide)  
✍️ **Created by:** [Hassan Khan](https://github.com/HassanNetSec)

