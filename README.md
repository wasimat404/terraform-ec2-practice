# 🚀 Terraform EC2 Practice Project

This project demonstrates how to provision an Amazon EC2 instance using **Terraform** and the AWS provider.

It dynamically fetches the latest Amazon Linux 2 AMI and launches a Free Tier–eligible EC2 instance in a specified AWS region.

---

## 📌 Project Overview

This Terraform configuration:

- Configures the AWS provider
- Dynamically retrieves the latest Amazon Linux 2 AMI
- Launches a Free Tier–eligible EC2 instance
- Tags the instance for identification

This project is intended for hands-on DevOps and Infrastructure as Code (IaC) practice.

---

## 🛠 Requirements

- Terraform v1.6+
- AWS Account
- AWS CLI configured (`aws configure`)
- IAM user with EC2 permissions

---

## ⚙️ Configuration

### 1️⃣ Clone the repository

```
git clone https://github.com/wasimat404/terraform-ec2-practice.git
cd terraform-ec2-practice
```

---

### 2️⃣ Initialize Terraform

```
terraform init
```

---

### 3️⃣ Review the Execution Plan

```
terraform plan
```

---

### 4️⃣ Create the EC2 Instance

```
terraform apply
```

Type `yes` when prompted.

---

## 🌍 AWS Region

The project is currently configured to use:

```
us-west-2
```

You can change the region inside the `provider` block in `main.tf`.

---

## 🧠 Free Tier Compatibility

This configuration uses:

```
instance_type = "t3.micro"
```

This instance type is Free Tier eligible in selected AWS regions.

To verify Free Tier eligible instance types:

```
aws ec2 describe-instance-types \
  --filters Name=free-tier-eligible,Values=true \
  --region us-west-2 \
  --query 'InstanceTypes[*].InstanceType'
```

---

## 🧹 Destroy Resources (Important)

To avoid unnecessary charges:

```
terraform destroy
```

Always destroy resources after testing.

---

## 📂 Project Structure

```
terraform-ec2-practice/
│
├── main.tf
├── .gitignore
└── .terraform.lock.hcl
```

---

## 🔒 Security Best Practices

- Do NOT commit `terraform.tfstate`
- Do NOT commit AWS credentials
- Use IAM users instead of root account
- Rotate access keys regularly

---

## 🎯 What This Project Demonstrates

- Infrastructure as Code (IaC)
- Terraform AWS Provider usage
- Dynamic AMI lookup
- Free Tier resource provisioning
- Safe Git practices with `.gitignore`

---

## 👨‍💻 Author

Wasim Akram  
DevOps Practice & Infrastructure Automation

---

🔥 This project is part of a hands-on DevOps learning journey focusing on automation, cloud provisioning, and infrastructure management using Terraform.
