Excellent progress, **Jeevan** 🔥

From today onward, you'll start building **real cloud projects** that combine your DevOps skills.

# Day 51 – AWS DevOps Project: Infrastructure as Code with Terraform ☁️🏗️🚀

In this project, you'll automate AWS infrastructure creation using Terraform.

---

# 🎯 Today's Goal

Build this architecture:

```text id="7pqnsf"
Developer
    ↓
Terraform
    ↓
AWS

VPC
 ├── Public Subnet
 ├── Internet Gateway
 ├── Route Table
 ├── Security Group
 └── EC2 Instance
```

You'll learn how DevOps teams provision infrastructure consistently and repeatedly.

---

# 🧠 Why Infrastructure as Code (IaC)?

Without Terraform:

❌ Manual AWS Console configuration

❌ Human errors

❌ Difficult to reproduce environments

With Terraform:

✅ Version-controlled infrastructure

✅ Automated deployments

✅ Reusable code

✅ Faster provisioning

---

# 📁 Project Structure

```text id="x4m4np"
terraform-aws-project/
│
├── provider.tf
├── variables.tf
├── main.tf
├── outputs.tf
└── terraform.tfvars
```

---

# 1️⃣ Prerequisites

Install:

* Terraform
* AWS CLI

Configure AWS credentials:

```bash id="snv7zn"
aws configure
```

Provide:

```text id="8izscu"
AWS Access Key ID
AWS Secret Access Key
Region: ap-south-1
```

Verify:

```bash id="4z5pg8"
aws sts get-caller-identity
```

---

# 2️⃣ Configure Terraform Provider

Create `provider.tf`

```hcl id="2j1p0g"
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = var.aws_region
}
```

---

# 3️⃣ Create Variables

Create `variables.tf`

```hcl id="i7mt65"
variable "aws_region" {
  default = "ap-south-1"
}

variable "instance_type" {
  default = "t2.micro"
}
```

---

Create `terraform.tfvars`

```hcl id="7lpp1w"
aws_region   = "ap-south-1"
instance_type = "t2.micro"
```

---

# 4️⃣ Create VPC

Add to `main.tf`

```hcl id="ys9on4"
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"

  tags = {
    Name = "devops-vpc"
  }
}
```

---

# 5️⃣ Create Public Subnet

```hcl id="6vc2pr"
resource "aws_subnet" "public" {
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.1.0/24"
  map_public_ip_on_launch = true

  tags = {
    Name = "public-subnet"
  }
}
```

---

# 6️⃣ Create Internet Gateway

```hcl id="fy75c0"
resource "aws_internet_gateway" "igw" {
  vpc_id = aws_vpc.main.id
}
```

---

# 7️⃣ Create Route Table

```hcl id="8fxtie"
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id

  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.igw.id
  }
}
```

Associate subnet:

```hcl id="p6d53d"
resource "aws_route_table_association" "public" {
  subnet_id      = aws_subnet.public.id
  route_table_id = aws_route_table.public.id
}
```

---

# 8️⃣ Create Security Group

```hcl id="j0x6h6"
resource "aws_security_group" "web" {
  name   = "web-sg"
  vpc_id = aws_vpc.main.id

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["YOUR_IP/32"]
  }

  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

Replace:

```text id="0bwqyi"
YOUR_IP/32
```

with your public IP address.

---

# 9️⃣ Create EC2 Instance

```hcl id="6a4j4d"
resource "aws_instance" "web" {
  ami                    = "ami-0f58b397bc5c1f2e8"
  instance_type          = var.instance_type
  subnet_id              = aws_subnet.public.id
  vpc_security_group_ids = [aws_security_group.web.id]

  tags = {
    Name = "devops-server"
  }
}
```

> Note: Verify the latest Amazon Linux 2 AMI for your region.

---

# 🔟 Outputs

Create `outputs.tf`

```hcl id="k8w9r8"
output "instance_public_ip" {
  value = aws_instance.web.public_ip
}
```

---

# 1️⃣1️⃣ Deploy Infrastructure

Initialize:

```bash id="jyf4t0"
terraform init
```

Validate:

```bash id="3g8d0r"
terraform validate
```

Preview:

```bash id="r8f9a4"
terraform plan
```

Create infrastructure:

```bash id="mdvj6d"
terraform apply
```

Destroy when finished:

```bash id="j2r1dx"
terraform destroy
```

---

# 🧪 Practice Lab (90–120 Minutes)

### Task 1

Configure AWS CLI.

---

### Task 2

Create all Terraform files.

---

### Task 3

Deploy:

* VPC
* Public subnet
* Internet gateway
* Route table
* Security group
* EC2 instance

---

### Task 4

SSH into EC2:

```bash id="dh4hja"
ssh -i key.pem ec2-user@PUBLIC_IP
```

---

### Task 5

Destroy resources to avoid charges.

---

# 🛠️ Mini Project

Build:

```text id="1w7e7w"
Terraform
     ↓
AWS VPC
     ↓
EC2 Instance
```

Document:

* VPC CIDR
* Subnet CIDR
* Instance type
* Public IP

---

# 🎤 Interview Questions

### What is Infrastructure as Code?

Managing infrastructure using code instead of manual processes.

---

### Why use Terraform?

To automate, standardize, and version-control infrastructure.

---

### What is a Terraform provider?

A plugin that allows Terraform to interact with a platform such as AWS.

---

### What is a Terraform state file?

A file that stores the current state of infrastructure.

---

### Why should Terraform state be stored remotely?

For collaboration, backup, and consistency.

---

# 🏆 What You Know After Day 51

You can now:

✅ Provision AWS infrastructure with Terraform

✅ Create VPCs and networking resources

✅ Deploy EC2 instances automatically

✅ Use variables and outputs

✅ Apply Infrastructure as Code concepts

You're moving beyond theory into practical cloud engineering skills.

---

# 🚀 Day 52 Preview

Tomorrow you'll learn:

# Terraform Modules & Remote State

Topics:

✅ Modules

✅ Reusable Infrastructure

✅ S3 Backend

✅ DynamoDB State Locking

✅ Team Collaboration

These concepts are heavily used in production DevOps environments.

When ready, type:

**"Day 52 DevOps study"** ☁️📦🚀
