**🚀 Three-Tier Web App on AWS EKS with Kubernetes (React + Node.js + MongoDB)**

This project demonstrates deploying a **production-ready, full-stack three-tier application** on **Amazon EKS (Elastic Kubernetes Service)** using **Kubernetes**. It features a React frontend, Node.js backend, and MongoDB database—fully containerized and orchestrated for scalability and resilience.

---
![Three-tier-App](https://github.com/user-attachments/assets/482444f5-17cf-4fb3-a33a-3404bb96f7f1)


**📁 Project Structure**

```
.
├── appcode/
│   ├── frontend/           # React app source code
│   └── backend/            # Node.js + Express API source code
├── K8s/
│   ├── frontend/           # Frontend deployment and service
│   ├── backend/            # Backend deployment and service
│   ├── db/                 # MongoDB deployment, service, PVC, and secrets
│   └── ingress.yaml        # Ingress with ALB annotations
└── README.txt
```

---

**🧩 Architecture Overview**

```
User ↔ ALB (Ingress Controller)
     ↳ Frontend (React)
     ↳ Backend (Node.js API)
     ↳ MongoDB (Persistent Database)
```

---

**🛠️ Tools & Technologies Used**

* **Amazon EKS**: Managed Kubernetes cluster
* **AWS CLI**: To provision and configure IAM roles, OIDC provider, and EKS resources
* **IAM Policies**: For service account roles used by ALB ingress controller
* **Kubernetes**: Deployments, Services, Ingress, Secrets, PVCs
* **AWS Load Balancer Controller**: For managing ingress with ALB
* **Docker + AWS ECR**: For building and pushing container images
* **MongoDB, Node.js, React**: Application stack

---

**⚙️ Deployment Steps**

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/three-tier-k8s-eks.git
   cd three-tier-k8s-eks
   ```

2. **Create Kubernetes Namespace**

   ```bash
   kubectl create namespace three-tier
   ```

3. **Apply Kubernetes Resources**

   ```bash
   kubectl apply -f .
   ```

4. **Install ALB Ingress Controller**

   * Set up IAM OIDC provider for EKS
   * Create IAM policy and attach it to a service account
   * Install ALB ingress controller using Helm

5. **Get Application URL**

   ```bash
   kubectl get ingress -n three-tier
   ```

   Access your app at: `http://<ALB-DNS>/`

---

**🔐 Security & Best Practices**

* Used **Kubernetes Secrets** to manage DB credentials
* Created **Persistent Volume Claims (PVCs)** for MongoDB
* Applied **RBAC and IAM roles** for secure access to AWS resources
* Used **path-based routing** for clean API access via ALB

---

**📘 What I Learned**

* Building a full-stack app and containerizing with Docker
* Creating and applying Kubernetes manifests in a structured manner
* Configuring secure access with IAM, OIDC, and AWS CLI
* Installing and configuring ALB Ingress Controller for public access
* Debugging pods and services using `kubectl logs`, `exec`, and `describe`
* Managing AWS infrastructure using a DevOps-first mindset

---

**🙋‍♂️ Let's Connect**

If you're passionate about DevOps, Cloud, and Kubernetes, let's connect on LinkedIn:
https://www.linkedin.com/in/shubham-devops/

