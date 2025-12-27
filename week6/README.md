# Terraform Setup & Initialization Guide

This document provides **step-by-step instructions** to install, configure, and initialize **Terraform** on your computer. These instructions are detailed enough to be shared with another person so they can successfully run Terraform from scratch.

---

## Table of Contents
1. Prerequisites
2. Programs to Use
3. Programs **Not** to Use
4. Install Required Software
5. Verify Installations
6. Configure Credentials (AWS Example)
7. Terraform Project Structure
8. Files You Should / Should Not Modify
9. Initialize and Run Terraform
10. Common Commands
11. GitHub Usage & Best Practices
12. Reference Repositories

---

## 1. Prerequisites

- A computer running **Windows 10/11**, **macOS**, or **Linux**
- Internet access
- GitHub account
- Access to a cloud provider (example below uses **AWS**)

---

## 2. Programs to Use (Required)

Use **only** the tools below for Terraform development:

- **Terraform CLI** – Infrastructure as Code tool
- **Git** – Source control
- **Visual Studio Code (VS Code)** – Code editor
- **AWS CLI** (or Azure/GCP CLI depending on provider)
- **Git Bash (Windows)** or **Terminal (macOS/Linux)**

Optional but recommended:
- VS Code Terraform Extension (HashiCorp)

---

## 3. Programs NOT to Use 🚫

Avoid these tools because they cause formatting, execution, or state issues:

- ❌ Notepad / WordPad
- ❌ Microsoft Word
- ❌ Editing Terraform files directly in GitHub UI
- ❌ Manually editing `.terraform/` directory
- ❌ Manually editing `terraform.tfstate`

---

## 4. Install Required Software

### A. Install Git

- Download: https://git-scm.com/downloads
- Accept default settings
- On Windows, ensure **Git Bash** is installed

Verify:
```
git --version
```

---

### B. Install Terraform

- Download: https://developer.hashicorp.com/terraform/downloads
- Add Terraform to your **system PATH**

Verify:
```
terraform --version
```

---

### C. Install Visual Studio Code

- Download: https://code.visualstudio.com/
- Install **HashiCorp Terraform extension** inside VS Code

---

### D. Install AWS CLI (Example Provider)

- Download: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

Verify:
```
aws --version
```

---

## 5. Verify Installations

Run the following commands to confirm everything works:

```
git --version
terraform --version
aws --version
```

All commands should return version numbers without errors.

---

## 6. Configure Credentials (AWS Example)

Configure AWS credentials locally:

```
aws configure
```

You will be prompted for:
- AWS Access Key
- AWS Secret Key
- Default region (example: us-east-1)
- Output format (json)

⚠️ **Never commit credentials to GitHub**

---

## 7. Terraform Project Structure

Recommended directory structure:

```
terraform-project/
├── main.tf
├── variables.tf
├── outputs.tf
├── provider.tf
├── versions.tf
├── terraform.tfvars   (optional)
├── .gitignore
└── README.md
```

---

## 8. Files You SHOULD / SHOULD NOT Modify

### ✅ Safe to Modify

- `main.tf`
- `variables.tf`
- `outputs.tf`
- `terraform.tfvars`
- `README.md`

### ❌ Do NOT Modify

- `.terraform/` directory
- `terraform.tfstate`
- `terraform.tfstate.backup`

Terraform manages these automatically.

---

## 9. Initialize and Run Terraform

### Step 1: Clone the GitHub Repository

```
git clone <repo-url>
cd <repo-name>
```

---

### Step 2: Initialize Terraform

```
terraform init
```

This downloads providers and sets up the working directory.

---

### Step 3: Validate Configuration

```
terraform validate
```

---

### Step 4: Review Execution Plan

```
terraform plan
```

---

### Step 5: Apply Infrastructure

```
terraform apply
```

Type `yes` when prompted.

---

### Step 6: Destroy (When Finished)

```
terraform destroy
```

---

## 10. Common Terraform Commands

```
terraform fmt
terraform init -upgrade
terraform state list
terraform state show <resource>
terraform output
```

---

## 11. GitHub Usage & Best Practices

### Recommended `.gitignore`

```
.terraform/
*.tfstate
*.tfstate.backup
*.tfvars
```

### Standard Git Workflow

```
git status
git add .
git commit -m "Week X HW Assignment"
git push origin main
```

---

## 12. Reference GitHub Repositories

- Terraform Examples (Official):
  https://github.com/hashicorp/terraform

- AWS Terraform Provider:
  https://github.com/hashicorp/terraform-provider-aws

- Terraform Best Practices:
  https://github.com/ozbillwang/terraform-best-practices

---

## Final Notes

- Always run Terraform commands from the **project root directory**
- Never store secrets in GitHub
- Keep commits small and descriptive
- Use one repo per project when possible

---

**Author:** Ervin Kershaw

