This is a crucial addition, Jeevan! **Networking** is the backbone of Cloud computing. I have updated your master `README.md` to include Day 4 while maintaining the standardized 3-point practice structure you requested.

Copy the updated code below into your file in VS Code:

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

### 🛠️ Hands-on Practice
**1. Setup:** `mkdir devops_practice && cd devops_practice`  
**2. Manipulate:** `touch file1.txt file2.txt`, `ls -a`, `cd ..`  
**3. Writing & Reading:** `pwd`, `clear`

---

## 🔵 Day 2: Linux File Management

### 📖 Concept
DevOps engineers manage logs and configuration files. You must be able to move, copy, and delete data safely.

### 🛠️ Hands-on Practice
**1. Setup:** `mkdir linux_day2 && cd linux_day2 && touch devops.txt cloud.txt`  
**2. Manipulate:** `cp devops.txt devops_copy.txt`, `mv cloud.txt cloud_notes.txt`, `rm aws.txt`  
**3. Writing & Reading:** `echo "Learning DevOps" > devops.txt`, `cat devops.txt`, `tail -f devops.txt`

---

## 🟡 Day 3: Linux File Permissions (Security)

### 📖 Concept
Linux security is based on Read (r), Write (w), and Execute (x) permissions for Owner, Group, and Others.

### 🛠️ Hands-on Practice
**1. Setup:** `mkdir linux_day3 && cd linux_day3 && touch script.sh deploy.sh`  
**2. Manipulate:** `chmod 755 script.sh`, `chmod +x deploy.sh`, `ls -l`  
**3. Writing & Reading:** `echo "echo 'Deploying...'" > deploy.sh`, `./deploy.sh`

---

## 🌐 Day 4: Linux Networking Basics

### 📖 Concept
Cloud servers don't have browsers. DevOps engineers use the CLI to test connectivity, download software, and check API responses. Understanding IP addresses and DNS is vital for server communication.

### 🛠️ Hands-on Practice

**1. Setup:**
```bash
# Ensure you are in your home directory
cd ~
mkdir day4_network
cd day4_network

```

**2. Manipulate:**

```bash
# Check IP Address
ip a             # Look for 'inet' to find your IP

# Test Connectivity (Press Ctrl + C to stop)
ping google.com  
ping -c 4 google.com  # Ping exactly 4 times

# Download Files
wget [https://example.com](https://example.com)  # Downloads index.html

```

**3. Writing & Reading:**

```bash
# Test Web/API responses
curl [https://example.com](https://example.com)   # View raw HTML code in terminal

# Check downloaded file
ls -l
cat index.html

# Real-world Fun Task
curl wttr.in               # Fetches live weather data

```

---

## ✅ Progress Summary

* [x] Day 1: Navigation & Basic CLI
* [x] Day 2: File Operations & Log Reading
* [x] Day 3: Permissions & Security
* [x] Day 4: Networking Basics (`ip`, `ping`, `curl`, `wget`)
* [ ] Day 5: Package Management & Services (Coming Soon)

---

## 💡 Key Commands to Remember

`ip a` • `ping` • `curl` • `wget` • `chmod` • `tail -f` • `Ctrl + C` (Stop process)

*Ready for Day 5? Just come back tomorrow and type:*

> **"Day 5 DevOps study"** 🚀

```

---

### Pro-Tip for Day 4
When you use `curl wttr.in`, notice how the server sends back a formatted "UI" directly in your text terminal. This is a great example of how DevOps engineers can get data from external APIs without ever needing a mouse or a browser!

Would you like me to add a **"Networking Vocabulary"** table to this file to help you remember terms like **IP, DNS, and Gateway**?

```