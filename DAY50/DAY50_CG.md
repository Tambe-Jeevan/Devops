Congratulations, **Jeevan** 🎉

You've reached **Day 50**. Today you'll combine everything you've learned into a complete, production-style DevOps project.

# Day 50 – End-to-End DevOps Project 🚀☁️☸️🐳📊

This project demonstrates the skills expected from a junior Cloud/DevOps Engineer.

---

# 🎯 Project Goal

Build an automated deployment pipeline that:

* Stores source code in GitHub
* Builds Docker images automatically
* Pushes images to Docker Hub
* Deploys applications to Kubernetes
* Monitors the application

---

# 🏗️ Project Architecture

```text
Developer
    ↓
Git Push
    ↓
GitHub Repository
    ↓
GitHub Actions
    ↓
Docker Build
    ↓
Docker Hub
    ↓
Kubernetes Cluster
    ↓
Service + Ingress
    ↓
Users
         ↓
Prometheus + Grafana
```

---

# 📁 Project Structure

```text
devops-project/
│
├── app/
│   └── index.html
│
├── Dockerfile
│
├── kubernetes/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ingress.yaml
│
├── .github/
│   └── workflows/
│       └── ci-cd.yml
│
└── README.md
```

---

# 1️⃣ Create the Application

Create `app/index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>DevOps Project</title>
</head>
<body>
  <h1>Welcome to Jeevan's DevOps Project 🚀</h1>
</body>
</html>
```

---

# 2️⃣ Create Dockerfile

```dockerfile
FROM nginx:alpine

COPY app/index.html /usr/share/nginx/html/index.html
```

---

# 3️⃣ Build and Test Locally

Build:

```bash
docker build -t your-dockerhub-username/devops-project:v1 .
```

Run:

```bash
docker run -d -p 8080:80 your-dockerhub-username/devops-project:v1
```

Open:

```text
http://localhost:8080
```

---

# 4️⃣ Push Code to GitHub

Initialize repository:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin YOUR_GITHUB_REPO_URL
git push -u origin main
```

---

# 5️⃣ Create GitHub Actions Workflow

Create:

```text
.github/workflows/ci-cd.yml
```

Example:

```yaml
name: CI-CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  docker:

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

      - name: Build Image
        run: docker build -t your-dockerhub-username/devops-project:latest .

      - name: Push Image
        run: docker push your-dockerhub-username/devops-project:latest
```

---

# 6️⃣ Configure GitHub Secrets

In your GitHub repository:

```text
Settings
  → Secrets and Variables
  → Actions
```

Create:

```text
DOCKER_USERNAME
DOCKER_PASSWORD
```

---

# 7️⃣ Kubernetes Deployment

Create `kubernetes/deployment.yaml`

```yaml
apiVersion: apps/v1
kind: Deployment

metadata:
  name: devops-project

spec:
  replicas: 2

  selector:
    matchLabels:
      app: devops-project

  template:
    metadata:
      labels:
        app: devops-project

    spec:
      containers:
      - name: app
        image: your-dockerhub-username/devops-project:latest

        ports:
        - containerPort: 80
```

Apply:

```bash
kubectl apply -f kubernetes/deployment.yaml
```

---

# 8️⃣ Kubernetes Service

Create `kubernetes/service.yaml`

```yaml
apiVersion: v1
kind: Service

metadata:
  name: devops-service

spec:
  selector:
    app: devops-project

  ports:
  - port: 80
    targetPort: 80

  type: NodePort
```

Apply:

```bash
kubectl apply -f kubernetes/service.yaml
```

---

# 9️⃣ Kubernetes Ingress

Create `kubernetes/ingress.yaml`

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress

metadata:
  name: devops-ingress

spec:
  rules:
  - host: devops.local

    http:
      paths:
      - path: /
        pathType: Prefix

        backend:
          service:
            name: devops-service

            port:
              number: 80
```

Apply:

```bash
kubectl apply -f kubernetes/ingress.yaml
```

---

# 🔟 Monitoring

Install monitoring stack using Helm:

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm repo update

helm install monitoring prometheus-community/kube-prometheus-stack
```

This installs:

* Prometheus
* Grafana
* Alertmanager

---

# 1️⃣1️⃣ Verify Deployment

Check resources:

```bash
kubectl get deployments

kubectl get pods

kubectl get svc

kubectl get ingress
```

---

# 1️⃣2️⃣ Test CI/CD

Modify:

```html
<h1>Version 2 🚀</h1>
```

Commit changes:

```bash
git add .
git commit -m "Updated application"
git push
```

GitHub Actions automatically:

```text
Builds Image
      ↓
Pushes Image
```

Update Kubernetes:

```bash
kubectl rollout restart deployment/devops-project
```

---

# 📋 Resume Project Description

> Designed and implemented an end-to-end CI/CD pipeline using GitHub Actions, Docker, Kubernetes, Helm, Prometheus, and Grafana. Automated application build and deployment workflows, implemented container orchestration, and configured monitoring for application observability.

---

# 🎤 Interview Questions

### What happens after code is pushed to GitHub?

GitHub Actions automatically triggers a workflow that builds and pushes a Docker image.

---

### Why use Docker?

To package applications consistently across environments.

---

### Why use Kubernetes?

To automate deployment, scaling, and management of containers.

---

### Why use Prometheus and Grafana?

To collect metrics and visualize application health.

---

### What is Ingress?

A Kubernetes resource that routes external traffic to services.

---

# 🏆 What You've Achieved in 50 Days

You now have foundational knowledge of:

✅ Linux

✅ Networking

✅ Git & GitHub

✅ Bash Scripting

✅ Python Basics

✅ Docker

✅ Jenkins

✅ GitHub Actions

✅ AWS

✅ Terraform

✅ Kubernetes

✅ Helm

✅ Monitoring

✅ CI/CD

✅ End-to-End DevOps Projects

You are ready to start:

* Building more advanced projects
* Applying for junior DevOps roles
* Preparing for interviews
* Earning cloud certifications

---

# 🚀 Day 51 Preview

Tomorrow you'll learn:

# AWS DevOps Project – Infrastructure as Code

Topics:

✅ Terraform + AWS

✅ EC2 Deployment

✅ VPC Setup

✅ CI/CD Integration

✅ Real Cloud Architecture

When ready, type:

**"Day 51 DevOps study"** ☁️🚀🏗️
