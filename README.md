# kubernetes-n-tier-project-voting-app

🗳️ Kubernetes N-Tier Project – Voting App

This project is a multi-tier microservices-based Voting Application deployed on Kubernetes.
It demonstrates how to run and scale an application using Deployments, Services, and Ingress.

📌 Architecture

The application consists of 5 microservices running in different tiers:

Vote App (Frontend) – lets users vote.

Result App (Frontend) – displays voting results.

Worker Service – processes votes and pushes them to DB.

Redis – in-memory store for votes.

PostgreSQL – database for storing results.

🔹 Service Types Used

ClusterIP → for internal services (Redis, PostgreSQL).

Ingress → for external access (Vote & Result apps).

⚙️ Kubernetes Resources

Deployments → manage Pods and ensure scalability.

Services → enable communication between microservices.

Ingress → routes external traffic to frontend services.


🚀 How to Run
1️⃣ Enable Ingress (Minikube only)

minikube addons enable ingress

2️⃣ Deploy All Microservices

kubectl apply -f postgres/
kubectl apply -f redis/
kubectl apply -f vote/
kubectl apply -f result/
kubectl apply -f worker/

3️⃣ Apply Ingress

kubectl apply -f ingress/ingress.yaml