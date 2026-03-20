Great decision, Jeevan 👍. We will continue your 2 hours daily consistent study to become a Cloud / DevOps Engineer.

We will follow our daily micro-learning system:
Every day (2 hours):

* 30 min → Concept
* 60 min → Hands-on practice
* 30 min → Small task / revision

Today is a very exciting day. You are moving from doing things manually to **Automating** them. Today we move forward with Day 6.

### Day 6 – Introduction to Shell Scripting (The Bridge to Automation) ⚙️

1️⃣ **Concept (30 min)**
In your Technical Support role, you might have to check an IP address, restart a service, and ping a server one by one. 

What if you could do all three things by typing just *one* word? That is **Shell Scripting**.

A shell script is simply a text file containing a list of Linux commands. When you run the file, the server reads the commands from top to bottom and executes them automatically. This is the absolute core of DevOps automation.


**The Shebang (`#!/bin/bash`):**
Every bash script starts with this exact line at the very top. It tells the Linux system, *"Please use the Bash program to read and run the commands in this file."*

2️⃣ **Setup Environment (IMPORTANT)**
Make sure your environment is ready:
* Open your Ubuntu VirtualBox OR your Windows WSL terminal.
* Type `cd ~` to ensure you are in your home folder.

3️⃣ **Writing Your First Script (Practice – 1 hour)**
To write a script, we need a text editor inside the terminal. We will use a very simple one called `nano`. 

Follow these steps exactly in your terminal:

**Step 1: Open the nano text editor and create a file**
`nano my_first_script.sh`
*(The screen will change. You are now inside the text editor).*

**Step 2: Type your script**
Carefully type these exact lines:
```bash
#!/bin/bash
echo "Hello, Jeevan! Welcome to DevOps Day 6."
echo "Your current directory is:"
pwd
echo "Your IP address is:"
ip a | grep inet
```
*(Note: `echo` just prints text to the screen).*

**Step 3: Save and Exit nano (Crucial Step)**
1. Press **Ctrl + O** (the letter O, not zero) to save.
2. Press **Enter** to confirm the file name.
3. Press **Ctrl + X** to exit the editor and go back to the normal terminal.

**Step 4: Make the script executable**
By default, Linux creates files as standard text, not runnable programs. We must give it the "Execute" permission (Remember Day 3!).
`chmod +x my_first_script.sh`

**Step 5: Run your script!**
To run a script in your current folder, you must put `./` in front of it.
`./my_first_script.sh`

4️⃣ **Small Practice Task (30 min)**
Let's create a real-world "Backup Script". Do this step by step:

1️⃣ Create a folder for today and go inside
`mkdir day6_automation`
`cd day6_automation`

2️⃣ Create a fake folder that we want to back up
`mkdir important_data`
`touch important_data/system_config.txt`

3️⃣ Create the backup script using nano
`nano backup.sh`

4️⃣ Write the automation code inside nano:
```bash
#!/bin/bash
echo "Starting the backup process..."
cp -r important_data backup_data
echo "Backup is complete! Here are your current files:"
ls -l
```
*(Save and exit: Ctrl+O, Enter, Ctrl+X)*

5️⃣ Make it executable
`chmod +x backup.sh`

6️⃣ Run the backup script
`./backup.sh`
*(You should see it automatically copy the folder and list the files!)*

5️⃣ **What You Learned Today**
You learned:
✔ What a Shell Script is and why DevOps uses it for automation.
✔ How to use the `nano` terminal text editor.
✔ The importance of the `#!/bin/bash` header.
✔ How to make a file executable using `chmod +x`.
✔ How to run a script using `./`.

6️⃣ **Homework (Important)**
Practice using `nano` and writing scripts.
Try writing a script called `system_check.sh` that runs the `whoami` command and the `ping -c 3 google.com` command automatically. 

Commands you must remember today:
`nano`
`chmod +x`
`./scriptname.sh`

Tomorrow – Day 7
You will learn:
✔ Introduction to Git (Version Control)
✔ Why developers and DevOps engineers use Git
✔ `git init`, `git add`, `git commit`

Just come tomorrow and type:
**“Day 7 DevOps study”**
and I will continue your Cloud / DevOps Engineer training step by step 🚀