Excellent progress, **Jeevan** 🔥

Today you'll learn how real production applications handle **high traffic**, **high availability**, and **automatic scaling**.

# Day 55 – AWS Load Balancers & Auto Scaling ⚖️☁️🚀

---

# 🎯 Today's Goal

Understand:

✅ Load Balancing

✅ Application Load Balancer (ALB)

✅ Network Load Balancer (NLB)

✅ Target Groups

✅ Auto Scaling Groups (ASG)

✅ High Availability

---

# 1️⃣ Why Do We Need a Load Balancer?

Suppose you have only one server:

```text
Users
  ↓
EC2-1
```

Problems:

❌ Server crash = Application down

❌ Cannot handle heavy traffic

❌ Single point of failure

---

# Solution

Use multiple servers.

```text
EC2-1
EC2-2
EC2-3
```

But users need a single entry point.

That's where a Load Balancer comes in.

```text
Users
  ↓
Load Balancer
 ↓   ↓   ↓
EC2 EC2 EC2
```

---

# 2️⃣ What is Elastic Load Balancing (ELB)?

AWS provides a managed load balancing service called:

Amazon Web Services Elastic Load Balancing (ELB)

Functions:

✅ Distributes traffic

✅ Improves availability

✅ Removes unhealthy servers

✅ Supports SSL/TLS

---

# 3️⃣ Types of AWS Load Balancers

```text
ELB
├── Application Load Balancer (ALB)
├── Network Load Balancer (NLB)
└── Gateway Load Balancer (GWLB)
```

For DevOps interviews:

Focus mainly on:

✅ ALB

✅ NLB

---

# 4️⃣ Application Load Balancer (ALB)

Works at:

```text
Layer 7 (Application Layer)
```

Understands:

```text
HTTP
HTTPS
URLs
Hostnames
```

---

# Example

```text
app.company.com
      ↓
ALB
     ↓
EC2 Instances
```

---

# Path-Based Routing

```text
company.com/app
      ↓
App Server

company.com/api
      ↓
API Server
```

ALB can route traffic based on URL paths.

---

# Host-Based Routing

```text
app.company.com
      ↓
Frontend

api.company.com
      ↓
Backend
```

Very common in production.

---

# 5️⃣ Network Load Balancer (NLB)

Works at:

```text
Layer 4 (Transport Layer)
```

Supports:

```text
TCP
UDP
TLS
```

---

# Characteristics

✅ Extremely fast

✅ Very low latency

✅ Handles millions of requests

---

# Use Cases

```text
Gaming
Financial Systems
VoIP
High-Performance Applications
```

---

# ALB vs NLB

| ALB          | NLB                   |
| ------------ | --------------------- |
| Layer 7      | Layer 4               |
| HTTP/HTTPS   | TCP/UDP               |
| Path Routing | No Path Routing       |
| Host Routing | No Host Routing       |
| Web Apps     | High Performance Apps |

---

# 6️⃣ What is a Target Group?

Load Balancers don't send traffic directly to instances.

Instead:

```text
Load Balancer
      ↓
Target Group
      ↓
EC2 Instances
```

---

# Example

```text
Target Group

├── EC2-1
├── EC2-2
└── EC2-3
```

---

# Health Checks

ALB continuously checks:

```text
http://server/health
```

Healthy:

✅ Receives traffic

Unhealthy:

❌ Removed automatically

---

# 7️⃣ Auto Scaling Groups (ASG)

One server may not be enough.

Traffic increases:

```text
100 Users
1000 Users
10000 Users
```

---

# Without Auto Scaling

```text
EC2-1
```

Server overload.

---

# With Auto Scaling

```text
EC2-1
EC2-2
EC2-3
EC2-4
```

Instances are added automatically.

---

# 8️⃣ Auto Scaling Workflow

```text
CPU > 70%
      ↓
Launch New EC2
```

---

When traffic decreases:

```text
CPU < 20%
      ↓
Terminate EC2
```

---

# Benefits

✅ Cost optimization

✅ High availability

✅ Better performance

---

# 9️⃣ Launch Template

ASG needs a blueprint.

Called:

```text
Launch Template
```

Contains:

* AMI
* Instance Type
* Security Group
* Key Pair

---

# Example

```text
Launch Template
      ↓
Auto Scaling Group
      ↓
EC2 Instances
```

---

# 🔟 High Availability Architecture

Production design:

```text
Users
   ↓
ALB
 ↓     ↓
AZ-1   AZ-2

EC2    EC2
EC2    EC2
```

If one Availability Zone fails:

```text
AZ-1 ❌

AZ-2 ✅
```

Application remains available.

---

# 1️⃣1️⃣ Real Production Architecture

```text
Internet
     ↓
ALB
     ↓

Public Subnets
     ↓

Auto Scaling Group
     ↓

Private App Servers
     ↓

RDS Database
```

This is a common AWS architecture used by many organizations.

---

# 🧪 Practice Lab (90–120 Minutes)

### Task 1

Create:

✔ Two EC2 instances

---

### Task 2

Install NGINX on both.

```bash
sudo yum install nginx -y
sudo systemctl enable nginx
sudo systemctl start nginx
```

---

### Task 3

Create:

✔ Target Group

---

### Task 4

Register both EC2 instances.

---

### Task 5

Create:

✔ Application Load Balancer

---

### Task 6

Verify:

Refresh ALB DNS name multiple times.

Traffic should distribute between instances.

---

### Task 7

Create:

✔ Launch Template

✔ Auto Scaling Group

---

# 🛠️ Mini Project

Build:

```text
Internet
     ↓
ALB
     ↓
ASG
 ↓     ↓
EC2   EC2
```

Document:

* ALB DNS
* Target Group
* Launch Template
* ASG Configuration

---

# 🎤 Interview Questions

### What is a Load Balancer?

A service that distributes incoming traffic across multiple servers.

---

### What is ALB?

A Layer 7 load balancer that supports HTTP/HTTPS routing.

---

### What is NLB?

A Layer 4 load balancer designed for high-performance TCP/UDP traffic.

---

### What is a Target Group?

A collection of resources that receive traffic from a load balancer.

---

### What is Auto Scaling?

Automatically adding or removing instances based on demand.

---

### Why Use Multiple Availability Zones?

To improve fault tolerance and high availability.

---

# 🏆 What You Know After Day 55

You now understand:

✅ Application Load Balancer (ALB)

✅ Network Load Balancer (NLB)

✅ Target Groups

✅ Health Checks

✅ Launch Templates

✅ Auto Scaling Groups

✅ High Availability Architecture

These are core AWS concepts frequently asked in DevOps, Cloud Engineer, and SRE interviews.

---

# 🚀 Day 56 Preview

Tomorrow you'll learn:

# AWS RDS & Database Fundamentals for DevOps

Topics:

✅ RDS

✅ MySQL

✅ PostgreSQL

✅ Multi-AZ

✅ Read Replicas

✅ Backups & Snapshots

✅ Database Security

When ready, type:

**"Day 56 DevOps study"** 🗄️☁️🚀
