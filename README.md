# Task 5: Build a Kubernetes Cluster Locally with Minikube

## Objective

Deploy and manage apps in Kubernetes using **Minikube**, **kubectl**, and **Docker**.

---

## 🛠 Tools Required

* [Docker](https://docs.docker.com/get-docker/)
* [Minikube](https://minikube.sigs.k8s.io/docs/start/)
* [kubectl](https://kubernetes.io/docs/tasks/tools/)

---

## 📂 Project Structure

```
task5_kubernetes_minikube/
│── deployment.yaml     # Defines Deployment for Nginx app
│── service.yaml        # Exposes Deployment via NodePort service
│── execution_guide.txt # Step-by-step execution guide
```

---

## ⚡ Steps to Run

### 1. Install Dependencies

```bash
# Install Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
```

### 2. Start Minikube Cluster

```bash
minikube start --driver=docker
```

### 3. Apply Deployment

```bash
kubectl apply -f deployment.yaml
kubectl get pods
```

### 4. Apply Service

```bash
kubectl apply -f service.yaml
kubectl get svc
```

### 5. Access App

```bash
minikube service myapp-service --url
```

Paste the URL in a browser → You should see **Nginx Welcome Page** 🎉

### 6. Scale Deployment

```bash
kubectl scale deployment myapp-deployment --replicas=3
kubectl get pods
```

### 7. Debug & Logs

```bash
kubectl describe pod <pod-name>
kubectl logs <pod-name>
```

### 8. Stop / Delete Cluster

```bash
minikube stop
minikube delete
```

---

## 📸 Deliverables

* **YAML Files:** Deployment + Service
* **Screenshots:** `kubectl get pods`, `kubectl get svc`

---

## Outcome

You will successfully:

* Create a Kubernetes cluster locally.
* Deploy an application.
* Expose it via NodePort.
* Scale and manage deployments.

---

👨‍💻 **Author**: DevOps Training Guide
🔥 Learn | Deploy | Scale | Master Kubernetes
