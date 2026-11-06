# Code Editor – Docker & AWS Deployment

A web-based code editor built with **React.js** and deployed using **Docker and AWS**. This project demonstrates containerization, cloud deployment, and modern full-stack application development.

## 🚀 Project Overview

The Code Editor is a browser-based application that provides an interactive environment for writing and editing code. The application is containerized using Docker and deployed on Amazon Web Services (AWS) to make it accessible over the internet.

## ✨ Features

- Interactive browser-based code editor.
- React.js frontend.
- Node.js backend (if enabled in your deployment).
- Docker-based application containerization.
- Docker Buildx for building container images.
- Amazon Elastic Container Registry (ECR) for storing Docker images.
- AWS EC2 for hosting application containers.
- AWS Application Load Balancer (ALB) for routing incoming traffic.
- Cloud-based application accessibility.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| React.js | Frontend development |
| JavaScript | Application logic |
| Node.js | Backend runtime |
| Docker | Containerization |
| Docker Buildx | Multi-platform image building |
| Amazon ECR | Docker image registry |
| Amazon EC2 | Cloud hosting |
| AWS ALB | Load balancing |
| Git & GitHub | Version control |

## 📁 Project Structure

```text
Docker-AWS/
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── Dockerfile
│
├── backend/
│   ├── server.js
│   ├── package.json
│   └── Dockerfile
│
├── docker-compose.yml
└── README.md
```

## ⚙️ Run Locally

### Prerequisites

- Node.js and npm
- Docker Desktop
- Git

### 1. Clone the repository

```bash
git clone https://github.com/Ritikrak/Code-Editor--Docker-AWS-.git
```

```bash
cd Code-Editor--Docker-AWS-
```

### 2. Build Docker Images

Build the backend image:

```bash
docker buildx build --platform linux/amd64 -t docker-aws/server:latest --load ./backend
```

Build the frontend image:

```bash
docker buildx build --platform linux/amd64 -t docker-aws/client:latest --load ./frontend
```

### 3. Run Docker Containers

Backend:

```bash
docker run -d -p 3000:3000 --name server-container docker-aws/server:latest
```

Frontend:

```bash
docker run -d -p 5173:5173 --name client-container docker-aws/client:latest
```

### 4. Access the Application

- Frontend: http://localhost:5173
- Backend: http://localhost:3000

## ☁️ AWS Deployment Architecture

The application deployment uses the following AWS services:

1. **Docker:** Containerizes the application.
2. **Amazon ECR:** Stores the Docker images.
3. **Amazon EC2:** Hosts and runs the application containers.
4. **Application Load Balancer:** Distributes incoming application traffic to registered targets.

### Deployment Workflow

```text
React Application
       |
       v
Docker Image Build
       |
       v
Amazon ECR
       |
       v
Amazon EC2
       |
       v
Docker Containers
       |
       v
Application Load Balancer
       |
       v
Users Access Application
```

### AWS Deployment Steps

1. Create an Amazon ECR repository.
2. Authenticate Docker with Amazon ECR.
3. Build and tag Docker images.
4. Push images to Amazon ECR.
5. Launch an EC2 instance.
6. Install Docker on EC2.
7. Pull Docker images from ECR.
8. Run the application containers.
9. Configure an Application Load Balancer.
10. Register EC2 instances with the target group and configure health checks.
11. Access the application using the ALB DNS endpoint.

## 🔐 Security Considerations

- Use IAM roles and least-privilege permissions.
- Avoid storing AWS credentials in source code.
- Keep environment variables and secrets outside Docker images.
- Restrict EC2 inbound traffic to the required ports.
- Allow application traffic through the ALB security group.

## 📌 Learning Outcomes

Through this project, I gained practical experience in:

- Containerizing React applications using Docker.
- Building Docker images with Docker Buildx.
- Managing and publishing container images using Amazon ECR.
- Deploying containerized applications on AWS EC2.
- Configuring Application Load Balancers and target groups.
- Understanding cloud deployment and container networking.

## 👨‍💻 Author

**Ritik Raj**

- GitHub: [@Ritikrak](https://github.com/Ritikrak)

---

⭐ If you find this project useful, consider giving it a star!
