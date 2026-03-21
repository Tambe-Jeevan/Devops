Great decision, Jeevan 👍. We will continue your 2 hours daily consistent study to become a Cloud / DevOps Engineer.

We will follow our daily micro-learning system:
Every day (2 hours):

* 30 min → Concept
* 60 min → Hands-on practice
* 30 min → Small task / revision

Today we move forward with Day 4.

### Day 4 – Linux Networking Basics (DevOps Foundation)

1️⃣ **Concept (30 min)**
Troubleshooting VPNs and internet connectivity involves understanding IP addresses, DNS, and routing. In the Cloud and DevOps world, networking is just as critical. Servers need to communicate with each other constantly—for example, a web server hosting a React frontend needs to securely talk to a database server.



Because Linux cloud servers do not have web browsers like Chrome or Edge, you cannot just "open a webpage" to test if the internet is working or to download a software installer. You must do all network testing and downloading directly through the command line.

2️⃣ **Setup Environment (IMPORTANT)**
Make sure your environment is ready:
* Open your Ubuntu VirtualBox OR your Windows WSL terminal.
* Type `cd ~` to ensure you are in your home folder.

3️⃣ **Basic Networking Commands (Practice – 1 hour)**
Open the terminal and practice these commands.

**Check your server's IP address:**
`ip a`
*(Look for a number like 192.168.x.x or 10.x.x.x next to "inet")*

**Test your internet connection (Ping):**
`ping google.com`
*(Important: In Linux, ping runs forever! You MUST press **Ctrl + C** on your keyboard to stop it).*

**Test connection for a specific number of times (e.g., 4 times):**
`ping -c 4 google.com`

**Download a file directly from the internet:**
`wget https://raw.githubusercontent.com/docker/awesome-compose/master/README.md`
*(This command fetches the file from that URL and saves it to your current folder).*

**Read a webpage's raw code without a browser:**
`curl https://example.com`
*(This prints the HTML code of the website directly into your terminal. DevOps engineers use this to check if an API or web app is responding correctly).*

4️⃣ **Small Practice Task (30 min)**
Do this step by step:

1️⃣ Create a new folder for today
`mkdir day4_network`

2️⃣ Go inside the folder
`cd day4_network`

3️⃣ Check your IP address
`ip a`

4️⃣ Ping a known website to verify your server has internet access
`ping -c 3 amazon.com`

5️⃣ Download a sample web page using `wget`
`wget https://example.com`

6️⃣ Check that the file downloaded successfully
`ls -l`
*(You should see a file named `index.html`)*

7️⃣ Read the downloaded file
`cat index.html`

5️⃣ **What You Learned Today**
You learned:
✔ How to check a Linux machine's IP address (`ip a`).
✔ How to test network connectivity and DNS resolution (`ping`).
✔ How to download files from the internet without a browser (`wget`).
✔ How to test web server responses via the terminal (`curl`).

These are essential skills for setting up cloud servers and troubleshooting network traffic.

6️⃣ **Homework (Important)**
Practice the `ping` and `curl` commands.

Try this real-world scenario:
* Use `curl` to fetch the weather for your current city directly in the terminal by typing exactly this: `curl wttr.in`
* Notice how it instantly retrieves data from an external server and displays it in your command line!

Commands you must remember today:
`ip a`
`ping`
`wget`
`curl`
`Ctrl + C` (to stop a running process)

Tomorrow – Day 5
You will learn:
✔ Package Management (How to install software on Linux)
✔ System Updates (`apt update`)
✔ Managing background services (`systemctl`)

Just come tomorrow and type:
**“Day 5 DevOps study”**
and I will continue your Cloud / DevOps Engineer training step by step 🚀