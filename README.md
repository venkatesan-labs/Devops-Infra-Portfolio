# DevOps Infra Portfolio — Venkatesan

                     ┌───────────────────────────┐
                     │       GitHub Repo          │
                     │ Devops-Infra-Portfolio     │
                     └──────────────┬────────────┘
                                    │
                            Webhook triggers
                                    │
                     ┌──────────────▼──────────────┐
                     │           Jenkins            │
                     │  (CI/CD Pipeline Engine)     │
                     │ - Checkout Code              │
                     │ - Build Docker Image         │
                     │ - Push Image (optional)      │
                     │ - Deploy Container           │
                     └──────────────┬──────────────┘
                                    │
                 ┌──────────────────┴──────────────────┐
                 │     Docker Host / Deployment Target  │
                 │   (Local VM / AWS EC2 / Cloud VM)    │
                 │                                      │
                 │  Docker-run → Portfolio Site         │
                 │  Port 80/8080 exposed for HTTP        │
                 └──────────────────────────────────────┘


## 📌 Architecture Explained

### 1️⃣ **Source Control (GitHub)**
Your portfolio source code resides here. Jenkins watches for changes.

### 2️⃣ **Jenkins CI/CD**
Uses `Jenkinsfile` to automate:
- Docker image build
- (Optional) Push to registry
- Deployment tasks

### 3️⃣ **Docker Deployment**
The portfolio site is packaged as a Docker container and deployed to a Docker host.

> The pipeline shows an automated DevOps workflow — code → build → deploy.

---

If you want, I can also generate:
✅ A PNG/SVG architecture image  
✅ A fully rendered Draw.io diagram  
✅ A live CI/CD Jenkins pipeline sample for this specific repo

Just tell me which format you need!
::contentReference[oaicite:3]{index=3}


This repository contains my **DevOps Infrastructure Portfolio**, which includes:

✅ A portfolio website showcasing my DevOps projects  
✅ Dockerized application with CI/CD deployment using Jenkins  
✅ Demonstrates Infrastructure as Code (IaC), containerization & automation

---

## 📁 Repository Structure

| Directory / File | Description |
|------------------|-------------|
| `html/` | Static HTML portfolio pages |
| `Dockerfile` | Builds container image for portfolio site |
| `Jenkinsfile` | CI/CD pipeline definition |
| `README.md` | Project documentation |

---

## 🛠️ Technologies Used

- **Docker** — Containerization  
- **Jenkins** — CI/CD automation  
- **HTML, CSS, JS** — Portfolio UI  
- **GitHub** — Source control  
- **AWS / Cloud (Optional)** — Deployment target

---

## 🚀 Features

✔ Static portfolio website to present DevOps projects  
✔ Docker image build and container deployment  
✔ Automated Jenkins pipeline for build & deploy  
✔ CI/CD best-practice demonstration

---

## 📦 How it Works

1. **Source code** is stored in GitHub.  
2. **Jenkins** uses `Jenkinsfile` to orchestrate CI/CD:
   - Build Docker image using `Dockerfile`
   - Run tests if any (extendable)
   - Deploy the application container  
3. **Deployment** can be to:
   - Local Docker host
   - AWS EC2 instance running Docker
   - Kubernetes cluster (optional future enhancement)

---

## 📌 Installation & Usage

1. Clone the repository  
   ```bash
   git clone https://github.com/kodecloud95/Devops-Infra-Portfolio-Venkatesan.git

2. Build Docker image

   docker build -t devops-portfolio .

3. Run container

   docker run -d -p 8080:80 devops-portfolio


   Visit: http://localhost:8080


📈 CI/CD (Jenkins Pipeline)

Pipeline steps (example — defined in Jenkinsfile):

Checkout code

Docker build: docker build

Docker push (optional registry)

Deployment to server
