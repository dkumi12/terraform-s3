# Terraform Project 1 – S3 Storage Foundation

This repository contains **Project 1** of a 5-project Terraform series focused on building cloud infrastructure **from first principles to production-ready patterns**.

The goal of this project is to learn and apply **Terraform fundamentals** by provisioning a secure, production-grade Amazon S3 bucket using Infrastructure as Code.

---

## 📌 Project Overview

What started as “just an S3 bucket” quickly became an exercise in **designing secure, reproducible infrastructure**.

This project provisions:
- An Amazon S3 bucket
- With encryption enabled
- Versioning turned on
- All public access blocked
- Structured tagging
- Reusable outputs for integration with future resources

The emphasis is not speed, but **clarity, intent, and correctness**.

---

## 🧠 Key Lessons

### 1. Infrastructure as Intent
Terraform is not about issuing commands.  
It is about **describing the desired end state** and allowing Terraform to determine the execution order.

---

### 2. `terraform plan` Is a Thinking Tool
`terraform plan` is where infrastructure decisions become visible.
It allows you to review *exactly* what will change before committing anything to AWS.

---

### 3. State Is Everything
Terraform state represents the source of truth for your infrastructure.
Losing or mismanaging state means losing control of your system.

This project reinforced why:
- State should never be committed to Git
- Remote state and locking matter in production

---

### 4. Security by Default
Even a simple storage resource requires decisions around:
- Encryption
- Access control
- Versioning
- Metadata and tagging

Infrastructure as Code forces these decisions **before deployment**, not after incidents.

---

## 🧱 Resources Created

This project creates the following Terraform-managed resources:

- `aws_s3_bucket`
- `aws_s3_bucket_public_access_block`
- `aws_s3_bucket_server_side_encryption_configuration`
- `aws_s3_bucket_versioning`

Total:
- 4 Terraform resources  
- ~70 lines of Terraform code  
- Deployment time under 30 seconds  

---

## 📁 Repository Structure

```

.
├── main.tf              # Core resource definitions
├── variables.tf         # Input variables
├── outputs.tf           # Reusable outputs
├── providers.tf         # Provider configuration
├── .terraform.lock.hcl  # Provider version locking
├── .gitignore           # Terraform and OS hygiene
└── README.md

````

---

## 🚀 How to Use

### Prerequisites
- Terraform installed
- AWS credentials configured locally

### Steps

```bash
terraform init
terraform plan
terraform apply
````

To destroy resources:

```bash
terraform destroy
```

---

## 🔒 Git Hygiene (Important)

This repository intentionally does **not** commit:

* `.terraform/` directory
* Terraform state files
* Provider binaries

If Terraform can regenerate it, it does not belong in Git.

---

## 🔭 What’s Next

This project is the foundation for the rest of the series.

Upcoming projects will build on this work to include:

* Custom VPC networking
* Public and private subnets
* Load balancing and auto scaling
* Modular Terraform architecture
* Remote state with locking

---

## ✍🏽 Author

**David Osei Kumi**
Cloud Engineering and Infrastructure as Code
Building in public

---

## 📄 License

This project is for learning and demonstration purposes.

```
