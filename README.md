# Directus Deployment on Azure using Docker & GitHub Actions

## Overview

This project demonstrates the deployment of **Directus (Headless CMS)** on an **Azure Virtual Machine** using **Docker and Docker Compose**, along with a **GitHub Actions CI/CD pipeline** to validate the deployment. The Directus application is publicly accessible via HTTP using the VM's public IP address. The CI/CD pipeline performs automated configuration validation and health checks to ensure the deployment is working correctly.

---

## Tech Stack

- Cloud Provider: **Microsoft Azure**
- Virtual Machine OS: **Ubuntu 22.04 LTS**
- Containerization: **Docker, Docker Compose**
- Database: **PostgreSQL**
- Application: **Directus**
- CI/CD: **GitHub Actions**

---

## Live Application Access

```
http://<YOUR_AZURE_VM_PUBLIC_IP>
```

---

## Project Deliverables

| Deliverable | Description |
|------------|-------------|
| Working Directus Site | Publicly accessible via Azure VM public IP |
| GitHub Repository | Contains all configuration files and documentation |
| CI/CD Pipeline | GitHub Actions pipeline validating the deployment |
| Implementation Documentation | Step-by-step implementation guides |

---

## Implementation Steps

### Step 1: Azure Virtual Machine Setup

Creation of a free-tier Azure account, launching an Ubuntu VM, and configuring networking.

➡️ [Azure VM Setup Guide](docs/azure-vm-setup.md)

---

### Step 2: Docker & Docker Compose Installation

Installation and verification of Docker and Docker Compose on the Azure VM.

➡️ [Docker Installation Guide](docs/docker-installation.md)

---

### Step 3: Directus Deployment using Docker

Deployment of Directus and PostgreSQL using Docker Compose and exposing the application via HTTP.

➡️ [Directus Deployment Guide](docs/directus-deployment.md)

---

### Step 4: CI/CD Pipeline using GitHub Actions

Implementation of a CI/CD pipeline that validates the deployment using automated checks.

➡️ [GitHub Actions CI/CD Pipeline](docs/cicd-pipeline.md)

---

## CI/CD Pipeline Overview

The GitHub Actions pipeline consists of the following stages:

### Validate Stage
- Validates the `docker-compose.yml` configuration syntax.

### Test Stage
- Performs HTTP health check on the Directus application.
- Downloads the Directus homepage HTML.

### Report Stage
- Generates a deployment summary report.

### Pipeline Artifacts
- `directus_homepage.html`
- `deployment_report.md`

---

## Verification Checklist

- ✅ Directus application accessible via browser
- ✅ Admin login successful
- ✅ GitHub Actions pipeline executes successfully
- ✅ Artifacts generated and stored by pipeline

---

## Notes

- Directus is exposed on **port 80** for clean HTTP access.
- Sensitive environment variables should be stored securely and excluded from version control.
- This project follows cloud and containerization best practices.

---

## Author

**Dhanush Gowda**
