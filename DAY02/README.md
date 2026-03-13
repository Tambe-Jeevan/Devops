# 🐧 Day 2: Linux File Management
**Goal:** Master the commands used by Cloud Admins to manage logs, configs, and deployments.

---

## 1️⃣ Core Concepts
Yesterday was about navigation; today is about **manipulation**. In a DevOps environment, you will constantly:
* **Move** configuration files to specific server directories.
* **Copy** templates for new deployments.
* **Delete** old temporary files to save disk space.
* **View** application logs to debug errors.

---

## 2️⃣ Essential Command Reference

### 📂 Copying (cp)
* `cp source.txt destination.txt` — Copy a file.
* `cp file.txt /path/to/folder/` — Copy file into a specific directory.
* `cp -r folder1 folder2` — **Recursive** copy (required for folders).

### 🚚 Moving & Renaming (mv)
* `mv oldname.txt newname.txt` — Rename a file.
* `mv file.txt /target/directory/` — Move (Cut & Paste) a file.

### 🗑️ Deleting (rm)
> ⚠️ **Warning:** Linux has no "Recycle Bin." Once you `rm`, it is gone.
* `rm file.txt` — Delete a file.
* `rm -r foldername` — Delete a folder and everything inside it.

### 📄 Viewing Content
| Command | Usage | Best For... |
| :--- | :--- | :--- |
| `cat` | `cat file.txt` | Viewing small files entirely. |
| `less` | `less file.txt` | Scrolling through large files (Press **q** to exit). |
| `head` | `head file.txt` | Seeing the first 10 lines. |
| `tail` | `tail file.txt` | Seeing the last 10 lines (Great for logs!). |

---

## 🛠️ Hands-on Practice Lab

Follow these steps in your terminal to build muscle memory:

1. **Setup:**
   ```bash
   mkdir linux_day2
   cd linux_day2
   touch devops.txt cloud.txt aws.txt