# 📌 Linux Notes: Essential Commands & Concepts

## 📂 File & Directory Management
- `ls` → List files in a directory
- `ls -l` → Detailed list with permissions
- `ls -a` → Show hidden files
- `mkdir folder_name` → Create a new directory
- `rm file_name` → Delete a file
- `rm -r folder_name` → Delete a folder and its contents
- `mv old_name new_name` → Rename or move a file
- `cp source destination` → Copy a file or directory

## 🔑 File Permissions & Ownership
- **Permission Structure:** `rwxrwxrwx`
  - `r` (Read) → View file contents
  - `w` (Write) → Modify file contents
  - `x` (Execute) → Run file as a program/script
- **Change Permissions:**
  - `chmod 600 file` → Owner: Read/Write
  - `chmod 644 file` → Owner: Read/Write, Others: Read
  - `chmod 700 file` → Owner: Read/Write/Execute
  - `chmod 755 file` → Owner: All, Others: Read/Execute
- **Numeric Values:**
  - `4` → Read, `2` → Write, `1` → Execute
  - Example: `chmod 754 file` (Owner: `rwx`, Group: `r`, Others: `r`)
- **Ownership:**
  - `chown new_owner file` → Change file owner
  - `chgrp new_group file` → Change group ownership

## 👤 User Management
- `whoami` → Check current user
- `id` → Show user ID and groups
- `sudo adduser newuser` → Add a new user
- `sudo deluser user` → Remove a user
- `sudo usermod -aG group_name user` → Add user to a group

## 🛠 Automating Git with Cron Jobs
- **Setting up automation:**
  - `crontab -e` → Edit cron jobs
  - Example job (auto-push changes at 22:00 daily):
    ```
    0 22 * * * cd ~/Documents/daily-ai-journal && git add . && git commit -m "Auto update journal" && git push origin main >> ~/cron_git_log.txt 2>&1
    ```
  - Check logs with `cat ~/cron_git_log.txt`

## 🌟 Git Workflow (Local to GitHub)
1️⃣ **Initialize Git:**
   ```bash
   git init
   git branch -m main  # Rename 'master' to 'main'
   ```
2️⃣ **Connect to GitHub:**
   ```bash
   git remote add origin git@github.com:USERNAME/REPOSITORY.git
   ```
3️⃣ **Push Changes:**
   ```bash
   git add .
   git commit -m "Your commit message"
   git push origin main
   ```
4️⃣ **Fixing Push Errors:**
   ```bash
   git pull --rebase origin main
   git push origin main
   ```
5️⃣ **Deleting Files from GitHub:**
   ```bash
   git rm file_name
   git commit -m "Removed old file"
   git push origin main
   ```

---

This document will be **updated over time** as we explore more Linux concepts. 🚀



