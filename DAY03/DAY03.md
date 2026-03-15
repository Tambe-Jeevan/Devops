Great work keeping the momentum, Jeevan! Day 3 is a huge milestone because **Permissions** are the core of Cloud security.

I have updated your master `README.md` to include Day 3. I followed your specific structure for the practice labs to keep it consistent.

---

```markdown
# 🚀 6-Month Cloud & DevOps Engineer Challenge
**Student:** Jeevan  
**Goal:** Master Cloud & DevOps through consistent 2-hour daily micro-learning.

---

## 📅 The Daily System (2 Hours)
* **30 min:** Concept Learning
* **60 min:** Hands-on Practice
* **30 min:** Small Task / Revision

---

## 🟢 Day 1: Introduction to Linux (Foundation)

### 📖 Concept
Most DevOps servers run on Linux. It is the engine behind Git, Docker, and Kubernetes.
* **Why?** Open source, lightweight, secure, and easy to automate via CLI.

### 🛠️ Hands-on Practice

**1. Setup:**
```bash
mkdir devops_practice
cd devops_practice

```

**2. Manipulate:**

```bash
touch file1.txt file2.txt file3.txt
ls -a     # Show all files
cd ..     # Go back
cd devops_practice

```

**3. Writing & Reading:**

```bash
pwd       # Confirm current directory
clear     # Clean the screen

```

---

## 🔵 Day 2: Linux File Management

### 📖 Concept

DevOps engineers manage logs and configuration files. You must be able to move, copy, and delete data safely.

### 🛠️ Hands-on Practice

**1. Setup:**

```bash
mkdir linux_day2
cd linux_day2
touch devops.txt cloud.txt aws.txt

```

**2. Manipulate:**

```bash
cp devops.txt devops_copy.txt    # Backup
mv cloud.txt cloud_notes.txt     # Rename/Move
rm aws.txt                       # Delete file

```

**3. Writing & Reading:**

```bash
echo "Learning DevOps with Jeevan" > devops.txt
cat devops.txt
tail -f devops.txt                # Follow live logs

```

---

## 🟡 Day 3: Linux File Permissions (Security)

### 📖 Concept

Linux uses a security model based on **Read (r)**, **Write (w)**, and **Execute (x)**. These are assigned to the **Owner**, **Group**, and **Others**.

* **Permissions numbers:** 7 (rwx), 6 (rw-), 5 (r-x), 4 (r--).
* **DevOps Use Case:** Ensuring scripts can run (`+x`) while keeping configuration files secure.

### 🛠️ Hands-on Practice

**1. Setup:**

```bash
mkdir linux_day3
cd linux_day3
touch file1.txt file2.txt script.sh deploy.sh

```

**2. Manipulate:**

```bash
# Check current permissions
ls -l

# Change permissions using numbers
chmod 777 file1.txt    # Full access for everyone (dangerous!)
chmod 644 file2.txt    # Owner can read/write, others can only read

# Change permissions for scripts
chmod +x script.sh     # Make it executable
chmod +x deploy.sh     # Make deploy script executable

# Change ownership (requires sudo)
# sudo chown ubuntu file1.txt

```

**3. Writing & Reading:**

```bash
# Add content to the executable script
echo "echo 'Deploy script running'" > deploy.sh

# Run the script
./deploy.sh

```

---

## ✅ Progress Summary

* [x] Day 1: Navigation & Basic CLI
* [x] Day 2: File Operations & Log Reading
* [x] Day 3: Permissions & Security (`chmod`, `chown`)
* [ ] Day 4: Users & Groups (Coming Soon)

---

## 💡 Key Commands to Remember

`pwd` • `ls -l` • `cd` • `mkdir` • `touch` • `cp` • `mv` • `rm` • `cat` • `chmod` • `chown`

*Ready for Day 4? Just come back tomorrow and type:*

> **"Day 4 DevOps study"** 🚀

```

---

### What's Next?
When you copy this into VS Code, you can see your progress growing! 

Would you like me to help you **Commit** and **Push** these changes to your GitHub repository so your progress is saved online?

```