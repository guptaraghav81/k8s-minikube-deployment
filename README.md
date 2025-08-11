# Kubernetes Minikube Deployment

## 📌 Overview
This project demonstrates how to deploy and manage applications in a local Kubernetes cluster using **Minikube**.  
It includes creating deployments, exposing services, scaling, and verifying using `kubectl`.

---

## 🛠 Tools Used
- **Minikube** – Local Kubernetes cluster
- **kubectl** – Kubernetes CLI
- **Docker** – Container image support

---

## 📂 Project Structure <br>
k8s-minikube-deployment/ <br>
├── deployment.yaml # App deployment <br>
├── service.yaml # App service exposure <br>
├── README.md # Documentation <br>
├── screenshots/ # Verification screenshots <br>
└── .gitignore <br>

---

📝 Steps to Run the Project:- <br>
1️⃣ Install Prerequisites<br>
Install Docker<br>

Install Minikube<br>

Install kubectl<br>

2️⃣ Start Minikube<br>

minikube start <br>
3️⃣ Create Deployment <br>
Edit and apply the deployment.yaml file: <br>

kubectl apply -f deployment.yaml <br>
4️⃣ Expose Service <br>

kubectl apply -f service.yaml <br>
5️⃣ Check Resources <br>

kubectl get pods <br>
kubectl get services <br>
6️⃣ Scale Deployments <br>
kubectl scale deployment my-app --replicas=3 <br>
7️⃣ Access the App <br>
minikube service my-service <br>
8️⃣ Debug & View Logs <br>

kubectl describe pod <pod-name> <br>
kubectl logs <pod-name> <br>
📄 Example deployment.yaml <br>
```
apiVersion: apps/v1 
kind: Deployment 
metadata: 
  name: my-app 
spec: 
  replicas: 2 
  selector: 
    matchLabels: 
      app: my-app 
  template: 
    metadata: 
      labels: 
        app: my-app 
    spec: 
      containers: 
      - name: my-app-container 
        image: nginx:latest 
        ports: 
        - containerPort: 80
```
📄 Example service.yaml <br>
yaml <br>
```
apiVersion: v1 
kind: Service 
metadata: 
  name: my-service 
spec: 
  type: NodePort 
  selector: 
    app: my-app 
  ports: <br>
    - port: 80 
      targetPort: 80 
      nodePort: 30007 
```
🚀 Features:- <br>
1.Local Kubernetes Cluster using Minikube
<br>
2.Application Deployment via YAML manifests
<br>
3.Service Exposure using NodePort
<br>
4.Scaling Deployments dynamically
<br>
5.Pod & Service Monitoring with kubectl
<br>
6.Logs & Troubleshooting using kubectl describe


🏆 Learning Outcome <br>
1.By completing this project, you will:

2.Understand how Kubernetes deployments work.

3.Create and expose services.

4.Scale applications in Kubernetes.

5.Use kubectl for management and troubleshooting.

