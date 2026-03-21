Nice consistency, **Jeevan** 👍. Today you will learn **Linux Users and Groups**, which is very important for **server access control in Cloud and DevOps environments**.

---

# Day 4 – Linux Users & Groups

## 1️⃣ Concept (25–30 min)

In Linux servers, **multiple people can access the same system** (developers, admins, DevOps engineers).
To control access, Linux uses **users and groups**.

Example in a company server:

| User  | Role                 |
| ----- | -------------------- |
| dev1  | Developer            |
| dev2  | Developer            |
| ops1  | DevOps Engineer      |
| admin | System Administrator |

Instead of giving permissions individually, we create **groups**.

Example groups:

* developers
* devops
* admin

Users are added to groups and permissions are managed easily.

This concept is used in cloud platforms like **Amazon Web Services** IAM user management.

---

# 2️⃣ Check Current User

Command:

```bash
whoami
```

This shows your logged-in username.

Example output:

```
ubuntu
```

---

# 3️⃣ Create a New User

Command:

```bash
sudo useradd username
```

Example:

```bash
sudo useradd devopsuser
```

---

# 4️⃣ Set Password for User

Command:

```bash
sudo passwd username
```

Example:

```bash
sudo passwd devopsuser
```

Linux will ask you to set a password.

---

# 5️⃣ Create a Group

Command:

```bash
sudo groupadd groupname
```

Example:

```bash
sudo groupadd developers
```

---

# 6️⃣ Add User to Group

Command:

```bash
sudo usermod -aG groupname username
```

Example:

```bash
sudo usermod -aG developers devopsuser
```

---

# 7️⃣ Check Groups of a User

Command:

```bash
groups username
```

Example:

```bash
groups devopsuser
```

Output example:

```
devopsuser developers
```

---

# 8️⃣ Switch User

Command:

```bash
su username
```

Example:

```bash
su devopsuser
```

Exit back to original user:

```bash
exit
```

---

# 9️⃣ What is `sudo`

`sudo` = **Superuser do**

It allows you to run commands with **administrator privileges**.

Example:

```bash
sudo apt update
```

Without `sudo`, normal users cannot install software.

---

# 10️⃣ Practice Lab (45–60 min)

Follow these steps carefully.

### Step 1 – Check your user

```bash
whoami
```

---

### Step 2 – Create a new user

```bash
sudo useradd devops
```

---

### Step 3 – Set password

```bash
sudo passwd devops
```

---

### Step 4 – Create group

```bash
sudo groupadd cloudteam
```

---

### Step 5 – Add user to group

```bash
sudo usermod -aG cloudteam devops
```

---

### Step 6 – Check groups

```bash
groups devops
```

---

### Step 7 – Switch user

```bash
su devops
```

Exit back:

```bash
exit
```

---

# 11️⃣ Mini Task (Important)

Create this structure:

Users:

* `dev1`
* `dev2`

Group:

* `developers`

Add both users to the **developers group**.

Commands you must use:

* `useradd`
* `groupadd`
* `usermod`
* `groups`

---

# 12️⃣ Why DevOps Engineers Use This

Example scenario:

Developers can only **read application files**, but **DevOps engineers can deploy code**.

Permissions are managed through **users and groups**.

This is similar to access management systems in **Microsoft Azure** and **Google Cloud Platform**.

---

# 13️⃣ Commands You Must Remember Today

Important commands:

* `whoami`
* `useradd`
* `passwd`
* `groupadd`
* `usermod`
* `groups`
* `su`
* `sudo`

---

# Tomorrow – Day 5

You will learn **Linux Process Management**, which is used to monitor applications running on servers.

Topics:

✔ Running processes
✔ `ps` command
✔ `top` command
✔ `kill` command
✔ Server monitoring basics

This is **very important for production servers in DevOps**.

---

When ready tomorrow, type:

**“Day 5 DevOps study”** 🚀
