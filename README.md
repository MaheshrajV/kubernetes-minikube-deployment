
---

## 🎯 Objective
✔ Dockerize a simple application  
✔ Create Kubernetes Deployment & Service manifests  
✔ Deploy the app to Minikube  
✔ Verify pods & services using kubectl  
✔ (Bonus) Configure Ingress for domain-based access  

---

## 🐳 Step 1 — Build Docker Image
Build the Docker image:
```bash
docker build -t k8s-app:v1 .

(Optional) Test locally:

docker run -p 3000:3000 k8s-app:v1

☸ Step 2 — Start Minikube

minikube start

Load the image into Minikube:

minikube image load k8s-app:v1

📄 Step 3 — Apply Kubernetes Manifests
Deployment

kubectl apply -f deployment.yaml

Service

kubectl apply -f service.yaml

🔍 Step 4 — Verify Deployment

Check running pods:

kubectl get pods

Check services:

kubectl get svc

Access the application:

minikube service k8s-app-service

or open in browser:

http://<minikube-ip>:<node-port>

Get Minikube IP:

minikube ip

⭐ Bonus — Ingress (Optional)

Enable ingress addon:

minikube addons enable ingress

Apply ingress config:

kubectl apply -f ingress.yaml

Add local host entry:

sudo nano /etc/hosts

<minikube-ip>   k8s.local

Access:

http://k8s.local

🚧 Challenges Faced
🔹 Local Docker image not accessible in Minikube

Solution

minikube image load k8s-app:v1

🔹 Port conflicts

Changed ports or stopped conflicting processes.
🔹 Pod restart / CrashLoopBackOff

Checked logs:

kubectl logs <pod-name>

🔹 Ingress not reachable

Enabled addon + updated hosts file.
🔹 YAML indentation errors

Ensured correct formatting.
🎓 Key Learnings

    Containerizing applications with Docker

    Deploying workloads via Kubernetes Deployments

    Exposing services using NodePort

    Using kubectl for verification & debugging

    Ingress routing for domain-based access

    Real-world DevOps deployment workflow
