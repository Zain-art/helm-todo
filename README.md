# helm-todo
# 🧰 Go TODO App with Helm Deployment and ArgoCD

This project is a simple TODO CRUD application written in Golang, packaged and deployed using Helm. It includes a Kubernetes-ready Helm chart with templated **Deployment**, **Service**, and optional **ConfigMap**/**Secret**.

---

## 📦 Project Overview

- ✅ Built in Go (Golang)
- ✅ Uses MySQL for persistence
- ✅ Containerized with Docker
- ✅ Deployed via Helm on Kubernetes
- ✅ Includes config templating with Helm charts

---

## 🖥️ Prerequisites

Before getting started, make sure you have the following installed:

### 🪟 For Windows

- [Go](https://go.dev/dl/)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Helm](https://helm.sh/docs/intro/install/)

### 🐧 For Linux (Ubuntu/Debian)

```bash
# Install Go
sudo apt update
sudo apt install golang-go

# Install Docker
sudo apt install docker.io

# Install Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Install kubectl
sudo apt install -y kubectl

# Install Helm
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
```

## Step 1: Clone the Repository
```bash
git clone https://github.com/Zain-art/go-todo-task1.git
cd go-todo-task1
```
## Step 2: Build the Docker Image using Github Actions CI/CD Pipeline Workflows

- Go to [go-todo-taks1 and see CI/CD Github Actions Workflows](https://github.com/Zain-art/go-todo-task1/blob/main/.github/workflows/ci.yml)

### Deploy with Helm on Minikube with docker driver
```bash
minikube start --driver=docker
```
## Step 3: Create a New Helm Chart
```bash
helm create go-todo-app
```
## 🚢 Step 4: Install Helm Chart
```bash
helm install my-todo .
```

### Check deployment:
```bash
kubectl get all
```
### Access the app:
```bash
kubectl port-forward service/todo-service 8000:80
```
##  Upgrade Helm Release
```bash
helm upgrade my-todo
```

## Uninstall Helm Release
```bash
helm uninstall my-todo 
```
##  Integrating Argo CD with your Helm-deployed Go TODO application enables continuous delivery with GitOps
### 🚀 GitOps with Argo CD 
### 📦 Step 5: Install Argo CD on Kubernetes
```bash
# Create namespace
kubectl create namespace argocd

# Install Argo CD
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
##  Step 6: Access Argo CD UI
```bash
# Port-forward the Argo CD API server
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
## 🔐 Step 7: Login to Argo CD
```bash
# Get the initial admin password
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo
```
* Login with:
* Username: admin
* Password: (from above command)

##  Create GitOps Repo in ArgoCD
### Step 8: Connect Your Git Repository
###  Create Argo CD Application via Web UI
### 🔄 Step 9: Sync and Deploy
### ✅ Step 10: Verify Deployment
```bash
kubectl get all
```
### 🌐 Step 11: Access the TODO Application via Port Forwarding
* Find the service name:
 ```bash
kubectl get svc
```
### Port forward the service (replace todo-service-helm with your actual service name if different):
```bash
kubectl port-forward svc/todo-service-helm 4040:80
```
* Open your browser and visit:
```bash
http://localhost:4040
```




