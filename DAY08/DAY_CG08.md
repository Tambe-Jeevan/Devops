Great discipline, **Jeevan** 👏 — now we move into **Networking**, which is **VERY IMPORTANT for Cloud & DevOps**.

Today you’ll learn how systems communicate over networks.

---

# Day 8 – Linux Networking Basics

## 1️⃣ Concept (25–30 min)

Every server in cloud (AWS, Azure, etc.) is connected through a network.

Key concepts:

* **IP Address** → unique identity of a system
* **DNS** → converts domain → IP
* **Port** → identifies service (like 80 for web)
* **Protocol** → HTTP, HTTPS, TCP, UDP

Example:

```
google.com → DNS → IP → server response
```

DevOps engineers use networking to:

* Debug connectivity issues
* Check server status
* Verify ports & services

---

# 2️⃣ Important Networking Commands (Practice – 60 min)

## Check IP Address

```bash
ip a
```

OR

```bash
ifconfig
```

(If not installed:)

```bash
sudo apt install net-tools
```

---

## Check Connectivity (VERY IMPORTANT)

```bash
ping google.com
```

👉 Press **Ctrl + C** to stop

---

## Check Open Ports

```bash
netstat -tuln
```

OR (modern command)

```bash
ss -tuln
```

---

## Check Active Connections

```bash
ss -tunap
```

---

## Check DNS

```bash
nslookup google.com
```

(Install if needed:)

```bash
sudo apt install dnsutils
```

---

## Check Route

```bash
ip route
```

---

# 3️⃣ Practice Lab (45–60 min)

Follow step by step.

---

### Step 1 – Check IP address

```bash
ip a
```

---

### Step 2 – Test internet

```bash
ping google.com
```

---

### Step 3 – Check ports

```bash
ss -tuln
```

Look for port **80 (HTTP)**.

---

### Step 4 – Start nginx (if not running)

```bash
sudo systemctl start nginx
```

---

### Step 5 – Check nginx port

```bash
ss -tuln | grep 80
```

👉 You should see port 80 active

---

### Step 6 – Check DNS

```bash
nslookup google.com
```

---

### Step 7 – Check routes

```bash
ip route
```

---

# 4️⃣ Mini Task (Important)

Do this:

1️⃣ Start nginx
2️⃣ Confirm port 80 is running
3️⃣ Ping any website
4️⃣ Check your IP

Commands to use:

* `ip a`
* `ping`
* `ss`
* `nslookup`

---

# 5️⃣ Real DevOps Example

If a website is not working:

Step 1:

```bash
ping website.com
```

Step 2:

```bash
ss -tuln | grep 80
```

Step 3:

```bash
systemctl status nginx
```

This is how DevOps engineers **troubleshoot production issues**.

---

# 6️⃣ Commands You Must Remember

* `ip a`
* `ping`
* `ss -tuln`
* `nslookup`
* `ip route`

---

# Tomorrow – Day 9

You will learn:

✔ Disk management
✔ `df`
✔ `du`
✔ `lsblk`
✔ Storage monitoring

This is important for:
👉 Servers running out of space (common real issue)

---

When ready, type:

**“Day 9 DevOps study”** 🚀
