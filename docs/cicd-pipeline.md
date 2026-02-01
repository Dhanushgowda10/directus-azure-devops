# GitHub Actions CI/CD Pipeline

## Pipeline Overview

The GitHub Actions pipeline validates the Directus deployment is publicly accessible and functioning correctly.

## Pipeline Stages

### 1. Validate Stage

**Job**: `validate_config`

Validates the `docker-compose.yml` configuration syntax:

```bash
docker-compose config
```

### 2. Test Stage

**Jobs**:
- `health_check`: Performs HTTP connectivity test
- `capture_homepage`: Downloads Directus homepage HTML

```bash
curl -I http://<VM_IP>
curl http://<VM_IP> -o directus_homepage.html
```

### 3. Report Stage

**Job**: `generate_report`

Generates deployment summary report:

```
# Deployment Report
- Azure VM deployment validated
- Directus accessible via HTTP
```

## Artifacts Generated

- `directus_homepage.html`: Homepage HTML content
- `deployment_report.md`: Deployment summary

## Running the Pipeline

The pipeline automatically runs on each push to the `main` branch.

### Manual Trigger

Go to Actions tab and click "Run workflow"

## Monitoring Pipeline

1. Go to GitHub repository
2. Click "Actions" tab
3. Select the latest workflow run
4. View logs and artifacts
