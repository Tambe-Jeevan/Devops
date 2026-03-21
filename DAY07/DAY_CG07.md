Excellent work, **Jeevan** 👏 — you’ve completed **1 full week of Linux**, which is a strong foundation for DevOps.

Today’s topic is **VERY IMPORTANT in real jobs** 👉 **Logs & Debugging**.
DevOps engineers spend a lot of time reading logs to fix issues.

---

# Day 7 – Linux Logs & Monitoring

## 1️⃣ Concept (25–30 min)

Logs = **records of system and application activities**

Examples:

* Server started
* Error occurred
* User login
* Application crash

Logs help you:

* Debug issues
* Monitor systems
* Understand failures

---

## Where Logs Are Stored

Most logs are stored in:

```bash
/var/log
```

This folder contains system logs.

---

# 2️⃣ Important Log Files

Go to log directory:

```bash
cd /var/log
ls
```

Important files:

* `syslog` → system logs
* `auth.log` → login/authentication
* `kern.log` → kernel logs
* `dpkg.log` → package installs

---

# 3️⃣ View Logs

## View full log

```bash
cat /var/log/syslog
```

---

## Scroll log (recommended)

```bash
less /var/log/syslog
```

Press **q** to exit.

---

## View last lines (VERY IMPORTANT)

```bash
tail /var/log/syslog
```

---

## Live logs (REAL DEVOPS USE 🔥)

```bash
tail -f /var/log/syslog
```

This shows logs in **real time**.

👉 Press **Ctrl + C** to stop

---

# 4️⃣ journalctl (System Logs)

Modern Linux systems use **systemd logs**.

```bash
journalctl
```

---

## Recent logs

```bash
journalctl -n 50
```

---

## Logs for specific service

Example:

```bash
journalctl -u nginx
```

---

# 5️⃣ Check Logs for Nginx

After installing nginx (Day 6), check logs:

```bash
cd /var/log/nginx
ls
```

Files:

* `access.log`
* `error.log`

View:

```bash
tail -f /var/log/nginx/error.log
```

---

# 6️⃣ Practice Lab (45–60 min)

Follow step by step.

---

### Step 1 – Go to logs

```bash
cd /var/log
ls
```

---

### Step 2 – View system log

```bash
less syslog
```

---

### Step 3 – View last lines

```bash
tail syslog
```

---

### Step 4 – Live logs

```bash
tail -f syslog
```

Stop with **Ctrl + C**

---

### Step 5 – Use journalctl

```bash
journalctl -n 20
```

---

### Step 6 – Check nginx logs

```bash
cd /var/log/nginx
ls
```

```bash
tail -f access.log
```

---

# 7️⃣ Mini Task (Important)

Do this:

1️⃣ Open nginx in browser
👉 `http://localhost`

2️⃣ Run:

```bash
tail -f /var/log/nginx/access.log
```

👉 You will see **live request logs** 🔥

---

# 8️⃣ Real DevOps Example

If your app fails:

You check logs:

```bash
tail -f /var/log/app.log
```

or

```bash
journalctl -u app
```

This is **daily work of DevOps engineers**.

---

# 9️⃣ Commands You Must Remember

* `cd /var/log`
* `cat`
* `less`
* `tail`
* `tail -f`
* `journalctl`
* `journalctl -u`

---

# 🎉 Week 1 Completed!

You now know:

✔ Linux basics
✔ File management
✔ Permissions
✔ Users & groups
✔ Processes
✔ Package management
✔ Logs

👉 This is a **strong DevOps foundation**.

---

# Tomorrow – Day 8

We start **Advanced Linux + Networking Basics**

You will learn:

✔ Networking commands
✔ `ping`
✔ `ifconfig` / `ip`
✔ `netstat`
✔ `ss`

This is **important for cloud & server communication**.

---

When ready, type:

**“Day 8 DevOps study”** 🚀
