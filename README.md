# End-to-End Continuous Deployment using ArgoCD on AWS EKS

## 🚀 Project Overview
This project demonstrates a complete Continuous Deployment (CD) pipeline using:

- Docker
- DockerHub
- GitHub
- ArgoCD
- AWS EKS

The deployment follows GitOps principles where ArgoCD continuously monitors GitHub for changes and automatically syncs them to the Kubernetes cluster.

---

## 🏗 Architecture

Docker → DockerHub → GitHub (K8s Manifests) → ArgoCD → AWS EKS → LoadBalancer → Browser

---

## 🔧 Steps Performed

1. Created AWS EKS Cluster using `eksctl`
2. Created Managed Node Group
3. Installed ArgoCD using Helm
4. Built Docker Image and pushed to DockerHub
5. Created Kubernetes Deployment & Service YAML
6. Configured ArgoCD with Automated Sync (Prune + Self-Heal)
7. Verified live deployment
8. Verified replica scaling through Git change

---

## 📦 Application Details

- Docker Image: `dhiraj9190/argocd-eks-demo:latest`
- Service Type: LoadBalancer
- Namespace: default
- Sync Policy: Automated

---

## 🔁 Continuous Deployment Proof

When the replica count was changed in GitHub:
- ArgoCD automatically detected the change
- Cluster was updated
- New pods were created without manual intervention

This confirms successful GitOps-based Continuous Deployment.

---

## 📁 Repository Structure
