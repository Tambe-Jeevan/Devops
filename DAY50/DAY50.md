Welcome to Day 50, Jeevan! You have reached a massive milestone. Today marks the conclusion of Month 2.

In Month 1, you learned how to use infrastructure tools (Linux, Docker, Terraform, Kubernetes).
In Month 2, you learned how to *control* those tools programmatically using Scripting (Python, Bash) and Advanced CI/CD (Jenkins, Webhooks).

Today is the **Month 2 Capstone Project**. We are not learning any new syntax today. Instead, you are going to combine Bash, Python, AWS Boto3, JSON parsing, and Cron into one massive, automated **Cloud Auto-Remediation System**.

If you can build this, you are officially writing code at the level of a Junior DevOps Engineer.

Our micro-learning structure for today:

* 30 min → Concept (The Capstone Architecture)
* 60 min → Hands-on practice (Building the Remediation Engine)
* 30 min → Small task (Testing the Automation Loop)

Let's conquer Day 50.

---

### Day 50 – Month 2 Capstone: The Cloud Auto-Remediation Engine ☁️🤖

#### 1️⃣ Concept (30 min)

Here is the exact architecture you are going to build today. This represents a real-world enterprise infrastructure monitoring workflow:

1. **The Monitor (Cron + Bash):** A Bash script runs continuously on a schedule. It scans a local server to see if a critical process (like `nginx`) has crashed.
2. **The Trigger (Bash -> Python):** If the Bash script detects a crash, it doesn't just restart the service. It triggers a secondary Python script.
3. **The API Action (Python + Boto3):** The Python script uses the AWS SDK to find the EC2 instance in the cloud and issues a hard hardware reboot (`reboot_instances`) to fix the underlying issue.
4. **The Audit (Python -> JSON):** Finally, Python writes a structured JSON log of the entire incident so the security team has a permanent record.

---

#### 2️⃣ Setup Environment (IMPORTANT)

Open your Ubuntu VirtualBox or your Windows WSL terminal.
We need a clean directory for your Capstone project.

`cd ~`
`mkdir day50_capstone`
`cd day50_capstone`

You will also need a dummy EC2 Instance ID for the Python script to target. Use `i-1234567890abcdef0` if you don't have a real one running.

---

#### 3️⃣ Building the Remediation Engine (Practice – 1 hour)

We are building two files today: the Bash Monitor and the Python API Engine.

**Step 1: Write the Python Engine (The Brains)**
We write the Python script first, because the Bash script needs to call it.
`nano aws_remediator.py`

Type this carefully. We are combining AWS Boto3 actions with JSON file writing.

```python
#!/usr/bin/env python3
import sys
import json
import boto3
from datetime import datetime

# Grab the service name passed from the Bash script (e.g., 'nginx')
if len(sys.argv) < 2:
    print("Error: Must provide the crashed service name.")
    sys.exit(1)

crashed_service = sys.argv[1]

# Constants
TARGET_INSTANCE = "i-1234567890abcdef0" # Replace with your real ID if you have one
REGION = "ap-south-1"
AUDIT_LOG = "/home/ubuntu/day50_capstone/incident_audit.json" # Change 'ubuntu' if needed

print(f"PYTHON ENGINE: Initializing remediation for crashed service: {crashed_service}...")

# 1. AWS Action: Reboot the Server
try:
    ec2 = boto3.client('ec2', region_name=REGION)
    print(f"PYTHON ENGINE: Sending hardware REBOOT command to {TARGET_INSTANCE}...")
    
    # Uncomment the line below to actually trigger AWS (if you have a real instance ID)
    # ec2.reboot_instances(InstanceIds=[TARGET_INSTANCE])
    
    status = "SUCCESS"
    action_taken = "EC2 Reboot Initiated"

except Exception as e:
    status = "FAILED"
    action_taken = str(e)

# 2. Audit Trail: Write to JSON
incident_data = {
    "timestamp": datetime.now().isoformat(),
    "incident_type": "Service Crash",
    "service_name": crashed_service,
    "target_server_id": TARGET_INSTANCE,
    "remediation_status": status,
    "action_taken": action_taken
}

# Append the JSON block to our audit file
with open(AUDIT_LOG, "a") as logfile:
    logfile.write(json.dumps(incident_data) + "\n")

print("PYTHON ENGINE: Remediation complete and JSON audit logged.")

```

*(Save and exit)*

**Step 2: Write the Bash Monitor (The Eyes)**
Now we write the Bash script that watches the system and triggers Python if things go wrong.
`nano system_monitor.sh`

```bash
#!/bin/bash

SERVICE="nginx"
PYTHON_SCRIPT="/home/ubuntu/day50_capstone/aws_remediator.py" # Change 'ubuntu' if needed

echo "--- Starting System Health Scan ---"

# Check if Nginx is active
if systemctl is-active --quiet $SERVICE; then
    echo "✅ [OK] $SERVICE is healthy."
else
    echo "🚨 [CRITICAL] $SERVICE has crashed!"
    echo "Triggering Python AWS Auto-Remediation..."
    
    # Execute the Python script and pass the service name as an argument
    /usr/bin/python3 $PYTHON_SCRIPT $SERVICE
fi

```

*(Save and exit)*

**Step 3: Make Both Executable**
`chmod +x aws_remediator.py`
`chmod +x system_monitor.sh`

---

#### 4️⃣ Small Practice Task (30 min)

Let's test the entire end-to-end flow.

1️⃣ **Ensure the Service is Running**
Make sure Nginx is healthy first:
`sudo systemctl start nginx`

Run your Bash monitor:
`./system_monitor.sh`
*(You should see the green `[OK]` message. The Python script is NOT triggered).*

2️⃣ **Break the System (The Chaos Test)**
Stop the web server to simulate a critical failure:
`sudo systemctl stop nginx`

3️⃣ **Run the Monitor Again**
`./system_monitor.sh`

*Watch the terminal closely!*
You will see Bash detect the crash and instantly print the red `[CRITICAL]` alert.
Then, Bash hands control over to Python. You will see the `PYTHON ENGINE:` outputs as it initializes, "sends" the reboot command to AWS, and logs the incident.

4️⃣ **Verify the JSON Audit**
Check that Python properly wrote the structured JSON log file:
`cat incident_audit.json`

You should see a perfectly formatted JSON string containing the exact timestamp, the service name (`nginx`), the target instance ID, and the status.

---

#### 5️⃣ Month 2 Completed! 🎉

Take a moment to realize what you just built. One month ago, you were just learning how to type `ls` and `cd`. Today, you wrote a multi-language, event-driven remediation engine that monitors local system states, executes cloud hardware commands via the AWS API, and generates machine-readable JSON audit trails.

You have successfully completed Month 2 of your Cloud/DevOps Engineer training!

#### 6️⃣ Clean Up & Rest

Take the weekend off. You have earned a break.

Month 3 focuses on **Advanced Infrastructure as Code (Terraform) & Configuration Management (Ansible)**. We will learn how to build and configure 500 servers simultaneously.

When you are ready to begin Month 3, just come back and type:
**"Day 51 DevOps study"** 🚀