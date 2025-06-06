# 🔐 01 – Linux File Permissions & Ownership

Welcome to **Part 1** of the `ParrotOS Practical Guide`!  
In this section, we cover one of the most essential Linux concepts: **file permissions and ownership**.

---

## 📁 What Are File Permissions?

Each file and directory has access rules that determine:
- Who can **read** it
- Who can **write (modify/delete)** it
- Who can **execute** (run or enter) it

### 🔍 Example

```bash
-rw-r--r-- 1 user user   0 Jun 6 13:40 archive.txt
drwxr-xr-x 2 root root  80 Jun 6 13:27 Desktop
```

| Symbol | Meaning                |
| ------ | ---------------------- |
| `d`    | Directory (if present) |
| `r`    | Read permission        |
| `w`    | Write permission       |
| `x`    | Execute permission     |
| `-`    | No permission          |

---

## 👥 User Types

Linux divides users into three categories:

| Symbol | Who?              |
| ------ | ----------------- |
| `u`    | User (owner)      |
| `g`    | Group             |
| `o`    | Others (everyone) |
| `a`    | All (u+g+o)       |

---

## ✍️ Changing Permissions

### ➕ Add Permission

```bash
chmod a+x script.sh       # All users can execute
chmod u+w notes.txt       # Owner can write
```

### ➖ Remove Permission

```bash
chmod o-r file.txt        # Remove read for others
chmod a-rwx secret.txt    # Remove all permissions
```

### 🎯 Set Specific Permissions (Symbolic)

```bash
chmod u=rwx,g=rw,o=rx file.sh
```

### 🔢 Set Permissions (Numeric)

| Value | Meaning |
| ----- | ------- |
| 7     | rwx     |
| 6     | rw-     |
| 5     | r-x     |
| 4     | r--     |
| 0     | ---     |

```bash
chmod 755 script.sh    # rwxr-xr-x
chmod 644 notes.txt    # rw-r--r--
```

---

## 👑 Ownership Commands

### 🔄 Change Owner

```bash
sudo chown hassan file.txt
```

### 🔁 Change Group

```bash
sudo chgrp developers file.txt
```

### 🧠 Change Both

```bash
sudo chown hassan:developers file.txt
```

---

## 🔐 Special Permissions

### 🟥 1. SUID (Set User ID)

* Run file **as the file owner**, not as the user running it.
* Useful for system commands like `passwd`.

```bash
chmod u+s file.sh     # Add SUID
chmod u-s file.sh     # Remove SUID
```

✅ Example:

```bash
ls -l /usr/bin/passwd
-rwsr-xr-x 1 root root 68248 Mar 23 2023 /usr/bin/passwd
```

---

### 🟨 2. SGID (Set Group ID)

* On **files**: run with the file's group permissions.
* On **directories**: new files inherit the group.

```bash
chmod g+s /project
```

---

### 🟦 3. Sticky Bit

* Used on **shared directories** (like `/tmp`).
* Only file **owners** can delete their own files.

```bash
chmod +t /shared
```

✅ Example:

```bash
ls -ld /tmp
drwxrwxrwt 10 root root 4096 Jun 6 15:00 /tmp
```

---

## 🧪 Practice Examples

```bash
touch demo.sh
chmod 755 demo.sh
sudo chown hassan demo.sh
chmod u+s demo.sh

mkdir devteam
chmod g+s devteam

chmod +t /tmp/shared-folder
```

---

## ✅ Summary Table

| Concept       | Command Example       |
| ------------- | --------------------- |
| Add exec      | `chmod u+x file.sh`   |
| Numeric chmod | `chmod 755 script.sh` |
| Change owner  | `chown user file.txt` |
| Change group  | `chgrp dev file.txt`  |
| SUID          | `chmod u+s binary`    |
| SGID          | `chmod g+s /folder`   |
| Sticky Bit    | `chmod +t /shared`    |

---

🔗 **Next Topic:** [02 - User & Group Management (coming soon)]  
📘 **Repo:** [`ParrotosPracticalGuide`](https://github.com/yourusername/ParrotosPracticalGuide)
