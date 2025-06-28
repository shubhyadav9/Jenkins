# Jenkins CI/CD Pipeline with Maven, Docker & Kubernetes

This project automates the end-to-end CI/CD process for a Java web application using **Jenkins**, **Maven**, **Docker**, and **Kubernetes**. It supports multi-environment deployment (Dev, QA, Prod), integrates Docker Hub authentication, and uses SSH and `kubectl` commands for remote deployment and scaling.

## 🚀 Features

- Source code checkout from GitHub
- Maven-based application build
- Docker image creation and push to Docker Hub
- Deployment to:
  - Docker-based Dev & QA environments
  - Kubernetes-based Production environment
- QA environment smoke testing
- Manual approval gate before production deployment
- Automated email notification on failure

## 🛠️ Technologies Used

- Jenkins (Pipeline as Code - `Jenkinsfile`)
- Maven
- Docker & Docker Hub
- SSH Agent Plugin (for remote deployment)
- Kubernetes (kubectl + manifest)
- Shell scripting
- AWS EC2 / Linux servers (assumed)

## 🔐 Prerequisites

- Jenkins with necessary plugins: Git, Pipeline, SSH Agent, Credentials Binding
- Docker installed on all target environments
- Kubernetes access with `kubectl` on production node
- Valid SSH and Docker Hub credentials stored in Jenkins credentials

## 📦 Pipeline Stages

1. **SCM** – Pull code from GitHub
2. **Build** – Package application using Maven
3. **Docker Build** – Create Docker image
4. **Docker Push** – Push image to Docker Hub
5. **Dev Deploy** – Run container on Dev server
6. **QA Deploy** – SSH and deploy to QA server
7. **QA Test** – Run smoke tests
8. **Approval** – Manual user confirmation
9. **Prod Deploy** – Deploy to Kubernetes on Prod

## 📎 How to Run

- Place the `Jenkinsfile` in your GitHub repo root
- Set up Jenkins credentials:
  - Docker Hub password (ID: `DOCKER_HUB_PWD`)
  - SSH key for remote servers (ID: `QA_ENV_SSH_CRED`)
- Trigger a build via Jenkins UI or Git webhook

## 📫 Author

**Shubham Yadav**  
DevOps Engineer  
[LinkedIn](https://www.linkedin.com/in/shubham-yadav-myprofile/)



