Great decision, Jeevan 👍. We will continue your 2 hours daily consistent study to become a Cloud / DevOps Engineer.

We will follow the exact daily micro-learning system you prefer:
Every day (2 hours):

* 30 min → Concept
* 60 min → Hands-on practice
* 30 min → Small task / revision

Today we move forward with Day 2.

### Day 2 – Linux File Management (DevOps Foundation)

1️⃣ **Concept (30 min)**
In DevOps, you constantly move, copy, and read configuration files or server logs. Since cloud servers have no graphical interface, you must do this via the terminal.

Why file management is critical for DevOps:
* Deploying code (copying files from a repository to a server)
* Reading error logs to troubleshoot (just like finding a VPN or ServiceNow error, but via text)
* Organizing server configurations

Typical Tech Support to DevOps mindset:
Instead of double-clicking to open a log file to find why an application crashed, you will use terminal commands to read the exact line of the error instantly.

2️⃣ **Setup Environment (IMPORTANT)**
Make sure your environment from Day 1 is ready:
* Open your Ubuntu VirtualBox OR your Windows WSL terminal.
* Make sure you are in your home directory (type `cd ~`).

3️⃣ **Advanced Linux Commands (Practice – 1 hour)**
Open the terminal and practice these file management commands.

Copy a file
`cp source.txt destination.txt`

Copy a whole folder (and its contents)
`cp -r source_folder destination_folder`

Move or Rename a file
`mv oldname.txt newname.txt`
*(Note: `mv` is used for both moving files to a new folder AND renaming them!)*

Delete a file
`rm unwanted_file.txt`

Delete a folder (and everything inside it)
`rm -r unwanted_folder`

View whole file content
`cat system.log`

View file content page by page (for long files)
`less system.log`
*(Press 'q' to quit)*

View the first 10 lines of a file
`head system.log`

View the last 10 lines of a file (Great for live logs!)
`tail system.log`

4️⃣ **Small Practice Task (30 min)**
Do this step by step:

1️⃣ Create a new folder
`mkdir day2_practice`

2️⃣ Enter the folder
`cd day2_practice`

3️⃣ Create a file and add some text
`echo "This is my first config file" > config.txt`

4️⃣ Copy the file
`cp config.txt backup_config.txt`

5️⃣ Rename the original file
`mv config.txt app_config.txt`

6️⃣ Read the copied file
`cat backup_config.txt`

7️⃣ Delete the copied file
`rm backup_config.txt`

5️⃣ **What You Learned Today**
You learned:
✔ Copying files and directories (`cp`)
✔ Moving and renaming files (`mv`)
✔ Safely deleting files and folders (`rm`)
✔ Reading file contents efficiently (`cat`, `less`, `head`, `tail`)

These are daily tasks for any Linux Administrator or DevOps Engineer.

6️⃣ **Homework (Important)**
Practice these commands 10–15 times.

Try this real-world scenario:
* Create a folder called `web_server`.
* Inside it, create a file named `index.html`.
* Copy `index.html` to a new file named `index_backup.html`.
* Create a folder named `old_backups` inside `web_server`.
* Move `index_backup.html` into the `old_backups` folder.

Commands you must remember today:
`cp`
`mv`
`rm`
`cat`
`tail`

Tomorrow – Day 3
You will learn:
✔ User and Group Management
✔ File Permissions (`chmod`, `chown`)
✔ Why permissions are important for server security

Just come tomorrow and type:
**“Day 3 DevOps study”**
and I will continue your Cloud / DevOps Engineer training step by step 🚀