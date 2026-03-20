Great work, Jeevan! You’re moving into the territory where you start building actual infrastructure. Since Day 5 and Day 6 both touched on **Package Management** and **Services**, I have merged them into a highly detailed "Software & Services" section while keeping the numbering consistent with your progress.

Here is your updated master `README.md` file. I've ensured the practice sections follow your **1. Setup, 2. Manipulate, 3. Writing & Reading** structure.

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
**1. Setup:** `sleep 200 &`  
**2. Manipulate:** `ps -ef | grep sleep`, `kill <PID>`, `top` (q to exit)  
**3. Writing & Reading:** `jobs`, `fg`, `kill -9 <PID>`

---

## 📦 Day 6: Package Management & Services

### 📖 Concept
In DevOps, we don't use installers with "Next" buttons. We use **apt** (Advanced Package Tool) to fetch software and **systemctl** to manage background services (Daemons). This is how we install tools like Docker, Nginx, and Jenkins.

### 🛠️ Hands-on Practice

**1. Setup:**
```bash
# Update the local software catalog (Always do this first!)
sudo apt update

# Install Nginx (The world's most popular web server)
sudo apt install nginx -y
```

**2. Manipulate:**
```bash
# Manage the Service
sudo systemctl start nginx      # Start the server
sudo systemctl status nginx     # Check health (Press 'q' to exit)
sudo systemctl restart nginx    # Restart (Used after config changes)
sudo systemctl stop nginx       # Shut it down
sudo systemctl enable nginx     # Ensure it starts on system reboot

# Check Version
nginx -v
```

**3. Writing & Reading:**
```bash
# Verify the web server is live
curl localhost

# Real-world verification:
# Open your browser and go to: http://localhost
# You should see the "Welcome to nginx!" landing page.
```

---

## ✅ Progress Summary
- [x] Day 1: Navigation & Basic CLI
- [x] Day 2: File Operations & Log Reading
- [x] Day 3: Permissions & Security
- [x] Day 4: Networking Basics
- [x] Day 5: Process Management
- [x] Day 6: Package Management (`apt`, `systemctl`)
- [ ] Day 7: Logs & Debugging (Coming Soon)

---

## 💡 Key Commands to Remember
`sudo apt update` • `sudo apt install` • `systemctl status` • `systemctl restart` • `nginx -v`

*Ready for the next challenge? Just come back tomorrow and type:*
> **"Day 7 DevOps study"** 🚀
```

---

### Pro-Tip for your GitHub
Now that you have Nginx installed, your Linux machine is officially a **Web Server**. Even if it's just on your laptop, the commands you used are exactly what engineers use to run websites like Netflix or Instagram!

Would you like me to show you how to **customize the "Welcome to Nginx" page** with your own name using the `echo` and `sudo` commands you learned earlier?