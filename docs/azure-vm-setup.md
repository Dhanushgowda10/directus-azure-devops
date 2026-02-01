# Azure Virtual Machine Setup

## Step 1: Create Azure Account

Create a free-tier Azure account using the [Azure Portal](https://portal.azure.com).

## Step 2: Create Virtual Machine

### Recommended Configuration

- **OS**: Ubuntu 22.04 LTS
- **Size**: B1s (eligible for free tier)
- **Authentication**: SSH Key
- **Public IP**: Enabled

### VM Creation Steps

1. Go to Azure Portal > Virtual Machines > Create
2. Select Resource Group (create new if needed)
3. Enter VM Name: `directus-vm`
4. Choose Region closest to you
5. Select Ubuntu 22.04 LTS image
6. Choose B1s size
7. Generate SSH key pair or use existing
8. Click "Create"

## Step 3: Configure Networking

### Inbound Rules (Network Security Group)

Add the following inbound rules:

| Port | Protocol | Source | Purpose |
|------|----------|--------|----------|
| 22 | TCP | Your IP | SSH Access |
| 80 | TCP | Any | HTTP - Directus |
| 443 | TCP | Any | HTTPS (Optional) |

### Steps to Add Rules

1. Go to Virtual Machine > Settings > Networking
2. Click "Add inbound port rule"
3. Configure each rule from the table above
4. Click "Add"

## Step 4: Connect to VM

### Using SSH

```bash
ssh -i /path/to/private/key azureuser@<VM_PUBLIC_IP>
```

Replace `<VM_PUBLIC_IP>` with your VM's public IP address.

## Verification

Once connected, verify the connection:

```bash
uname -a  # Should show Ubuntu 22.04
ip addr   # Should show the VM's IP configuration
```
