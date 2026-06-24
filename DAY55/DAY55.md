Welcome to Day 55, Jeevan!

Yesterday, you wrote a complete Ansible Playbook to configure an Nginx web server. It was clean and easy to read.

However, if you put the tasks to install Nginx, set up a MySQL database, configure a firewall, and install Python all into one single `setup_server.yml` file, that file will eventually become 1,000 lines long. It becomes impossible to manage.

Just like Terraform uses "Modules" to organize and reuse code, Ansible uses **Roles**.

Today, we learn how to break your playbooks into clean, reusable components, and we will explore **Ansible Galaxy**—the open-source marketplace where you can download enterprise-grade roles written by other DevOps engineers.

Our micro-learning structure for today:

* 30 min → Concept (Ansible Roles & Galaxy)
* 60 min → Hands-on practice (Creating a Role Structure)
* 30 min → Small task (Calling the Role)

Let's begin Day 55.

---

### Day 55 – Ansible Roles & Galaxy 📂🌌

#### 1️⃣ Concept (30 min)

**What is an Ansible Role?**
A Role is simply a standardized directory structure. Instead of putting everything in one file, you break it apart:

* `tasks/main.yml`: Only the actions to perform (e.g., install Nginx).
* `files/`: Static files to copy (e.g., your `index.html`).
* `vars/main.yml`: Variables used by the role.

**What is Ansible Galaxy?**
Why spend 4 hours writing a complex role to install and secure a PostgreSQL database when an expert has already written one?
**Ansible Galaxy** is a public repository (like Docker Hub or GitHub) where you can download pre-written roles. You just run a command, and the role drops into your project, ready to use.

---

#### 2️⃣ Setup Environment (IMPORTANT)

Open your Ubuntu VirtualBox or Windows WSL terminal.
Navigate to your Ansible workspace.

`cd ~/day53_ansible`

---

#### 3️⃣ Building and Refactoring into a Role (Practice – 1 hour)

We are going to take your Nginx playbook from yesterday and convert it into a professional Ansible Role.

**Step 1: Create the Role Scaffold**
Ansible has a built-in command called `ansible-galaxy` that will automatically generate the correct folder structure for a new role. Let's create a role named `nginx_web`.

Run this command:
`ansible-galaxy init roles/nginx_web`

*Look at what it built!*
`ls -R roles/nginx_web`
You will see it created standard folders like `tasks`, `handlers`, `vars`, `defaults`, and `meta`.

**Step 2: Move the HTML File**
Move your `index.html` file from yesterday into the role's `files` directory. This keeps everything related to the web server packaged tightly together.
`mv index.html roles/nginx_web/files/`

**Step 3: Write the Tasks**
Now, we take the three specific tasks from yesterday's playbook and place them inside the role's `tasks/main.yml` file.

`nano roles/nginx_web/tasks/main.yml`

*Delete the placeholder text and paste this:*

```yaml
---
# tasks file for nginx_web

- name: Ensure Nginx is installed
  apt:
    name: nginx
    state: present

- name: Deploy custom HTML file
  copy:
    src: index.html   # Notice we don't need the path! Ansible automatically looks in the 'files' folder.
    dest: /var/www/html/index.html
    owner: www-data
    group: www-data
    mode: '0644'

- name: Ensure Nginx service is running
  service:
    name: nginx
    state: started
    enabled: yes

```

*(Save and exit)*

---

#### 4️⃣ Small Practice Task (30 min)

Your role is packaged and ready. Now, we just need a master playbook to call it.

1️⃣ **Create the Master Playbook**
Go back to your main project folder.
`cd ~/day53_ansible`

We will create a very clean, simple playbook named `site.yml` (the industry standard name for a master playbook).
`nano site.yml`

Type this code. Look how incredibly clean this is!

```yaml
---
- name: Configure Production Web Servers
  hosts: webservers
  become: yes

  roles:
    - nginx_web

```

*(Save and exit)*

2️⃣ **Execute the Master Playbook**
Run the playbook exactly as you did yesterday:
`ansible-playbook -i inventory.ini site.yml -K`
*(Enter your sudo password when prompted).*

Watch the execution! Ansible will read `site.yml`, see the `roles:` block, automatically navigate into `roles/nginx_web/tasks/main.yml`, and execute the Nginx configuration perfectly.

Because we moved `index.html` into the role's `files` folder, the `copy` module found it automatically without needing a long file path.

---

#### 5️⃣ What You Learned Today

You learned:

* Why monolithic playbooks become unmanageable and how **Roles** solve this problem.
* How to use the `ansible-galaxy init` command to automatically generate the standard role directory scaffold.
* How Ansible implicitly knows to look inside a role's `files/` directory when using the `copy` module.
* How to refactor raw tasks into a reusable role.
* How to write a clean master playbook (`site.yml`) that simply invokes roles.

---

#### 6️⃣ Homework

Go to [galaxy.ansible.com](https://galaxy.ansible.com/) in your web browser.
In the search bar, type `docker`. Look at how many pre-written roles exist just to install Docker!

If you wanted to download one of these, you would simply run `ansible-galaxy install geerlingguy.docker` in your terminal, and you would instantly have a professional Docker installation role added to your project.

Tomorrow is Day 56. We tackle one of the most powerful concepts in Ansible: **Dynamic Variables & Jinja2 Templates**. You will learn how to inject unique server IP addresses and custom configurations directly into files dynamically while Ansible is running.