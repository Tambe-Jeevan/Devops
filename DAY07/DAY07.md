Great decision, Jeevan 👍. We will continue your 2 hours daily consistent study to become a Cloud / DevOps Engineer.

We will follow our daily micro-learning system:
Every day (2 hours):

* 30 min → Concept
* 60 min → Hands-on practice
* 30 min → Small task / revision

Today is a massive step. You are learning the tool that every single developer and DevOps engineer uses every day. 

### Day 7 – Introduction to Git (Version Control Foundation) 🐙

1️⃣ **Concept (30 min)**
Imagine you write a shell script. You save it as `script.sh`. The next day, you want to add a new feature, but you are afraid of breaking it. So, you copy it and name it `script_v2.sh`. Then `script_final.sh`. Then `script_really_final.sh`. 

In Technical Support, you might see users doing this with Word documents all the time!

**Git** stops this mess. Git is a **Version Control System**. It secretly watches your folder, records every single change you make to a file, and allows you to "time travel" back to any older version instantly. 

In DevOps, we treat *everything* as code (Infrastructure as Code). If you accidentally break a server configuration, Git lets you revert to yesterday's working configuration in one second.

**The 3 Stages of Git:**

1.  **Working Directory:** Where you are actively typing and editing files.
2.  **Staging Area:** A waiting room. You use `git add` to tell Git, "I am ready to save these specific files."
3.  **Local Repository:** The permanent database. You use `git commit` to permanently take a snapshot of the staging area.

2️⃣ **Setup Environment (IMPORTANT)**
Make sure your environment is ready:
* Open your Ubuntu VirtualBox OR your Windows WSL terminal.
* First, we need to install Git! Type:
`sudo apt update`
`sudo apt install git -y`

3️⃣ **Basic Git Commands (Practice – 1 hour)**
Open the terminal and practice these commands.

**Step 1: Introduce yourself to Git (Do this only once)**
Git needs to know who is making the changes.
`git config --global user.name "Jeevan"`
`git config --global user.email "jeevan@example.com"`

**Step 2: Initialize a Git Repository**
Go to any folder and turn on Git's "watching" feature:
`git init`

**Step 3: Check the Status**
This is your best friend. It tells you what files are changed, new, or ready to save.
`git status`

**Step 4: Add files to the Staging Area (The Waiting Room)**
To add one specific file: `git add filename.txt`
To add ALL changed files at once: `git add .` *(The dot means "everything here")*

**Step 5: Commit the files (Take the snapshot)**
You must always leave a message explaining what you did.
`git commit -m "Created my first backup script"`

**Step 6: View the History**
See a list of every snapshot you have ever taken:
`git log`

4️⃣ **Small Practice Task (30 min)**
Let's simulate a real DevOps scenario. Do this step by step:

1️⃣ Create a new folder for a project and go inside
`mkdir day7_git_project`
`cd day7_git_project`

2️⃣ Turn on Git in this folder
`git init`

3️⃣ Create a new configuration file
`echo "Server=AWS" > config.txt`

4️⃣ Check the status (Git will say config.txt is "untracked")
`git status`

5️⃣ Add the file to the staging area
`git add config.txt`

6️⃣ Commit the file permanently
`git commit -m "Added initial AWS server config"`

7️⃣ Make a change to the file
`echo "Database=MySQL" >> config.txt` *(Note: `>>` adds text to the end of a file)*

8️⃣ Add and Commit the new change
`git add .`
`git commit -m "Added MySQL database config"`

9️⃣ Check your Git history
`git log`
*(You should see your two separate commits with timestamps!)*

5️⃣ **What You Learned Today**
You learned:
✔ Why Version Control is mandatory in IT and DevOps.
✔ How to install and configure Git.
✔ The Git workflow: Modify -> Add -> Commit.
✔ How to check what is happening using `git status` and `git log`.

6️⃣ **Homework (Important)**
Practice the `git init`, `git add .`, and `git commit -m "message"` cycle 4 or 5 times with different files. Getting muscle memory for these three commands is crucial.

Commands you must remember today:
`git init`
`git status`
`git add .`
`git commit -m ""`
`git log`

Tomorrow – Day 8
Today everything was saved locally on your computer. Tomorrow you will learn:
✔ Introduction to GitHub (The Cloud for Git)
✔ Connecting your local Linux terminal to GitHub
✔ Pushing your code to the internet (`git push`)

Just come tomorrow and type:
**“Day 8 DevOps study”**
and I will continue your Cloud / DevOps Engineer training step by step 🚀