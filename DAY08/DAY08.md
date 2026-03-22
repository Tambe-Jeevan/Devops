Great decision, Jeevan 👍. We will continue your 2 hours daily consistent study to become a Cloud / DevOps Engineer.

We will follow our daily micro-learning system:
Every day (2 hours):

* 30 min → Concept
* 60 min → Hands-on practice
* 30 min → Small task / revision

Today we move forward with Day 8. You have mastered tracking changes on your own computer. Now, it is time to put your work on the internet.

### Day 8 – Introduction to GitHub (Pushing Code to the Cloud) ☁️🐙

1️⃣ **Concept (30 min)**
Yesterday, you learned **Git**. Git lives locally on your hard drive. But what if your laptop breaks? Or what if you need to work with 5 other DevOps engineers on the same project?

This is where **GitHub** comes in. 

* **Git** is the command-line tool that tracks your changes.
* **GitHub** is a cloud website (owned by Microsoft) that hosts your Git repositories on the internet. 



Think of it like this for a typical desktop support scenario: **Git** is like saving a Word document securely on your local `C:\` drive with version history. **GitHub** is like uploading that document to OneDrive or Google Drive so your whole team can view it, download it, and collaborate on it. 

In DevOps, GitHub is the ultimate trigger. Later in your journey, you will set up automations so that the moment you upload (push) code to GitHub, a server automatically builds and deploys a website!

2️⃣ **Setup Environment (IMPORTANT)**
You need two things ready today:
1. Open your web browser and go to **github.com**. Create a free account if you do not have one. 
2. Open your Ubuntu VirtualBox OR your Windows WSL terminal.

3️⃣ **Connecting Local to Cloud (Practice – 1 hour)**
Open the terminal and practice these steps. We are going to link your local folder to the internet.

**Step 1: Create a Repository on GitHub (In your browser)**
1. Log in to GitHub.com.
2. Click the `+` icon in the top right corner and select **New repository**.
3. Name it `devops-day8`.
4. Leave it as "Public" and do NOT check "Add a README file". 
5. Click **Create repository**.
*(GitHub will now show you a page with some commands. Leave this page open!)*

**Step 2: Prepare your local code (In your terminal)**
Let's create something to upload.
`mkdir devops-day8`
`cd devops-day8`
`git init`
`echo "This is my first cloud repository" > readme.md`
`git add .`
`git commit -m "Initial commit"`

**Step 3: Link your local folder to GitHub**
Go back to your browser and copy the URL of your new GitHub repository (it looks like `https://github.com/yourusername/devops-day8.git`). Then run this command in your terminal:
`git remote add origin https://github.com/yourusername/devops-day8.git`
*(This tells your local Git: "I am adding a remote cloud location called 'origin' at this URL.")*

**Step 4: Rename your main branch**
Modern Git uses 'main' as the default branch name. 
`git branch -M main`

**Step 5: Push your code to the Cloud!**
This is the magic command. It uploads your local snapshots to GitHub.
`git push -u origin main`

*(Note: When you run this, a browser window might pop up asking you to sign in to GitHub to authorize your terminal. If you are on standard Ubuntu, it might ask for a username and password. GitHub no longer accepts account passwords in the terminal—you have to use a "Personal Access Token" instead, which you can generate in GitHub Settings -> Developer Settings).*

4️⃣ **Small Practice Task (30 min)**
Let's do a full end-to-end update. Imagine a developer asked you to update the server configuration file and push the changes for the team.

1️⃣ In your `devops-day8` folder, create a new file:
`echo "Server: Nginx, OS: Ubuntu" > server_config.txt`

2️⃣ Check the status to see the new file
`git status`

3️⃣ Add the file to the staging area
`git add server_config.txt`

4️⃣ Commit the file locally
`git commit -m "Added Nginx server configuration"`

5️⃣ Push the new commit to GitHub
`git push`
*(You don't need `-u origin main` anymore, Git remembers it!)*

6️⃣ Open GitHub.com in your browser, refresh the page, and look at your files! You should see `server_config.txt` right there on the internet.

5️⃣ **What You Learned Today**
You learned:
✔ The critical difference between Git (local) and GitHub (cloud).
✔ How to create a remote repository on GitHub.com.
✔ How to link your local machine to the cloud (`git remote add origin`).
✔ How to upload your code to the internet (`git push`).

6️⃣ **Homework (Important)**
Create one more repository on GitHub called `tech-support-scripts`. Create a local folder with the same name, write a tiny `.sh` script inside it (like the ones from Day 6), commit it, and push it to GitHub. 

Commands you must remember today:
`git remote add origin <url>`
`git push`

Tomorrow – Day 9
Today you pushed code *up* to the cloud. Tomorrow you will learn:
✔ Downloading code *down* from the cloud (`git clone`)
✔ Pulling updates when a teammate changes a file (`git pull`)
✔ Working with open-source projects

Just come tomorrow and type:
**“Day 9 DevOps study”**
and I will continue your Cloud / DevOps Engineer training step by step 🚀