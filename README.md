# helm-todo
# 🧰 Go TODO App with Helm Deployment

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
```bash
- Go to [go-todo-taks1]  https://github.com/Zain-art/go-todo-task1/blob/main/.github/workflows/ci.yml
```


