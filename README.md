# Containerized MEAN Stack Deployment (DevOps )

## Overview

This project demonstrates a complete DevOps workflow by containerizing and deploying a full-stack MEAN (MongoDB, Express, Angular, Node.js) application on AWS EC2 using Docker, Docker Compose, Nginx reverse proxy, and a CI/CD pipeline with GitHub Actions.

The application allows users to perform CRUD operations on tutorials (create, read, delete, search).

---

## Tech Stack

* **Frontend:** Angular 15
* **Backend:** Node.js + Express
* **Database:** MongoDB
* **Containerization:** Docker
* **Orchestration:** Docker Compose
* **Cloud:** AWS EC2 (Ubuntu Server)
* **Reverse Proxy:** Nginx
* **CI/CD:** GitHub Actions
* **Registry:** Docker Hub

---

## Architecture

1. Angular frontend served via Nginx container
2. Express backend API container
3. MongoDB database container
4. Nginx reverse proxy exposes application on port 80
5. GitHub Actions automatically builds and deploys on push

---

## Features Implemented

* Multi-container Docker deployment
* Container networking
* Persistent MongoDB volume
* Reverse proxy configuration
* Public cloud deployment
* Automated CI/CD pipeline
* Automatic redeployment on code push

---

## Deployment Steps (Summary)

### Local Setup


docker compose up -d


### Cloud Deployment

* Created AWS EC2 Ubuntu instance
* Installed Docker & Docker Compose
* Pulled images from Docker Hub
* Configured Nginx reverse proxy

### CI/CD Pipeline

On every push to `main` branch:

1. GitHub Actions builds Docker images
2. Pushes images to Docker Hub
3. Connects to EC2 via SSH
4. Pulls latest images
5. Restarts containers automatically

---

## Live Application

Accessible via:

```
http://<EC2-PUBLIC-IP>
```

---

## Proof of Deployment

### CI/CD Pipeline

![CI/CD Success](screenshots/cicd/workflow.png)

### Docker Hub Images

![Docker Hub Repositories](screenshots/dockerhub/dockerhub-repos1.png)
![Docker Hub Repositories](screenshots/dockerhub/dockerhub-repos2.png)

### Running Containers on AWS

![Docker Containers](screenshots/containers/docker-ps.png)

### Application UI

![Application Home](screenshots/deployment/app_1.png)

### Nginx Reverse Proxy

![Nginx Running](screenshots/nginx/nginx-status.png)

---

## Step-by-Step Deployment 

### 1. Clone Repository

```
git clone https://github.com/safalgawande/containerized-mean-app.git
cd containerized-mean-app
```

### 2. Run Locally Using Docker Compose

```
docker compose up -d --build
```

Application will be available at:

```
http://localhost:8081
```

### 3. Cloud Deployment (AWS EC2)

* Launch Ubuntu EC2 instance
* Install Docker & Docker Compose
* Pull images from Docker Hub
* Run docker-compose.yml

### 4. Reverse Proxy

Nginx configured to route port 80 → frontend container.

### 5. CI/CD

GitHub Actions automatically:

* Builds Docker images
* Pushes to Docker Hub
* SSH into server
* Pulls new images
* Restarts containers


---

## Learning Outcomes

* Hands-on Docker containerization
* Multi-service orchestration
* Cloud deployment on AWS
* Reverse proxy configuration
* Building a CI/CD pipeline
* Automated production deployment

