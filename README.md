# EC2 to S3 Access using IAM Role – Troubleshooting

## 📌 Overview
This project demonstrates how EC2 accesses a private S3 bucket using IAM Roles and how different permission issues affect access.

---

## ❌ Scenario 1: No IAM Role
Command:
aws s3 ls s3://ec2-s3-private

Error:
Unable to locate credentials

👉 Reason: EC2 instance had no identity

---

## ❌ Scenario 2: IAM Role without Policy
Error:
Access Denied

👉 Reason: IAM Role existed but had no S3 permissions

---

## ✅ Scenario 3: IAM Role with Policy
Policy:
AmazonS3ReadOnlyAccess

Result:
Successfully accessed S3 bucket

---

## 🧠 Key Learning

Access in AWS requires:

Identity (IAM Role) + Permission (Policy)

- No identity → No credentials  
- No permission → Access Denied  
- Both present → Access granted  

---

## 🛠️ Tools Used
- AWS EC2
- AWS S3
- IAM Roles
- AWS CLI
