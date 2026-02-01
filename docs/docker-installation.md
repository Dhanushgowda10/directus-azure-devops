# Docker & Docker Compose Installation

## Install Docker

SSH into your Azure VM and run the following commands:

```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER
newgrp docker
```

## Install Docker Compose

```bash
sudo apt install -y docker-compose
```

## Verify Installation

Verify both Docker and Docker Compose are installed correctly:

```bash
docker --version
docker-compose --version
```

Both commands should return version numbers, confirming successful installation.
