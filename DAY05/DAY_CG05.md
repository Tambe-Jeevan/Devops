Great consistency, **Jeevan** 👏 — this is exactly how you build DevOps skills step by step.

Today’s topic is **very important in real jobs** because DevOps engineers constantly monitor running applications.

---

# Day 5 – Linux Process Management

## 1️⃣ Concept (25–30 min)

A **process** = any program running on your system.

Examples:

* Browser
* Nginx server
* Database
* Scripts

In DevOps, you must:

* Check running processes
* Monitor CPU & memory
* Stop or restart services

---

# 2️⃣ View Running Processes

## Basic command

```bash
ps
```

Shows current shell processes.

---

## Detailed view

```bash
ps -ef
```

This shows:

* Process ID (PID)
* User
* Running command

---

## Real-time monitoring (IMPORTANT)

```bash
top
```

This shows:

* CPU usage
* Memory usage
* Running processes live

👉 Press **q** to exit

---

## Better view (optional)

```bash
htop
```

If not installed:

```bash
sudo apt install htop
```

---

# 3️⃣ Kill a Process

Sometimes a program hangs or crashes.

## Kill using PID

```bash
kill PID
```

Example:

```bash
kill 1234
```

---

## Force kill

```bash
kill -9 PID
```

Use only if normal kill doesn’t work.

---

# 4️⃣ Find Process by Name

```bash
ps -ef | grep nginx
```

This is **very common in DevOps**.

---

# 5️⃣ Run Process in Background

```bash
sleep 100 &
```

This runs in background.

---

# 6️⃣ Bring Background Process to Foreground

```bash
fg
```

---

# 7️⃣ Practice Lab (45–60 min)

Follow step by step.

---

### Step 1 – Check processes

```bash
ps
```

---

### Step 2 – Detailed processes

```bash
ps -ef
```

---

### Step 3 – Open real-time monitor

```bash
top
```

Observe CPU & memory.

Press **q** to exit.

---

### Step 4 – Run background process

```bash
sleep 200 &
```

---

### Step 5 – Find process

```bash
ps -ef | grep sleep
```

---

### Step 6 – Kill process

```bash
kill <PID>
```

Replace `<PID>` with actual number.

---

### Step 7 – Force kill (if needed)

```bash
kill -9 <PID>
```

---

# 8️⃣ Mini Task (Important)

Do this:

1️⃣ Run a background process
2️⃣ Find it using `ps -ef | grep`
3️⃣ Kill it

---

# 9️⃣ Real DevOps Example

Imagine your server app is not working.

You will:

```bash
ps -ef | grep app
```

Then:

```bash
kill -9 PID
```

Then restart service.

This is daily work in **production environments**.

---

# 🔟 Commands You Must Remember

* `ps`
* `ps -ef`
* `top`
* `htop`
* `kill`
* `kill -9`
* `grep`
* `&`

---

# Tomorrow – Day 6

You will learn:

✔ Package management
✔ Install software (like nginx)
✔ Update system
✔ Remove packages

This is important because DevOps engineers install tools like:

* Docker
* Jenkins
* Kubernetes

---

When ready, type:

**“Day 6 DevOps study”** 🚀
