# 🚀 Voting App on Amazon EKS - DevOps Project

A real-time **3-tier voting application** deployed on **Amazon EKS (Kubernetes)** using **Docker, Terraform, and GitHub Actions CI/CD**.

---

## 📌 Project Overview

This project demonstrates:

* **Microservices architecture** using containerized applications
* Deployment on **AWS EKS (managed Kubernetes)**
* **CI/CD automation** with GitHub Actions
* Real-world **debugging & troubleshooting scenarios**

| Feature          | Description        |
| ---------------- | ------------------ |
| ☁️ Cloud         | AWS EKS            |
| 📦 Containers    | Docker             |
| ⚙️ Orchestration | Kubernetes         |
| 🔄 CI/CD         | GitHub Actions     |
| 🌐 Routing       | NGINX Ingress      |
| 🗄️ Database     | PostgreSQL & Redis |

---

## 🎯 Project Objectives

* Build and containerize **microservices architecture**
* Push Docker images to **Docker Hub**
* Provision infrastructure on **AWS EKS**
* Configure **NGINX Ingress** for external traffic
* Automate deployments using **CI/CD pipeline**
* Implement **Kubernetes manifests**

💡 Users can vote for **cats 🐱** or **dogs 🐕** and view results in real-time.

---

## 🏗️ Architecture

![Architecture](screenshots/architecture.png)

### 🔄 Request Flow

```text
User → NGINX Ingress → Amazon EKS → Microservices → Database
```

### 🧱 3-Tier Architecture

| Layer    | Service    | Technology    | Description        |
| -------- | ---------- | ------------- | ------------------ |
| Frontend | Vote       | Python Flask  | Voting interface   |
| Frontend | Result     | Node.js       | Displays results   |
| Backend  | Worker     | .NET          | Processes votes    |
| Cache    | Redis      | In-memory DB  | Temporary storage  |
| Database | PostgreSQL | Relational DB | Persistent storage |

---

## 🛠️ Tech Stack

| Category      | Tools             |
| ------------- | ----------------- |
| Cloud         | AWS EKS           |
| IaC           | Terraform         |
| Containers    | Docker            |
| Orchestration | Kubernetes        |
| CI/CD         | GitHub Actions    |
| Networking    | NGINX Ingress     |
| Database      | PostgreSQL, Redis |

---

## 📊 Results & Impact

* ✅ Successfully deployed a **3-tier application on AWS EKS**
* ✅ Implemented **automated CI/CD pipeline**
* ✅ Reduced manual deployment steps significantly
* ✅ Resolved real-world Kubernetes issues

---

## ⚡ How to Run This Project

### 1️⃣ Clone Repository

```bash
git clone https://github.com/donaemeka/Real-Time-Voting-Application-on-AWS-EKS.git
cd Real-Time-Voting-Application-on-AWS-EKS
```

---

### 2️⃣ Create EKS Cluster

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

---

### 3️⃣ Verify Cluster

```bash
kubectl get nodes
```

---

### 4️⃣ Build & Push Docker Images

```bash
docker build -t <dockerhub-username>/voting-app-vote ./vote
docker push <dockerhub-username>/voting-app-vote
```

*(Repeat for result and worker services)*

---

### 5️⃣ Deploy to Kubernetes

```bash
kubectl apply -f k8s/
kubectl get pods
```

---

### 6️⃣ Install NGINX Ingress

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/aws/deploy.yaml
```

---

### 7️⃣ Access Application

```bash
kubectl get ingress
```

Open:

* 🌐 `http://EXTERNAL-IP/vote`
* 🌐 `http://EXTERNAL-IP/result`

---

## 📸 Screenshots

### Kubernetes Overview

![Kubernetes Overview](screenshots/k8s-overview.png)

### Vote App UI

![Vote UI](screenshots/vote-ui.png)

### Result App UI

![Result UI](screenshots/result-ui.png)

### CI/CD Pipeline

![GitHub Actions](screenshots/github-actions.png)

---

## 📚 Lessons Learned

* Provisioning Kubernetes clusters using **eksctl**
* Writing **Kubernetes manifests** for microservices
* Understanding **Ingress vs NodePort**
* Debugging **CrashLoopBackOff errors**
* Using **kubectl logs for troubleshooting**
* Importance of **labels & selectors**
* Building **CI/CD pipelines with GitHub Actions**

---

## 🐞 Issues & Fixes

| Issue                | Cause                         | Solution                      |
| -------------------- | ----------------------------- | ----------------------------- |
| CrashLoopBackOff     | Missing environment variables | Added REDIS_HOST & REDIS_PORT |
| 503 NGINX Error      | Backend not ready             | Waited for pods to be running |
| CI/CD not triggering | Wrong file location           | Moved to `.github/workflows/` |

---

## 🚀 Future Improvements

* 📊 Add **Prometheus + Grafana monitoring**
* 📦 Implement **Helm charts**
* ⚡ Enable **auto-scaling**

---

## 🙋 About Me

I am **Donatus Emeka Anyalebechi**, a **Junior DevOps Engineer** passionate about building and automating cloud infrastructure.

This project demonstrates my ability to:

* Deploy scalable applications on **AWS**
* Work with **Kubernetes & Docker**
* Implement **CI/CD pipelines**
* Debug real-world production issues

---

## 🎯 Open to Opportunities

I am actively seeking a **Junior DevOps Engineer role** where I can contribute and grow.

---

## 📫 Contact

* 📧 Email: **[donaemeka92@gmail.com](mailto:donaemeka92@gmail.com)**
* 💻 GitHub: https://github.com/donaemeka
* 🔗 LinkedIn: https://www.linkedin.com/in/donatus-devops
