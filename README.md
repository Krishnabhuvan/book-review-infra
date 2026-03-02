# 📘 Book Review Application — Infrastructure

A production-grade cloud infrastructure project built to simulate real-world DevOps workflows. 
This repository contains all Terraform code and Azure DevOps pipeline configuration 
for provisioning the Book Review Application infrastructure on Microsoft Azure.

---

## 🏗️ Architecture
```
GitHub (book-review-infra)
        ↓
Azure DevOps Pipeline
        ↓
Terraform (init → plan → apply)
        ↓
Azure Infrastructure
├── Frontend VM (Ubuntu 22.04)
├── Backend VM (Ubuntu 22.04)
└── MySQL Flexible Server
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Terraform | Infrastructure as Code |
| Azure DevOps | CI/CD Pipeline |
| Microsoft Azure | Cloud Provider |
| Ubuntu 22.04 LTS | VM Operating System |
| MySQL Flexible Server | Database |

---

## 📁 Project Structure
```
terraform/
├── main.tf              # Root module
├── provider.tf          # Azure provider config
├── variables.tf         # Input variables
├── outputs.tf           # Output values (IPs, FQDN)
├── envs/
│   └── dev.tfvars       # Environment-specific values
└── modules/
    ├── compute/         # VM provisioning
    ├── network/         # VNet, Subnet, NSG
    └── database/        # MySQL Flexible Server
```

---

## 🚀 Pipeline Flow

1. Developer pushes changes to `terraform/` folder
2. Azure DevOps pipeline triggers automatically
3. Pipeline downloads SSH public key from Secure Files
4. Terraform initializes, plans, and applies infrastructure
5. Outputs frontend IP, backend IP, and MySQL FQDN

---

## 📸 Screenshots

> Add your pipeline screenshots here

![Infra Pipeline Success](screenshots/infra-pipeline.png)

---

## 📤 Outputs

After successful run:
- `frontend_public_ip` — Frontend VM public IP
- `backend_public_ip` — Backend VM public IP  
- `mysql_fqdn` — MySQL server hostname

---

## 🔐 Security

- SSH keys stored in Azure DevOps Library Secure Files
- Azure credentials managed via Service Principal and Service Connection
- NSG rules restrict inbound traffic to required ports only

---

## 👤 Author

**Karanam Krishna Bhuvan**  
[LinkedIn](#) | [GitHub](https://github.com/Krishnabhuvan)
