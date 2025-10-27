# 🧩 TASK 5 — Build a Kubernetes Cluster Locally with Minikube

## 🎯 Objective
The goal of this task was to learn the basics of **Kubernetes** by running it locally using **Minikube**.  
I deployed a simple **Nginx web server**, exposed it with a **service**, checked the pods, scaled the deployment, and explored logs.  
This task helped me understand how Kubernetes manages applications using **pods**, **deployments**, and **services**.

---

## 🧰 Tools and Technologies Used
- **Minikube** → To create a local Kubernetes cluster  
- **kubectl** → To manage and interact with the cluster  
- **Docker** → Used as the container runtime for Minikube  
- **Nginx** → A simple web server used as the demo application  
- **VS Code / Terminal** → For writing YAML files and running commands  

---

##  Step-by-Step Process

###  Step 1 — Starting Minikube
I started Minikube using Docker as the driver:
```bash
minikube start --driver=docker
minikube status
###  Step 2 - Creating a Deployment 
- Write the yaml file and run this command
kubectl apply -f deployment-task5.yaml
- To verify pods use this command
kubectl get pods
### Step 3 - Creating a Service
- Write the yaml file and this command
kubectl apply -f service-task5.yaml
- To verify Services use this command
kubectl get svc
### Step 5 - Accessing the Applicaion
- Use this command
minikube service task5-service
### Step 6 - Scaling the Deployment
- Use this command
kubectl scale deployment task5-deployment --replicas=4
- To verify the pods
kubectl get pods
### Step 7 - Checking the pod details and logs
kubectl describe pod <pod-name>
kubectl logs <pod-name>
### Step 8 - Cleanup
kubectl delete -f deployment-task5.yaml
kubectl delete -f service-task5.yaml
minikube stop

