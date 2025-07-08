# 🚀 AWS Cloud Deployment Project

This project showcases a complete end-to-end deployment of a containerized full-stack application using key AWS services including **EC2**, **RDS (PostgreSQL)**, **S3**, **Elastic Load Balancer**, and **Infrastructure as Code** via **Terraform**.


## 📁 Project Structure
.
├── backend/ # Backend app (Node.js, Flask, etc.)
├── frontend/ # Frontend app (React, Vue, etc.)
├── infrastructure/ # IaC Terraform files
│ ├── main.tf
│ ├── versions.tf
│ ├── terraform.tfstate
│ └── terraform.tfstate.backup
├── Dockerfile # Docker config for app
├── .env # Environment variables
└── README.md

![Screenshot](https://github.com/user-attachments/assets/cc76bda5-0407-4451-83f8-d8e2d811265c)

---

## ✅ Features

- ☁️ EC2 instance with Dockerized deployment
- 📦 S3 integration for static assets (avatars, uploads)
- 🛢️ PostgreSQL database via Amazon RDS
- ⚖️ Load balancing with Elastic Load Balancer (ELB)
- 🔐 Secure access via Security Groups
- 🔁 Repeatable deployments with Terraform
- 🖥️ Local Docker testing prior to cloud deployment

---

## 🧱 AWS Services Used

| Service | Purpose |
|--------|---------|
| EC2 | Host Dockerized app |
| RDS (PostgreSQL) | Managed database backend |
| S3 | Store and serve static files (e.g., avatars) |
| ELB | Distribute traffic to EC2 instance |
| Terraform | Define and deploy infrastructure |

---

## 🛠️ Setup & Deployment

🔹 1. Clone the Repo
```bash
git clone https://github.com/yourusername/aws-fullstack-deployment.git
cd aws-fullstack-deployment

🔹 2. Build Docker Locally
docker build -t my-app .
docker run -p 3000:3000 --env-file .env my-app

🔹 3. Provision Infrastructure with Terraform
cd infrastructure/
terraform init
terraform plan
terraform apply

🔹 4. Deploy on EC2
SSH into your EC2 instance and run:
docker build -t my-app .
docker run -d -p 80:3000 --env-file .env my-app

🔹 5. Upload Static Files to S3
aws s3 cp ./assets/ s3://your-s3-bucket-name/ --recursive

📂 Terraform Files Explained
File	Description
main.tf	Defines EC2, RDS, S3, Security Groups
versions.tf	Required provider versions
terraform.tfstate	Current state of infrastructure
terraform.tfstate.backup	Backup of previous state

🌐 Application Architecture
[ Client ] → [ Elastic Load Balancer ] → [ EC2 w/ Dockerized App ]
                                 │
                      [ RDS PostgreSQL Database ]
                                 │
                        [ S3 Static Storage ]

Images
![image](https://github.com/user-attachments/assets/5bd228d4-581c-4e14-aa01-dba2a8ab88ae)
![Screenshot 2025-06-25 at 13 46 39](https://github.com/user-attachments/assets/ecd893cb-067d-47bb-b5a9-85277d7fa011)
<img width="581" alt="Screenshot 2025-06-17 at 10 32 12" src="https://github.com/user-attachments/assets/6194234c-f122-44a6-8c84-e4d2d1af263e" />
![Screenshot 2025-06-12 at 15 38 14](https://github.com/user-attachments/assets/e9ac2df6-9231-4291-8260-ccd6aed2e266)



🔐 Security
Security Groups used to allow only necessary ports (e.g., 22, 80, 5432)
No hardcoded secrets — environment variables via .env file
Encrypted RDS instance and restricted S3 access

🧠 Lessons Learned
Writing and maintaining Terraform IaC
Debugging EC2 ↔ RDS connectivity
Managing app state across local Docker and AWS
Configuring secure storage in S3

🏷️ Badges
<!-- Project Badges -->
![Status](https://img.shields.io/badge/Project%20Status-Completed-brightgreen)
![AWS Services](https://img.shields.io/badge/AWS-EC2%20|%20RDS%20|%20S3-blue?logo=amazonaws)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![Terraform](https://img.shields.io/badge/IaC-Terraform-5c4ee5?logo=terraform)
![CDK](https://img.shields.io/badge/IaC-AWS%20CDK-orange?logo=amazonaws)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-blue?logo=postgresql)
![Load Balancer](https://img.shields.io/badge/Elastic%20Load%20Balancer-Enabled-yellowgreen)
![S3](https://img.shields.io/badge/Storage-Amazon%20S3-orange?logo=amazonaws)
![Secure](https://img.shields.io/badge/Security-Security%20Groups%20Enabled-important)
![License](https://img.shields.io/badge/License-MIT-lightgrey)
![Portfolio](https://img.shields.io/badge/Portfolio-Project-success)

📄 License
This project is licensed under the MIT License. See the LICENSE file for details.

🙋‍♀️ Author
Sumi Dhakal


