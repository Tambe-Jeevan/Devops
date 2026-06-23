Welcome to Day 54, Jeevan! You are making excellent progress in Month 3.

Yesterday, you used Ansible Ad-Hoc commands to check the status of your servers. However, Ad-Hoc commands are like typing raw Linux commands into a terminal—they are good for quick checks, but terrible for complex, repeatable automation.

If you need to install a web server, copy an HTML file, change firewall rules, and restart a service across 500 servers, you must write an **Ansible Playbook**.

Our micro-learning structure for today:

* 30 min → Concept (Idempotency & YAML)
* 60 min → Hands-on practice (Writing your first Playbook)
* 30 min → Small task (Executing the Playbook)

Let's begin Day 54.

---

### Day 54 – Ansible Playbooks & Idempotency 📜🅰️

#### 1️⃣ Concept (30 min)

An **Ansible Playbook** is a simple text file written in **YAML** (YAML Ain't Markup Language). It is incredibly easy to read because it uses plain English words to define tasks.

**The Golden Rule: Idempotency**
If you run a Bash script that says `mkdir /data` twice, the second time it will throw a red error: `File exists`. Bash is dumb; it just blindly executes commands.

Ansible Playbooks are **Idempotent**. This means you describe the *desired state* of the server.
You tell Ansible: *"Make sure Nginx is installed."*

* If Nginx is not installed, Ansible installs it.
* If Nginx is *already* installed, Ansible does absolutely nothing and reports "OK".

You can run an Ansible Playbook 10,000 times, and it will never break your server. It will only make changes if the server drifts from your desired state.

---

#### 2️⃣ Setup Environment (IMPORTANT)

Open your Ubuntu VirtualBox or Windows WSL terminal.
Navigate to your Ansible workspace from yesterday.

`cd ~/day53_ansible`

Ensure your `inventory.ini` file is still there by running `ls`.

---

#### 3️⃣ Writing the Playbook (Practice – 1 hour)

We are going to write a Playbook that fully configures a web server. It will:

1. Install Nginx.
2. Copy a custom HTML file to the server.
3. Ensure the Nginx service is running.

**Step 1: Create the HTML file**
First, we need a file to copy to the target servers.
`echo "<h1>Hello from Jeevan's Ansible Playbook!</h1>" > index.html`

**Step 2: Create the Playbook file**
Playbooks use the `.yml` or `.yaml` extension.
`nano setup_webserver.yml`

**Step 3: Write the YAML Code**
Type this exactly. YAML is extremely strict about spaces. Use exactly two spaces for each indentation level (never use the Tab key!).

```yaml
---
- name: Configure Web Servers
  hosts: webservers      # This targets the group in your inventory.ini
  become: yes            # This tells Ansible to use 'sudo' for these tasks

  tasks:
    - name: Ensure Nginx is installed (Ubuntu/Debian)
      apt:
        name: nginx
        state: present   # Idempotency: "Make sure it exists"

    - name: Deploy custom HTML file
      copy:
        src: ./index.html
        dest: /var/www/html/index.html
        owner: www-data
        group: www-data
        mode: '0644'

    - name: Ensure Nginx service is running
      service:
        name: nginx
        state: started   # Idempotency: "Make sure it is turned on"
        enabled: yes     # "Make sure it starts if the server reboots"

```

*(Save and exit: **Ctrl+O**, **Enter**, **Ctrl+X**)*

---

#### 4️⃣ Small Practice Task (30 min)

Let's execute the automation and witness idempotency in action.

1️⃣ **Run the Playbook (The First Time)**
To run a playbook, you use the `ansible-playbook` command and point it to your inventory and your YAML file. Since we need to install software (`become: yes`), it might ask for your local sudo password.

`ansible-playbook -i inventory.ini setup_webserver.yml -K`
*(The `-K` flag prompts you to enter your sudo password).*

Watch the output! You will see:

* **Gathering Facts:** Ansible logs in and learns everything about the server (OS, IP, RAM).
* **changed:** It will say "changed" for installing Nginx and copying the file, meaning it actively did work.
* **PLAY RECAP:** It will show `ok=4, changed=3`.

2️⃣ **Test the Web Server**
Open your browser or use curl to see if the playbook actually worked:
`curl localhost`
*(You should see "Hello from Jeevan's Ansible Playbook!")*

3️⃣ **Run the Playbook (The Second Time - Proving Idempotency)**
Run the exact same command again:
`ansible-playbook -i inventory.ini setup_webserver.yml -K`

*Look at the output this time!*
Notice that nothing says `changed`! Everything says `ok`.
Ansible logged in, checked if Nginx was installed (it was), checked if the file matched (it did), and checked if the service was running (it was). It made exactly **zero changes** to the system. This is the magic of safe, idempotent DevOps automation.

---

#### 5️⃣ What You Learned Today

You learned:

* Why **Idempotency** is the most important concept in Configuration Management.
* How to write an Ansible Playbook using YAML syntax.
* How to use the `become: yes` directive to escalate privileges to root (`sudo`).
* How to use specific Ansible Modules (`apt`, `copy`, `service`) instead of writing raw Bash commands.
* How to use `ansible-playbook -K` to execute the automation securely.
* How to prove that a playbook is safe to run multiple times without corrupting a server.

---

#### 6️⃣ Homework

Let's test Ansible's ability to fix configuration drift.
Manually break your web server by stopping the service:
`sudo systemctl stop nginx`

Now, run your playbook one more time:
`ansible-playbook -i inventory.ini setup_webserver.yml -K`

Watch the output! Ansible will see that the installation is `ok`, the file is `ok`, but the service state is `changed`. It detects that Nginx is stopped and automatically fixes it by starting it back up!

Tomorrow is Day 55. We dive into **Ansible Roles & Galaxy**. You will learn how to download pre-written enterprise automation playbooks so you don't have to write everything from scratch.