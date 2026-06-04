Welcome back, Jeevan! You are officially 40 days into your journey. Your consistency is what will make you a Senior Engineer.

In your Desktop Support experience, if a user's hard drive crashes or gets infected with ransomware, you probably have to re-image their machine or pull files from a backup server. If they didn't back up their data, they lose everything.

In the cloud, it is exactly the same. An EC2 server is just a virtual machine attached to a virtual hard drive called an **EBS Volume** (Elastic Block Store). If that server gets hacked or corrupted, you need a backup. In AWS, a hard drive backup is called a **Snapshot**.

Today, you are going to use Boto3 to automate the creation of these snapshots. More importantly, you will write a **Lifecycle Policy** to delete old backups, saving the company thousands of dollars.

Here is our breakdown for today:

* 30 min → Concept
* 60 min → Hands-on practice
* 30 min → Small task / revision

Let's begin Day 40.

### Day 40 – Automated AWS Backups & Lifecycle Management 💾☁️

## 1️⃣ Concept (30 min)

**The Cost of Forgetting:**
Taking a snapshot in AWS is easy. But storage costs money. If you back up a 100GB hard drive every single night, and you never delete the old backups, you will be paying for 3,000GB of storage by the end of the month!

A true DevOps engineer doesn't just create backups; they manage the *lifecycle*. We want to keep the last 7 days of backups and automatically delete anything older.

Before we write the script, play with this interactive simulator to see exactly why Lifecycle Policies are critical for cloud budgeting:

---

## 2️⃣ Setup Environment (IMPORTANT)

Open your Ubuntu VirtualBox OR your Windows WSL terminal.
Make sure your AWS credentials are still active.

**Step 1: Create your workspace**
`cd ~/day39_boto3`
*(We will stay in the same folder as yesterday since we are still using Boto3).*

**Step 2: Get a Target Volume ID**
To back up a hard drive, you need its ID.
If you have an EC2 instance running (or stopped) in Mumbai, go to the AWS Console -> EC2 -> Volumes, and copy the **Volume ID** (it looks like `vol-0123456789abcdef0`).
*(If you do not have one, just read through the code today so you understand the logic!)*

---

## 3️⃣ Writing the Backup Lifecycle Script (Practice – 1 hour)

We are going to write a Python script that does two things:

1. Creates a brand new snapshot of your server's hard drive.
2. Looks at all previous snapshots and deletes any that are older than 7 days.

**Step 1: Create the Python file**
`nano backup_manager.py`

**Step 2: Write the code**
Type this carefully. We are importing Python's `datetime` and `timedelta` modules to do "time math" (Current Date minus 7 Days).

```python
#!/usr/bin/env python3
import boto3
from datetime import datetime, timezone, timedelta

# Define our constants
REGION = 'ap-south-1'
VOLUME_ID = 'vol-YOUR_VOLUME_ID_HERE' # Paste your Volume ID here!
RETENTION_DAYS = 7

# Connect to AWS
ec2 = boto3.client('ec2', region_name=REGION)

print(f"--- Starting Backup Job for {VOLUME_ID} ---")

# 1. CREATE THE NEW BACKUP
print("1. Creating new snapshot...")
new_snap = ec2.create_snapshot(
    VolumeId=VOLUME_ID,
    Description=f"Automated daily backup for {VOLUME_ID}"
)
print(f"✅ Success! Created Snapshot: {new_snap['SnapshotId']}")

# 2. CLEAN UP OLD BACKUPS
print(f"\n2. Scanning for backups older than {RETENTION_DAYS} days...")

# Calculate the cutoff date (exactly 7 days ago from right now)
cutoff_date = datetime.now(timezone.utc) - timedelta(days=RETENTION_DAYS)

# Ask AWS for a list of ALL snapshots belonging to this specific volume
snapshots = ec2.describe_snapshots(
    Filters=[{'Name': 'volume-id', 'Values': [VOLUME_ID]}]
)['Snapshots']

deleted_count = 0

# Loop through the list and check the dates
for snap in snapshots:
    snap_time = snap['StartTime']
    snap_id = snap['SnapshotId']
    
    # If the snapshot is older than the cutoff date, delete it!
    if snap_time < cutoff_date:
        print(f"🗑️ Deleting old snapshot: {snap_id} (Created on: {snap_time.date()})")
        ec2.delete_snapshot(SnapshotId=snap_id)
        deleted_count += 1

if deleted_count == 0:
    print("✨ No old snapshots found to delete. Storage is optimized.")

print("--- Backup Job Complete ---")

```

*(Save and exit: **Ctrl+O**, **Enter**, **Ctrl+X**)*

**Step 3: Make it executable**
`chmod +x backup_manager.py`

---

## 4️⃣ Small Practice Task (30 min)

Let's execute the automation.

1️⃣ **Run the script**
`./backup_manager.py`

2️⃣ **Analyze the Output**
You should see it successfully create a new snapshot. Because this is the first time you ran it, the cleanup section will likely say `✨ No old snapshots found to delete`.

3️⃣ **Verify in the AWS Cloud**
Do not just trust the terminal. Go to your browser, log into the **AWS Management Console**, navigate to **EC2**, and click on **Snapshots** on the left menu.
You will see a brand new snapshot being created with your description "Automated daily backup"!

4️⃣ **The Final Automation**
Just like you did on Day 33, this script is useless if you have to type `./backup_manager.py` every day.
Open your Linux crontab:
`crontab -e`

Add this line to the bottom to run your Python backup script every night at 2:00 AM:
`0 2 * * * /usr/bin/python3 /home/ubuntu/day39_boto3/backup_manager.py >> /home/ubuntu/backup.log 2>&1`

---

## 5️⃣ What You Learned Today

You learned:

* Why cloud storage lifecycles are critical for managing company budgets.
* How to use Python's `timedelta` to calculate a cutoff date in the past.
* How to use Boto3 `create_snapshot()` to backup physical cloud hard drives.
* How to use Boto3 `describe_snapshots()` with a **Filter** to ensure you only look at snapshots for one specific volume.
* How to use Boto3 `delete_snapshot()` to clean up AWS infrastructure programmatically.

## 6️⃣ Homework

Go into the AWS Console and manually delete the snapshot you just created so you don't get charged a few pennies for leaving it there!

Tomorrow is Day 41. You have mastered cron (time-based automation). Tomorrow, we move to **Event-Based Automation**:

* Introduction to Webhooks.
* How to trigger a Python script not by a clock, but by a web request (e.g., triggering a script when a developer types a message in Slack!).