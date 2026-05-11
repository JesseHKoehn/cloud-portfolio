# Lab 1 — Azure Resource Group & Storage Account

## 📋 Overview
Deployed my first Azure resources using the Azure CLI entirely 
from the terminal. No portal clicking — pure CLI.

## 🎯 What I Learned
- What a Resource Group is and why it matters
- How to deploy a Storage Account via Azure CLI
- The difference between storage tiers (LRS vs GRS vs ZRS)
- How to verify deployments in the Azure portal
- Cost awareness — always check before deploying

## 🛠️ Tools Used
- Azure CLI
- macOS Terminal
- Git & GitHub

## 📝 Commands Used

### Set default region
```bash
az configure --defaults location=eastus
```

### Create a Resource Group
```bash
az group create --name rg-portfolio-lab1 --location eastus
```

### Create a Storage Account
```bash
az storage account create \
  --name yournamecloudstorage \
  --resource-group rg-portfolio-lab1 \
  --sku Standard_LRS \
  --kind StorageV2
```

### Verify resources
```bash
az group show --name rg-portfolio-lab1
az storage account show --name jhkcloudstorage \
  --resource-group rg-portfolio-lab1
```

## 💰 Cost Analysis
| Resource | Tier | Cost |
|---|---|---|
| Resource Group | N/A | Always free |
| Storage Account | Standard_LRS | $0 — nothing stored |

## 🧹 Cleanup
Deleted resource group after lab to avoid any charges:
```bash
az group delete --name rg-portfolio-lab1 --yes --no-wait
```

## ✅ Outcome
Successfully deployed and verified first Azure resources 
using CLI only. Portfolio documented and pushed to GitHub.