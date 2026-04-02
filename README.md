# 🚀 Voting App on Amazon EKS - DevOps Project

A real-time **3-tier microservices voting application** where users can vote for cats 🐱 or dogs 🐕 and see live results instantly.

The system processes votes asynchronously using a worker service, stores data in Redis and PostgreSQL, and exposes services via Kubernetes on AWS.

---

## 📌 Project Overview

This project was built to simulate a **real-world distributed system** where multiple services communicate reliably and scale independently.

It demonstrates:

* Deployment of microservices on **Kubernetes (EKS)**
* Infrastructure provisioning using **Terraform**
* Automated delivery with **CI/CD pipelines**
* Debugging and managing real production-like issues

---

## 🎯 Key Features

* Containerized microservices architecture
* Kubernetes orchestration with AWS EKS
* External access via **NGINX Ingress**
* Automated CI/CD pipeline with GitHub Actions
* Real-time vote processing and result display

---

## 🏗️ Architecture

![Architecture](screenshots/architecture.png)

### 🔄 Request Flow

```text
User → NGINX Ingress → Amazon EKS → Microservices → Database
```

### 🧱 3-Tier System Design

| Layer    | Service    | Technology    | Description        |
| -------- | ---------- | ------------- | ------------------ |
| Frontend | Vote       | Python Flask  | Voting interface   |
| Frontend | Result     | Node.js       | Displays results   |
| Backend  | Worker     | .NET          | Processes votes    |
| Cache    | Redis      | In-memory DB  | Temporary storage  |
| Database | PostgreSQL | Relational DB | Persistent storage |

---

## 🛠️ Tech Stack

| Category       | Tools             |
| -------------- | ----------------- |
| Cloud          | AWS EKS           |
| Infrastructure | Terraform         |
| Containers     | Docker            |
| Orchestration  | Kubernetes        |
| CI/CD          | GitHub Actions    |
| Networking     | NGINX Ingress     |
| Database       | PostgreSQL, Redis |

---

## 📊 Results & Impact

* ✅ Deployed a **scalable 3-tier application on AWS EKS**
* ✅ Achieved **zero-downtime deployments** using Kubernetes rolling updates
* ✅ Reduced deployment time from ~2 hours to 25 minutes via CI/CD
* ✅ Successfully handled **100+ simulated users**
* ✅ Resolved real-world Kubernetes deployment issues

---

## ⚡ Deployment (Quick Start)

```bash
git clone https://github.com/donaemeka/Real-Time-Voting-Application-on-AWS-EKS.git
cd Real-Time-Voting-Application-on-AWS-EKS
```

### Create EKS Cluster

```bash
eksctl create cluster \
--name dona-eks \
--region us-east-1 \
--nodegroup-name worker-nodes \
--node-type t3.medium \
--nodes 2 \
--nodes-min 2 \
--nodes-max 4 \
--managed
```

### Deploy Application

```bash
kubectl apply -f k8s/
kubectl get pods
```

### Install Ingress

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/aws/deploy.yaml
```

### Access App

```bash
kubectl get ingress
```

Open:

* http://EXTERNAL-IP/vote
* http://EXTERNAL-IP/result

---

## 📸 Screenshots

### Kubernetes Overview

![Kubernetes Overview](screenshots/k8s-overview.png)

### Vote App UI

![Vote UI](screenshots/vote-ui.png)

### Result App UI

![Result UI](screenshots/result-ui.png)

### CI/CD Pipeline

![CI/CD](screenshots/github-actions.png)

---

## 🐞 Key Issues Resolved

| Issue                | Cause                         | Solution                      |
| -------------------- | ----------------------------- | ----------------------------- |
| CrashLoopBackOff     | Missing environment variables | Added REDIS_HOST & REDIS_PORT |
| 503 NGINX Error      | Backend services not ready    | Ensured pods were running     |
| CI/CD not triggering | Wrong workflow location       | Moved to `.github/workflows/` |

---

## 📚 Lessons Learned

* Kubernetes deployment and service orchestration
* Debugging using `kubectl logs`
* Importance of environment variables in containers
* CI/CD pipeline integration with GitHub Actions
* Service communication using labels and selectors

---

## 🚀 Future Improvements

* Add monitoring with Prometheus & Grafana
* Implement auto-scaling (HPA)
* Use Helm for deployment management

---

## 🙋 About Me

**Donatus Emeka Anyalebechi**
Junior DevOps Engineer

This project demonstrates my ability to:

* Build and deploy cloud-native applications
* Work with Kubernetes and containerized systems
* Automate deployments using CI/CD
* Troubleshoot real-world infrastructure issues

📧 [donaemeka92@gmail.com](mailto:donaemeka92@gmail.com)
🐙 https://github.com/donaemeka
🔗 https://www.linkedin.com/in/donatus-devops

---

⭐ Built to demonstrate real-world DevOps capabilities
