# Continuous Integration: Docker Pipeline on GitHub Actions

## Overview
This project documents my journey in implementing **Continuous Integration (CI)** using **Docker** and **GitHub Actions**.  
The focus was to build a Docker image of our Go application automatically and run tests in multiple environments, ensuring that the application works regardless of the OS or setup.

---

## 💻 Technologies used
<p align="center">
  <a href="https://www.docker.com/" target="_blank"><img src="https://img.shields.io/badge/Docker-blue?logo=docker&logoColor=white&labelColor=2b6cb0" alt="Docker Badge"></a>
  <a href="https://github.com/features/actions" target="_blank"><img src="https://img.shields.io/badge/GitHub_Actions-2088ff?logo=github&logoColor=white&labelColor=1b6eff" alt="GitHub Actions Badge"></a>
  <a href="https://go.dev/" target="_blank"><img src="https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white&labelColor=0a7c99" alt="Go Badge"></a>
</p>

---

## Objectives
- **Run CI on any branch:** Ensure tests are available during development, not just on main.  
- **Cross-platform testing:** Use matrix strategies to test the application on multiple operating systems.  
- **Dockerized application:** Build a Docker image with proper environment variables, ports, and commands.  
- **Flexible database configuration:** Enable the app to connect to any database via environment variables.  
- **Secure CI secrets:** Use GitHub Actions secrets for passwords and sensitive data.  
- **Artifact management:** Save compiled binaries and test results for reuse, avoiding unnecessary rebuilds.

---

## 🧠 Key Learning Areas

### ⚙️ GitHub Actions & CI Pipelines
- Configure the CI to run on **any branch**, not just main.  
- Use **matrix strategies** to test across multiple OS (Ubuntu, Windows, macOS).  
- Understand the limitation of matrix strategies — they only apply to the job where they are declared.  

### 🐳 Docker & Dockerfile
- Create a **Dockerfile** defining the base image, ports, and commands for the application.  
- Configure the application to read **environment variables**, allowing flexible database connections.  
- Set environment variables inside the Docker image for consistency with development setups.  

### 🔒 Security & Secrets
- Store credentials securely using **GitHub Actions secrets**.  
- Reference secrets in workflows without exposing sensitive information in the code.  
- Log in to Docker Hub automatically from CI using secure secrets.  

### 📦 Automation & Artifacts
- Automate Docker image creation in CI using a dedicated workflow (e.g., `Docker.yml`).  
- Save build outputs and binaries as **artifacts** for reuse.  
- Download artifacts to avoid redundant compilation, saving time in the pipeline.


