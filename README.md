# Spring Boot + React Full-Stack Application (Dockerized)

This project is a clone from https://github.com/PouyaPouryaie/react-springboot-CRUD. This demonstrates how to containerize a **Spring Boot backend**, **React frontend**, and **PostgreSQL database** using **Docker** and **Docker Compose**. <br/>
The setup ensures:  
✅ **Backend and database ports are not exposed** to the outside world.  
✅ **Nginx acts as a reverse proxy**, forwarding API requests to Spring Boot.  
✅ **Docker Compose** manages all services for easy deployment.  
✅ **CI/CD automation using GitLab CI/CD** with a **self-hosted EC2 runner**.  

---

## 🏗 Project Architecture

The application follows a **three-tier architecture**:

1️⃣ **Frontend (React + Nginx)** → Handles UI and user interactions.  
2️⃣ **Backend (Spring Boot)** → Processes API requests and communicates with the database.  
3️⃣ **Database (PostgreSQL)** → Stores and manages application data.  

![diagram-export-13-2-2025-5_42_19-pm](https://github.com/user-attachments/assets/d04ef1d5-1ad6-42e8-96f7-c8692d884701)

---

## 🚀 Getting Started

### 1️⃣ Prerequisites
Make sure you have:
- [Docker](https://www.docker.com/) installed  
- [Docker Compose](https://docs.docker.com/compose/) installed  

### 2️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/springboot-react-docker.git
cd springboot-react-docker
```

### 3️⃣ Run the Application
```bash
docker compose up --build -d
```
✅ The **React frontend** will be available at `http://localhost`.  
✅ The **backend (Spring Boot API)** is only accessible inside the Docker network.  
✅ The **PostgreSQL database** is only accessible within the backend container.  


### 4️⃣ Stopping the Application
To stop all services:
```bash
docker compose down
```
To remove containers **including database volumes**:
```bash
docker compose down -v
```

---

## 🔄 CI/CD Automation with GitLab

The application is configured with **GitLab CI/CD** for automated builds and deployments.

### 📜 CI/CD Pipeline (`.gitlab-ci.yml`)

The pipeline:  
✅ **Builds frontend & backend images**  
✅ **Pushes them to Docker Hub**  
✅ **Deploys them on EC2 using Docker Compose**  

👉 **Refer to the `.gitlab-ci.yml` file for full details.**  

---

## 📝 Additional Configurations

### 🔄 Reverse Proxy with Nginx
The `nginx.conf` file ensures:  
✅ **API requests (`/api/`) are proxied to `fullstack-backend:8080`**  
✅ **CORS headers allow secure frontend-backend communication**  

👉 **Refer to `nginx.conf` for full configuration.**  

---

## 📖 Blog Post
For a detailed explanation, check out my blog post:  
👉 **[Dockerizing a Spring Boot + React Application](#)** *(Insert blog link here)*  

---

## 📚 Resources
- [Docker Documentation](https://docs.docker.com/)  
- [Spring Boot with Docker](https://spring.io/guides/gs/spring-boot-docker/)  
- [Nginx Reverse Proxy Guide](https://www.nginx.com/resources/wiki/start/)  
- [GitLab CI/CD](https://docs.gitlab.com/ee/ci/)  
