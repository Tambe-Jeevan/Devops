Good consistency, **Jeevan** 👍. If you continue like this **daily for 6–8 months**, you can realistically move toward **Cloud / DevOps roles**.
Today we continue with **Day 2**.

---

# Day 2 – Linux File Management (Important for DevOps)

## 1️⃣ Concept (20–30 min)

Yesterday you learned:

* create folders
* create files
* navigate directories

Today you will learn **file management**, which every **Linux / Cloud server admin** uses daily.

Important operations:

* Copy files
* Move files
* Delete files
* View file content

These are used when managing **logs, configuration files, deployments, and scripts**.

---

# 2️⃣ Commands to Learn (Practice – 60 min)

## Copy Files

Command:

```bash
cp source destination
```

Example:

```bash
cp file1.txt file2.txt
```

This creates a **copy of file1.txt** named **file2.txt**.

---

## Copy File to Another Folder

Example:

```bash
cp file1.txt /home/ubuntu/devops
```

---

## Copy Folder

To copy a folder you must use **-r (recursive)**.

```bash
cp -r folder1 folder2
```

---

# Move Files

Move = cut + paste.

```bash
mv file1.txt newfile.txt
```

This **renames the file**.

Move file to another directory:

```bash
mv file1.txt /home/ubuntu/devops
```

---

# Delete Files

Remove file:

```bash
rm file1.txt
```

Remove folder:

```bash
rm -r foldername
```

⚠ Be careful: Linux **does not have recycle bin**.

---

# View File Content

### Show entire file

```bash
cat file1.txt
```

---

### View file page by page

```bash
less file1.txt
```

Press **q** to exit.

---

### View first lines

```bash
head file1.txt
```

---

### View last lines

```bash
tail file1.txt
```

This is very important for **reading logs in DevOps**.

---

# 3️⃣ Practice Lab (30 min)

Do this step by step.

### Step 1

Create practice folder.

```bash
mkdir linux_day2
cd linux_day2
```

---

### Step 2

Create files.

```bash
touch devops.txt cloud.txt aws.txt
```

Check files.

```bash
ls
```

---

### Step 3

Copy file.

```bash
cp devops.txt devops_copy.txt
```

---

### Step 4

Rename file.

```bash
mv cloud.txt cloud_notes.txt
```

---

### Step 5

Delete file.

```bash
rm aws.txt
```

---

### Step 6

Add text inside file.

```bash
echo "Learning DevOps" > devops.txt
```

View file.

```bash
cat devops.txt
```

---

# 4️⃣ Mini Task (Important)

Create this structure:

```
devops_study
   linux
   cloud
   docker
```

Commands you must use:

* mkdir
* mv
* cp
* rm
* ls

---

# 5️⃣ Commands You Must Remember

Important commands today:

* `cp`
* `mv`
* `rm`
* `cat`
* `head`
* `tail`
* `less`

These are used daily by **Linux admins and DevOps engineers**.

---

# 6️⃣ Small DevOps Insight

In real DevOps work, you often run commands like:

```
tail -f application.log
```

This shows **live logs of an application**.

You will learn this later when working with **servers and deployments**.

---

# Tomorrow – Day 3

You will learn **VERY IMPORTANT Linux concept**:

✔ File permissions
✔ chmod
✔ chown
✔ rwx permissions
✔ Why servers restrict access

This is **critical for cloud security**.

---

When you finish practice, come tomorrow and type:

**“Day 3 DevOps study”** 🚀
