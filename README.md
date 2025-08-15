# MLOps Pipeline with Python, AWS, and Docker

This repository implements an **end-to-end MLOps pipeline** following the tutorial  
[MLOps Pipeline with Python, AWS, and Docker](https://www.youtube.com/watch?v=gwNPV882tkc).  
The project demonstrates how to package a machine learning model into a Docker container, push it to AWS ECR, and deploy it automatically using GitHub Actions.

---

## 📌 Features
- **Machine Learning model packaging** with Python
- **Docker containerization**
- **Continuous Integration & Deployment (CI/CD)** via GitHub Actions
- **AWS Elastic Container Registry (ECR)** for storing images
- **Automated container deployment**
- **Reusable workflow for production updates**

---

## 🛠 Tech Stack
- **Python 3.9+**
- **Docker**
- **AWS ECR**
- **GitHub Actions**
- **Bash scripting**

---

## 📂 Project Structure
├── app/ # ML model code and API logic
├── requirements.txt # Python dependencies
├── Dockerfile # Docker build instructions
├── .github/workflows/ # CI/CD pipeline definitions
└── README.md

---

## ⚙️ Prerequisites
Before running this project, ensure you have:
- [Docker](https://docs.docker.com/get-docker/) installed
- An **AWS account** with:
  - ECR repository created
  - IAM user with `AmazonEC2ContainerRegistryFullAccess`
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) configured locally
- **GitHub repository secrets** set:
  - `AWS_ACCESS_KEY_ID`
  - `AWS_SECRET_ACCESS_KEY`
  - `AWS_REGION`
  - `AWS_DEFAULT_REGION`

---

## 🚀 Setup & Run Locally
**Clone the repository**
   ```bash
   git clone ``
   cd mlops-pipeline

##  Continuous Deployment

This project uses **GitHub Actions** for automatic deployment.

** How it works: **
1. **GitHub Actions Workflow**  
   - Triggered automatically when you push changes to the `main` branch.  
   - Stops and removes any running `cnncls` container to avoid conflicts.  
   - Builds a new Docker image from your code.  

2. **AWS Connection**  
   - The workflow logs into AWS using the `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` stored in GitHub Secrets.  
   - The new Docker image is pushed to your AWS **Elastic Container Registry (ECR)**.  

3. **Final Deployment**  
   - AWS pulls the latest image from ECR and runs it as a container.  
   - The updated application is now live and ready to serve requests.  


