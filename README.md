🔐 Secure DevSecOps CI/CD Pipeline – Production-Grade Deployment
This project demonstrates a fully integrated DevSecOps pipeline that automates code building, scanning, containerization, and deployment to Azure Kubernetes Service (AKS). It incorporates security at every stage of the software development lifecycle.

❗ Note: The frontend and backend application code used in this project were cloned from public GitHub repositories. My work focuses on the DevSecOps pipeline, infrastructure, automation, and security integration.

## 🌐 Tech Stack

| Layer             | Tools / Services                          |
|------------------|-------------------------------------------|
| CI/CD            | Jenkins (on Azure VM)                     |
| Security Scans   | SonarQube (SAST), Trivy (SCA), OWASP ZAP (DAST) |
| Containers       | Docker                                    |
| Registry         | Azure Container Registry (ACR)            |
| Orchestration    | Azure Kubernetes Service (AKS)            |
| Ingress          | NGINX Ingress Controller + Azure Load Balancer |
| Monitoring       | Prometheus + Grafana                      |
| Notifications    | Slack (via Jenkins Webhooks)              |
| Source Control   | GitHub (cloned app)                       |


## 📁 Repository Structure


project-root/
├── frontend/ # ⬅️ Frontend application (cloned)
│ └── Dockerfile
│
├── backend/ # ⬅️ Backend application (cloned)
│ └── Dockerfile
│
├── k8s/ # ⬅️ Kubernetes manifests
│ ├── frontend-deployment.yaml
│ ├── backend-deployment.yaml
│ ├── frontend-service.yaml
│ ├── backend-service.yaml
│ ├── ingress.yaml
│
└── README.md


🔄 Pipeline Overview

1) Developer pushes code to GitHub

2) Jenkins (hosted on Azure VM) triggers pipeline:

3) Clones repo

4) Builds Docker images for frontend & backend

5) Runs security scans:

           SonarQube (SAST)

           Trivy (SCA)

           OWASP ZAP (DAST)

6) Pushes Docker images to ACR

7) Deploys to AKS using kubectl and YAML manifests

8) NGINX Ingress Controller (on AKS) handles external access

9) Azure Load Balancer routes traffic to the Ingress

10) Prometheus and Grafana monitor app and cluster health

11) Slack sends notifications on pipeline results and alerts

🛡️ Security Integration

✅ Static Code Analysis (SAST) with SonarQube

✅ Dependency Vulnerability Scan (SCA) with Trivy

✅ Dynamic App Security Testing (DAST) with OWASP ZAP

✅ Jenkins uses credential bindings to secure secrets

✅ Network exposure is minimized via NGINX Ingress rules




📊 Monitoring Stack

Prometheus scrapes metrics from containers and nodes

Grafana visualizes performance dashboards

Alerts can be configured to notify Slack




🔧 Infrastructure Notes

Jenkins, SonarQube, Prometheus, and Grafana run on the same Azure VM

AKS handles production-grade deployment and scaling

ACR stores Docker images securely for AKS to pull




🛠️ Requirements

Azure subscription

Azure VM (Ubuntu 22.04 LTS)

Azure Kubernetes Service (AKS)

Azure Container Registry (ACR)

Domain or public IP for Ingress

Slack Webhook configured for Jenkins





🙏 Credits :

Frontend Source: https://github.com/harshmangalam/facebook-clone-app-react-client.git

Backend Source: https://github.com/harshmangalam/facebook-clone-app-nodejs-server.git

These apps are not developed by me — credit goes to their original authors.




👨‍💻 Maintainer


Name: Khalid Nazih

Role: DevOps & Network Engineer

LinkedIn: https://www.linkedin.com/in/khalid-nazih-b5618b2b6/



