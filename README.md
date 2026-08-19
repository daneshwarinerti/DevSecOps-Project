# DevSecOps CI/CD Pipeline


A secure CI/CD pipeline for a Python Flask application using GitHub Actions, Docker, and AWS.


The project demonstrates how security checks can be integrated into the software delivery process and how a Dockerized application can be automatically deployed to Amazon ECS Fargate.


## 🚀 Features


- Automated CI/CD using GitHub Actions
- Python dependency vulnerability scanning with pip-audit
- Secret detection using Gitleaks
- Automated testing with pytest
- Docker image build
- Container vulnerability scanning using Trivy
- Secure AWS authentication using GitHub OIDC
- Docker image storage in Amazon ECR
- Automated deployment to Amazon ECS Fargate
- Application Load Balancer for application access
- Rolling deployment through ECS


## 🛠️ Tech Stack


- Python
- Flask
- Docker
- Git
- GitHub Actions
- pip-audit
- Gitleaks
- Trivy
- Amazon ECR
- Amazon ECS Fargate
- Application Load Balancer
- AWS IAM
- AWS OIDC


## 🔐 Security


Security checks are integrated directly into the CI/CD pipeline.


### Dependency Scan


`pip-audit` checks Python dependencies for known vulnerabilities.


### Secret Scan


`Gitleaks` detects accidentally committed secrets such as credentials, API keys, and tokens.


### Container Scan


`Trivy` scans the Docker image for HIGH and CRITICAL vulnerabilities.


The pipeline is configured to stop when security checks fail.


## 🔄 CI/CD Pipeline


Every push to the `main` branch triggers the pipeline.


```text
Code Push
   ↓
GitHub Actions
   ↓
Dependency Scan
   ↓
Secret Scan
   ↓
Run Tests
   ↓
Docker Build
   ↓
Trivy Security Scan
   ↓
AWS OIDC Authentication
   ↓
Push Image to Amazon ECR
   ↓
Update ECS Task Definition
   ↓
Deploy to ECS Fargate
   ↓
Application Load Balancer
☁️ AWS Deployment

The application is deployed using:

Amazon ECR – stores Docker images
Amazon ECS Fargate – runs the application container
Application Load Balancer – exposes the application
IAM OIDC – provides secure authentication from GitHub Actions

GitHub Actions uses OIDC to assume an AWS IAM role instead of storing long-lived AWS access keys.

🐳 Docker

Build the Docker image:

docker build -t devsecops-app .

Run the application:

docker run -p 5000:5000 devsecops-app

The application runs on:

http://localhost:5000
💻 Run Locally

Clone the repository:

git clone http://github.com/daneshwarinerti/DevSecOps-Project
cd DevSecOps-Project

Create a virtual environment:

python -m venv venv

Activate it on Windows:

venv\Scripts\activate

Install dependencies:

pip install -r requirements.txt

Run the application:

python app.py
📁 Project Structure
DevSecOps-Project/
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── tests/
│
├── app.py
├── Dockerfile
├── requirements.txt
├── sonar-project.properties
└── README.md
📌 Key DevSecOps Concepts

This project demonstrates practical implementation of:

Continuous Integration
Continuous Deployment
Shift-left security
Dependency scanning
Secret scanning
Container security
Security gates
Docker image versioning
AWS OIDC authentication
Automated ECS deployments

👩‍💻 Author

Dhaneshwari Nerti

Information Science and Engineering

DevOps | Cloud | DevSecOps
