Great decision, Jeevan 👍. We will continue your 2 hours daily consistent study to become a Cloud / DevOps Engineer.

We will follow our daily micro-learning system:
Every day (2 hours):

* 30 min → Concept
* 60 min → Hands-on practice
* 30 min → Small task / revision

Today we move forward with Day 5.

### Day 5 – Installing Software & Managing Services (DevOps Foundation)

1️⃣ **Concept (30 min)**
When installing applications in Windows, you usually download a `.exe` file from a website and click "Next, Next, Install". You also manage background processes using the "Windows Services" menu.

In the DevOps and Linux world, you do all of this directly from the command line.

* **Package Management (`apt`):** Ubuntu Linux uses a tool called `apt` (Advanced Package Tool). It connects to official servers, downloads the software you want securely, and installs it automatically. 

* **Service Management (`systemctl`):** When you install a server application (like a database or a web server), it needs to run constantly in the background. These background programs are called "Services" (or Daemons in Linux). You manage them using a powerful command called `systemctl`.


2️⃣ **Setup Environment (IMPORTANT)**
Make sure your environment is ready:
* Open your Ubuntu VirtualBox OR your Windows WSL terminal.
* Type `cd ~` to ensure you are in your home folder.

3️⃣ **Installing & Managing Commands (Practice – 1 hour)**
Open the terminal and practice these commands. (Remember, installing software requires `sudo` for administrator rights).

**Update your software list (Always do this first!):**
`sudo apt update`
*(This does not install new software; it just downloads the latest catalog of available software).*

**Install a package (Let's install 'nginx', a very popular web server):**
`sudo apt install nginx -y`
*(The `-y` automatically says "yes" to any confirmation prompts).*

**Check the status of a service:**
`sudo systemctl status nginx`
*(Press 'q' to exit the status screen).*

**Stop a running service:**
`sudo systemctl stop nginx`

**Start a service:**
`sudo systemctl start nginx`

**Restart a service (Very useful when you change a configuration file):**
`sudo systemctl restart nginx`

**Enable a service to start automatically when the computer reboots:**
`sudo systemctl enable nginx`

4️⃣ **Small Practice Task (30 min)**
Do this step by step:

1️⃣ Update your server's package list
`sudo apt update`

2️⃣ Install the Nginx web server
`sudo apt install nginx -y`

3️⃣ Check if Nginx is running properly
`sudo systemctl status nginx`

4️⃣ Test the web server locally using the `curl` command you learned yesterday
`curl localhost`
*(If successful, you will see a bunch of HTML code that says "Welcome to nginx!")*

5️⃣ Stop the web server
`sudo systemctl stop nginx`

6️⃣ Try testing it again
`curl localhost`
*(This time, it should fail because you stopped the service!)*

5️⃣ **What You Learned Today**
You learned:
✔ How to update the system's software registry (`apt update`).
✔ How to safely install new software via the terminal (`apt install`).
✔ How to control background processes (`systemctl start/stop/restart`).
✔ How to verify a service is actually running (`systemctl status`).

6️⃣ **Homework (Important)**
Practice managing services. Start and stop Nginx multiple times and use `curl localhost` to see the immediate effect. DevOps engineers do this every day when deploying new website code!

Commands you must remember today:
`apt update`
`apt install`
`systemctl status`
`systemctl restart`

Tomorrow – Day 6
You will learn:
✔ Introduction to Shell Scripting (Your first step into Automation!)
✔ Writing your first `.sh` file
✔ Running a script to automate tasks

Just come tomorrow and type:
**“Day 6 DevOps study”**
and I will continue your Cloud / DevOps Engineer training step by step 🚀