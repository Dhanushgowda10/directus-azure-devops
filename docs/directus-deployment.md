# Directus Deployment using Docker Compose

## Project Structure

The deployment uses the `docker-compose.yml` configuration file which defines two services:

- **PostgreSQL**: Database service
- **Directus**: CMS application

## Services Configuration

### PostgreSQL Service

- Image: `postgres:15`
- Database: `directus`
- User: `directus`
- Password: `directuspass`
- Volume: Persistent data storage

### Directus Service

- Image: `directus/directus:latest`
- Port Mapping: `80:8055`
- Admin Email: `admin@example.com`
- Admin Password: `Admin@123`
- Database Connection: Connects to PostgreSQL service

## Deployment Steps

### 1. SSH into Azure VM

```bash
ssh -i /path/to/key azureuser@<VM_IP>
```

### 2. Clone or Upload Configuration

Ensure `docker-compose.yml` is in your working directory.

### 3. Start Services

```bash
docker-compose up -d
```

### 4. Verify Deployment

```bash
docker ps
```

You should see both `directus_postgres` and `directus` containers running.

## Accessing Directus

Open your browser and navigate to:

```
http://<VM_PUBLIC_IP>
```

Login with:
- Email: `admin@example.com`
- Password: `Admin@123`
