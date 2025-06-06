# 🐦 ParrotOS Practical Guide – Bash, Linux & Cybersecurity Essentials

Welcome to the **ParrotOS Practical Guide** — a curated set of hands-on tutorials, scripts, and walkthroughs for learning **Linux**, **Bash scripting**, **filesystem management**, and **basic network operations** with a cybersecurity focus.

This repository is designed especially for:
- 💻 Cybersecurity students
- 🔐 Ethical hacking learners
- 🐧 Beginners transitioning to Linux
- 🧠 Anyone looking to automate daily tasks with Bash

---

## 📚 What's Inside?

| Folder / File               | Description                                          |
| -------------------------- | ---------------------------------------------------- |
| `01-file-permissions.md`   | Guide on Linux file permissions, ownership & SUID    |
| `07-day-parrotos-bash-plan.md` | Full 7-day learning plan: Bash + Network commands    |
| `scripts/` (coming soon)   | Bash automation scripts for filesystem & networking  |

---

## 🗓️ 7-Day Parrot OS Learning Plan

Jumpstart your learning with a structured day-by-day roadmap:

- **Day 1** – Linux Basics & Bash Intro
- **Day 2** – File/Folder Management
- **Day 3** – Permissions & Ownership
- **Day 4** – Bash Variables & Conditionals
- **Day 5** – Loops & User Input
- **Day 6** – Networking Tools (ping, nmap, curl)
- **Day 7** – Final Project: Scan, Log & Secure Script

📄 [View the full plan here →](07-day-parrotos-bash-plan.md)

---

## 📘 Sample Tutorial: File Permissions

```bash
chmod u+x script.sh       # Give execute permission to the user
chown hassan file.txt     # Change file owner to hassan
chmod 755 script.sh       # rwxr-xr-x using numeric mode
```

Learn more in [`01-file-permissions.md`](01-file-permissions.md)

---

## 📁 How to Use

1. **Clone the repository**
```bash
git clone https://github.com/HassanNetSec/ParrotOSPracticalGuide.git
cd ParrotOSPracticalGuide
```

2. **Browse and try tutorials**
   - Read markdown files one by one
   - Practice Bash commands in your Parrot OS terminal

3. **Run example scripts (coming soon)**
```bash
bash scripts/day3_permissions.sh
```

---

## 🚀 Features

- Beginner-friendly language and examples
- Security-aware scripting (safe permissions, logging)
- Focused on **Parrot OS**, but compatible with any Debian-based distro
- Encourages safe Linux practices (e.g., testing, logging, sudo usage)

---

## 📦 Upcoming Additions

- [ ] Bash script examples for each tutorial
- [ ] A section on log file analysis and monitoring (`/var/log/`)
- [ ] Web vulnerability practice (XSS, SQLi) on localhost
- [ ] Cron job automation walkthrough

---

## 🤝 Contributing

If you'd like to improve the guide:
- Fork the repo
- Add your edits or examples
- Submit a Pull Request (PR)

Suggestions, issues, and improvements are always welcome!

---

## 🙋 About the Author

**Hassan Khan**  
Cybersecurity & Full Stack Enthusiast | GIKI Computer Science Student  
🎯 Interests: Linux, Automation, Ethical Hacking, Web Security  
🔗 [GitHub – HassanNetSec](https://github.com/HassanNetSec)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

🛡️ **Master your terminal. Script your skills. Secure your system.**

