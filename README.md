# 🚀 End-to-End DevOps CI/CD Pipeline using Flask, Docker & Jenkins

A production-style Flask Authentication system fully containerized using Docker and deployed on AWS EC2 with automated CI/CD using Jenkins & GitHub Webhooks.

---

## ✨ Features

✅ User Login & Registration  
✅ Password Hashing  
✅ Flask + MySQL Backend  
✅ Nginx Reverse Proxy  
✅ Dockerized Multi-Container Setup  
✅ Jenkins CI/CD Pipeline  
✅ GitHub Webhook Auto Deployment  
✅ Persistent MySQL Storage  
✅ AWS EC2 Deployment  

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| 🐍 Flask | Backend Framework |
| 🐬 MySQL | Database |
| 🐳 Docker | Containerization |
| ⚙️ Jenkins | CI/CD Automation |
| 🌐 Nginx | Reverse Proxy |
| ☁️ AWS EC2 | Cloud Hosting |

---

        ##⚙️ Docker Architecture
                ┌─────────────┐
                │   Jenkins   │
                └──────┬──────┘
                       │
                       ▼
                GitHub Webhook
                       │
                       ▼
│  Nginx   │──▶│ Flask App │──▶│  MySQL   │



##🔄 CI/CD Workflow

GitHub Push
     ↓
GitHub Webhook
     ↓
Jenkins Pipeline
     ↓
Docker Build & Deploy
     ↓
Live Application 🚀


##🔧 Jenkins CI/CD Setup

Features
Automatic Deployment on Git Push
GitHub Webhook Integration
Docker Compose Build & Deployment
Secret .env Management using Jenkins Credentials


##🐳 Running Locally

1 Clone Repository

    git clone https://github.com/your-username/flask-sql-docker.git

    cd flask-sql-docker


2 Create .env file in that dir

    MYSQL_HOST=your_host_name

    MYSQL_USER=your_user_name
    MYSQL_PASSWORD=your_user_password

    MYSQL_ROOT_PASSWORD=your_root_password

    MYSQL_DATABASE=your_db_name
    SECRET_KEY=your_secret_key 


3. start container using compose.yml

   docker-compose up -d --build


4. start jenkins container (it is inside jenkins dir)

   docker-compose up -d --build


6. update security group for e2 and then run jenkins on :8080

7. put your credentials (.env) inside jenkins credtentials > secret file 


8. Run it 

    http://localhost or http://your_aws_ip (if you run inside aws)


9. For jenkins-github pipeline you need to enable webhook in Github 


##🧠 What I Learned

Through this project I learned:

    Docker Networking
    Multi-Container Architecture
    Persistent Volumes
    Jenkins Pipelines
    GitHub Webhooks
    CI/CD Concepts
    Linux & Docker Debugging
    MySQL Container Initialization
    Environment Variable Management
    Reverse Proxy Setup with Nginx       

