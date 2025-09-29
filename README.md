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
<br>
<br>
<br>
<img width="1913" height="932" alt="Screenshot 2025-09-29 160448" src="https://github.com/user-attachments/assets/6e49dcfc-57fe-4901-99eb-1e54b3db3c25" />
<br>
<br>
<img width="1898" height="857" alt="Screenshot 2025-09-29 161031" src="https://github.com/user-attachments/assets/196b9f33-4b4c-4ed4-b573-66d7ba6aca40" />
<br>
<br>
<img width="1910" height="955" alt="Screenshot 2025-09-29 160824" src="https://github.com/user-attachments/assets/0f3c29bd-39f5-432e-b7ef-110249e2fdbe" />
<br>
<br>

