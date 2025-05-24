:

## 🔐 Secure DevSecOps CI/CD Pipeline – Production-Grade Deployment (GCP Edition)
This project demonstrates a fully integrated DevSecOps pipeline that automates code building, scanning, containerization, and deployment to Google Kubernetes Engine (GKE). It incorporates security at every stage of the software development lifecycle.

❗ Note: The frontend and backend application code used in this project were cloned from public GitHub repositories. My work focuses on the DevSecOps pipeline, infrastructure, automation, and security integration.

## 🌐 Tech Stack

| Layer           | Tools / Services                                                               |
|----------------|----------------------------------------------------------------------------------|
| **CI/CD**       | Jenkins (on GCP Compute Engine)                                                 |
| **Security Scans** | SonarQube (SAST), Trivy (SCA), OWASP ZAP (DAST)                             |
| **Containers**   | Docker                                                                         |
| **Registry**     | Google Artifact Registry                                                       |
| **Orchestration**| Google Kubernetes Engine (GKE)                                                 |
| **Ingress**      | NGINX Ingress Controller + Google Cloud Load Balancer                         |
| **Monitoring**   | Prometheus + Grafana                                                           |
| **Notifications**| Slack (via Jenkins Webhooks)                                                   |
| **Source Control**| GitHub (cloned app)                                                          |


## 📁 Repository Structure

Secure-DevSecOps-Pipline/
│
├── frontend/                      # [Frontend application]
│   ├── Dockerfile
│   └── .dockerignore
│
├── backend/                       # [Backend application]
│   ├── Dockerfile
│   └── .dockerignore
│
└── k8s-deployment/               # Kubernetes deployment files
    ├── frontend-deployment.yaml
    ├── backend-deployment.yaml
    ├── frontend-service.yaml
    ├── backend-service.yaml
    └── ingress.yaml
│
└── README.md                      # GCP setup guide

## 🔄 Pipeline Overview

Developer pushes code to GitHub

Jenkins (hosted on GCP VM) triggers pipeline

Clones repo

Builds Docker images for frontend & backend

Runs security scans:

SonarQube (SAST)

Trivy (SCA)

OWASP ZAP (DAST)

Pushes Docker images to Google Artifact Registry

Deploys to GKE using kubectl and YAML manifests

NGINX Ingress Controller (on GKE) handles external access

Google Cloud Load Balancer routes traffic to the Ingress

Prometheus and Grafana monitor app and cluster health

Slack sends notifications on pipeline results and alerts

🛡️ Security Integration
✅ Static Code Analysis (SAST) with SonarQube
✅ Dependency Vulnerability Scan (SCA) with Trivy
✅ Dynamic App Security Testing (DAST) with OWASP ZAP
✅ Jenkins uses credential bindings to secure secrets
✅ Network exposure is minimized via NGINX Ingress rules and firewall policies

## 📊 Monitoring Stack

Prometheus scrapes metrics from containers and nodes

Grafana visualizes performance dashboards

Alerts can be configured to notify Slack

## 🔧 Infrastructure Notes

Jenkins, SonarQube, Prometheus, and Grafana run on the same GCP Compute Engine VM

GKE handles production-grade deployment and scaling

Artifact Registry securely stores Docker images for GKE to pull

## 🛠️ Requirements

Google Cloud Platform subscription

Google Compute Engine VM (Ubuntu 22.04 LTS)

Google Kubernetes Engine (GKE) cluster

Google Artifact Registry

Domain or public IP for Ingress

Slack Webhook configured for Jenkins

## 🙏 Credits :

Frontend Source: https://github.com/harshmangalam/facebook-clone-app-react-client.git
Backend Source: https://github.com/harshmangalam/facebook-clone-app-nodejs-server.git

These apps are not developed by me — credit goes to their original authors.

## 👨‍💻 Maintainer

Name: Khalid Nazih
Role: DevOps & Network Engineer
LinkedIn: linkedin.com/in/khalid-nazih-b5618b2b6

