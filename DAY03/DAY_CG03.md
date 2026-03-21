Good progress, **Jeevan** 👏. Linux permissions are **very important for Cloud and DevOps**, because servers must control **who can read, write, or execute files**. Today we learn **file permissions**.

---

# Day 3 – Linux File Permissions

## 1️⃣ Concept (25–30 min)

Every file in Linux has **3 permission types**:

| Permission | Meaning |
| ---------- | ------- |
| r          | Read    |
| w          | Write   |
| x          | Execute |

These permissions apply to **3 types of users**:

| User Type  | Meaning                     |
| ---------- | --------------------------- |
| Owner (u)  | Person who created the file |
| Group (g)  | Users in the same group     |
| Others (o) | Everyone else               |

Example permission:

```
-rwxr-xr--
```

Meaning:

Owner → read, write, execute
Group → read, execute
Others → read only

---

# 2️⃣ View File Permissions

Command:

```bash
ls -l
```

Example output:

```
-rw-r--r-- 1 ubuntu ubuntu 0 Mar 15 devops.txt
```

Breakdown:

```
-rw-r--r--
```

* `rw-` → owner
* `r--` → group
* `r--` → others

---

# 3️⃣ Change Permissions (chmod)

Command:

```bash
chmod permission filename
```

Example:

```bash
chmod 755 script.sh
```

Permission numbers:

| Number | Permission             |
| ------ | ---------------------- |
| 7      | read + write + execute |
| 6      | read + write           |
| 5      | read + execute         |
| 4      | read only              |

Example:

```bash
chmod 644 file.txt
```

Meaning:

Owner → read write
Group → read
Others → read

---

# 4️⃣ Change File Owner (chown)

Command:

```bash
sudo chown user file
```

Example:

```bash
sudo chown ubuntu devops.txt
```

This changes **file ownership**.

---

# 5️⃣ Make Script Executable

DevOps engineers run scripts often.

Example:

Create script.

```bash
touch script.sh
```

Add permission.

```bash
chmod +x script.sh
```

Run script.

```bash
./script.sh
```

---

# 6️⃣ Practice Lab (45–60 min)

Step 1 – Create folder

```bash
mkdir linux_day3
cd linux_day3
```

---

Step 2 – Create files

```bash
touch file1.txt file2.txt script.sh
```

---

Step 3 – Check permissions

```bash
ls -l
```

---

Step 4 – Change permissions

```bash
chmod 777 file1.txt
```

Check again:

```bash
ls -l
```

---

Step 5 – Change another permission

```bash
chmod 644 file2.txt
```

---

Step 6 – Make script executable

```bash
chmod +x script.sh
```

---

# 7️⃣ Mini Task (Important)

Do this:

1️⃣ Create file **deploy.sh**

```bash
touch deploy.sh
```

2️⃣ Make it executable

```bash
chmod +x deploy.sh
```

3️⃣ Add text

```bash
echo "Deploy script running" > deploy.sh
```

---

# 8️⃣ DevOps Real World Example

Example deployment script permission:

```
-rwxr-xr-x deploy.sh
```

This means:

Owner can run script
Others can execute but not modify

This protects **production servers**.

---

# 9️⃣ Commands You Must Remember Today

Important commands:

* `ls -l`
* `chmod`
* `chown`
* `chmod +x`

These are used in **server management and automation**.

---

# Tomorrow – Day 4

You will learn:

✔ Linux users and groups
✔ useradd
✔ groupadd
✔ passwd
✔ sudo

This is important for **server security and cloud access management**.

---

When ready, come tomorrow and type:

**“Day 4 DevOps study”** 🚀
