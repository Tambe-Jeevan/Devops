Excellent progress, Jeevan! Monitoring system health and managing background tasks is where you truly start acting like a System Administrator.

I have updated your master `README.md` to include **Day 5**, keeping your specific 3-point practice structure and the consolidated format.

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
**1. Setup:** `mkdir devops_practice && cd devops_practice`  
**2. Manipulate:** `touch file1.txt file2.txt`, `ls -a`, `cd ..`  
**3. Writing & Reading:** `pwd`, `clear`

---

## 🔵 Day 2: Linux File Management
**1. Setup:** `mkdir linux_day2 && cd linux_day2 && touch devops.txt cloud.txt`  
**2. Manipulate:** `cp devops.txt devops_copy.txt`, `mv cloud.txt cloud_notes.txt`, `rm aws.txt`  
**3. Writing & Reading:** `echo "Learning DevOps" > devops.txt`, `cat devops.txt`, `tail -f devops.txt`

---

## 🟡 Day 3: Linux File Permissions (Security)
**1. Setup:** `mkdir linux_day3 && cd linux_day3 && touch script.sh deploy.sh`  
**2. Manipulate:** `chmod 755 script.sh`, `chmod +x deploy.sh`, `ls -l`  
**3. Writing & Reading:** `echo "echo 'Deploying...'" > deploy.sh`, `./deploy.sh`

---

## 🌐 Day 4: Linux Networking Basics
**1. Setup:** `cd ~ && mkdir day4_network && cd day4_network`  
**2. Manipulate:** `ip a`, `ping -c 4 google.com`, `wget https://example.com`  
**3. Writing & Reading:** `curl https://example.com`, `ls -l`, `curl wttr.in`

---

## ⚙️ Day 5: Linux Process Management

### 📖 Concept
A process is any program running on the system (Nginx, Database, etc.). DevOps engineers must monitor CPU/Memory usage and stop hanging processes to keep servers healthy.

### 🛠️ Hands-on Practice

**1. Setup:**
```bash
# Start a fake process in the background
sleep 200 & 
# The '&' symbol sends the command to the background
```

**2. Manipulate:**
```bash
# View Processes
ps              # Simple view
ps -ef          # Detailed view (User, PID, Command)
top             # Real-time monitor (Press 'q' to exit)

# Find and Terminate
ps -ef | grep sleep   # Find the Process ID (PID) of your sleep command
kill <PID>            # Stop the process gracefully
kill -9 <PID>         # Force kill (if it doesn't stop)
```

**3. Writing & Reading:**
```bash
# Managing foreground/background
sleep 100 &     # Start again
jobs            # List background jobs
fg              # Bring back to foreground (Ctrl + C to kill it now)
```

---

## ✅ Progress Summary
- [x] Day 1: Navigation & Basic CLI
- [x] Day 2: File Operations & Log Reading
- [x] Day 3: Permissions & Security
- [x] Day 4: Networking Basics
- [x] Day 5: Process Management (`ps`, `top`, `kill`)
- [ ] Day 6: Package Management (Coming Soon)

---

## 💡 Key Commands to Remember
`ps -ef` • `top` • `kill -9` • `grep` • `&` (Background) • `fg` (Foreground)

*Ready for Day 6? Just come back tomorrow and type:*
> **"Day 6 DevOps study"** 🚀
```

---

### Pro-Tip for your GitHub
Since you are using `top` and `ps -ef`, you might notice a lot of information. In a real job, you will use `htop` for a more colorful and readable view. You can try installing it tomorrow during the "Package Management" lesson!

Would you like me to show you how to add a **"Table of Contents"** at the top of this file so you can jump to any day quickly?